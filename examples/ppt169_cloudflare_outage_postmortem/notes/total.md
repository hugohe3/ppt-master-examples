# 01_cover

This is a reconstruction of the Cloudflare outage of the eighteenth of November two thousand twenty-five, built entirely from Cloudflare's own published account of it. Two things are worth fixing before anything else. The first is the window: customer impact began at eleven twenty-eight and every service was restored at seventeen oh six, five hours and thirty-eight minutes later, and every time in this deck is Coordinated Universal Time. The second is the cause, stated by Cloudflare in the sentence on this page: the outage was not caused, directly or indirectly, by a cyber attack or malicious activity of any kind. That matters because the failure behaved for almost three hours as though it were an attack, and the people responding to it reasonably believed that it might be.

---

# 02_incident_summary

This page is written so it can be forwarded on its own. The four moments across the top are the ones Cloudflare records. At eleven oh five a change to a database access control was deployed. At eleven twenty-eight that deployment reached customer environments and the first errors appeared on customer HTTP traffic. At fourteen thirty a correct configuration file was deployed globally and the main impact ended. At seventeen oh six every downstream service was restarted and the incident closed. Underneath, the chain in four parts. A permissions change made a generated query return duplicate rows. The feature file that query builds doubled in size. The bots module inside the core proxy preallocates memory for at most two hundred machine-learning features, well above the roughly sixty actually in use, and the oversized file crossed that limit. Everything downstream of that limit returned errors. The point to hold on to is where the failure sat: in the ingestion of configuration Cloudflare generates for itself, not in the traffic that configuration governs.

---

# 03_impact_by_surface

Six product surfaces are named in the published account, and they did not all fail the same way. Four returned errors. Core CDN and security services returned HTTP five hundred errors to end users. Turnstile failed to load. Workers KV returned significantly elevated five hundred errors because requests to its front-end gateway went through the failing core proxy. Access saw widespread authentication failures until the rollback was initiated at thirteen oh five, though existing sessions were unaffected and every failed attempt returned an error page rather than reaching the target application. Two surfaces degraded instead. The dashboard stayed mostly operational, but most users could not log in because Turnstile was unavailable on the login page. Email Security kept processing and delivering mail, but lost access to an IP reputation source, which reduced spam-detection accuracy and stopped some new-domain-age detections; some Auto Move actions failed and Cloudflare states that all of them were reviewed and remediated. One effect sits outside the table: response latency rose across the CDN because the debugging and observability systems consumed large amounts of processor time enriching every uncaught error.

---

# 04_two_proxy_generations

An unrelated migration was in flight during the incident, and it split the customer experience in two. Cloudflare was moving traffic onto a new proxy engine called FL2. Customers already on FL2 saw HTTP five hundred errors for anything that depended on the bots module, and because Workers KV and Access sit behind the same core proxy, they failed too. Customers still on the older FL engine saw no errors at all. What they got instead was worse in a quieter way: bot scores were not generated correctly and every request received a bot score of zero, so any customer with a rule that blocks bots would have seen large numbers of false positives without an error page to explain them. And a third group saw nothing: customers who were not using the bot score in their rules were unaffected. Both behaviours are stated in the published account; neither is inferred here.

---

# 05_five_minute_cycle

This is the page that explains why the diagnosis took as long as it did. The feature file is regenerated every five minutes by a query running on a ClickHouse cluster, and that cluster was being updated gradually rather than all at once. Bad data was produced only when the query happened to run on a part of the cluster that had already been updated. So every five minutes the network received either a good file or a bad one, and the whole system failed and then recovered and then failed again. Cloudflare calls that behaviour very unusual for an internal error, and it is exactly what a fluctuating external attack looks like. Eventually every node was generating the bad file and the failure settled into a stable failing state. The chart is a schematic reconstruction drawn from that description. The event times on the horizontal axis are published; the height of the line is not. No error-rate magnitude appears anywhere in the account, so the vertical scale carries no published value and should not be read as one.

---

# 06_timeline_1105_1305

The first ninety-seven minutes, entry by entry. Eleven oh five, the database access control change is deployed and everything is still normal. Eleven twenty-eight, the deployment reaches customer environments and the first errors appear on customer HTTP traffic. Eleven thirty-one, an automated test detects the issue; manual investigation begins one minute later and the incident call is created at eleven thirty-five. From that point through thirteen oh five the team is investigating the wrong layer, and the account is candid about it: the visible symptom was a degraded Workers KV response rate causing downstream impact, so the mitigations attempted were traffic manipulation and account limiting. At thirteen oh five the first real relief arrives, when internal bypasses fail Workers KV and Cloudflare Access back to a prior version of the core proxy. That is one hour and thirty-seven minutes after impact began, and it happened before anyone knew what the trigger was.

---

# 07_timeline_1337_1706

The second half moves quickly once the trigger is identified. At thirteen thirty-seven the work narrows onto rolling the Bot Management configuration file back to a last-known-good version, with the file restore as the fastest of several parallel workstreams. At fourteen twenty-four two things happen: creation and propagation of new configuration files is stopped, and the test of the restored file completes successfully, at which point the fix is accelerated globally. At fourteen thirty a correct file is deployed everywhere and most services begin operating normally; downstream services start seeing reduced errors. The remaining two and a half hours are restarts, and at seventeen oh six every operation is fully restored. Three hours and two minutes from impact to main resolution, five hours and thirty-eight minutes to the end. Both durations are arithmetic on the published timestamps.

---

# 08_detection_and_diagnosis

The gap on this page is the most useful number in the review. Detection took three minutes: impact began at eleven twenty-eight and the first automated test fired at eleven thirty-one, with a human on it the following minute and an incident call four minutes later. Identifying which module was failing took two hours and fifty-three minutes beyond that. The alerting worked; the hypothesis is what cost the time, and the account names three reasons without excusing any of them. The failure alternated every five minutes as good and bad files took turns, which does not look like a code defect. Cloudflare's status page, which is hosted completely off Cloudflare's infrastructure with no dependencies on it, went down at the same moment by coincidence, which made it look as though something was targeting both. And the internal incident channel was already primed by a recent run of very large Aisuru denial-of-service attacks. Holding an attack hypothesis in that situation was reasonable; naming it here is not a criticism of holding it.

---

# 09_mechanism

Five stages, each of which behaved exactly as written. At eleven oh five a change made previously implicit permissions on the underlying database explicit, so users could now see metadata for tables in the r0 database as well as the default one. The query that builds the Bot Management feature file selects column names and types from the system columns table, filtered on the table name but not on the database name — the fragment on the left is the published query, and the missing database predicate is the whole story. With the new permissions, that query began returning the same columns twice, and the feature file's row count more than doubled. The bots module preallocates memory for at most two hundred machine-learning features as a performance optimisation, against roughly sixty in use, and the oversized file crossed that limit. The FL2 check on that limit produced an unhandled error and the thread panicked, which is the line on the right, and every request that depended on the bots module returned a five hundred. Each of those five facts is stated in the published account; the order that connects them is that account's own inferred sequence.

---

# 10_contributing_factors

Four conditions had to hold at once, and the review deliberately does not collapse them into one. Two are properties of code. An assumption about the query's scope, made years earlier and never restated, meant nobody revisited it when the permissions model changed. And a fixed limit that guarded memory had no bounded failure path behind it, so an input above the limit produced a panic rather than a rejected file or a degraded bot score. Two are properties of process. Configuration that Cloudflare generates for itself was validated less rigorously than configuration a customer supplies — we know this because the first published remediation item is to harden it in the same way as user-generated input, which states plainly that before this incident it was not. And the permissions change rolled out gradually across the cluster, so the output alternated and the failure signature looked like an attack rather than a deployment. Every one of these traces back to evidence on the timeline pages, and none of them is described here as the cause.

---

# 11_systemic_condition

The fourth factor from the previous page is the one that outlives this incident, so it becomes the subject here. Compare the two outages. In July two thousand nineteen, a new firewall rule containing a regular expression that backtracked enormously exhausted processor capacity on every core handling web traffic worldwide. It was distributed through Quicksilver, which pushes changes globally in seconds, and by design the firewall skipped the staged rollout process because it has to answer threats fast. The mitigation was a global kill switch, executed at fourteen oh seven, with traffic and processor levels back to normal two minutes later; twenty-seven minutes end to end. In November two thousand twenty-five, a database permissions change more than doubled a feature file that is refreshed every few minutes and published to the entire network for the same reason — so the model can react to new bots quickly. This time there was no per-feature kill switch to reach for, which is why the second published remediation item is to enable more of them. Six years apart, different triggers, same mechanism turning a local defect into a global one. Naming that shared condition is an inference drawn across two published accounts, not a claim either account makes.

---

# 12_what_went_well

A review that lists only failures teaches the wrong lesson, so three things are worth protecting. Automated detection worked and worked fast: three minutes from impact to the first alert, with a human investigating one minute later. A bypass path existed and was actually used — at thirteen oh five internal bypasses failed Workers KV and Cloudflare Access back to a prior version of the core proxy, which reduced impact for every system that depends on Workers KV, including Access itself, and it was done before anyone knew what the trigger was. And the older proxy generation degraded instead of failing outright: customers on FL saw no errors, and customers who were not using the bot score saw no impact at all. Each of those is an observed fact from the published account. The judgement that they are worth protecting is this review's.

---

# 13_corrective_actions

Cloudflare publishes four commitments, and this page maps each one to the factor it addresses. Hardening the ingestion of Cloudflare-generated configuration files the way user-generated input is hardened answers the validation factor and is prevention. Enabling more global kill switches for features answers the propagation factor and is mitigation. Eliminating the ability for core dumps and error reports to overwhelm system resources answers the latency effect and is also mitigation. Reviewing failure modes for error conditions across all core proxy modules answers the unbounded failure path and is prevention. The three columns on the right are the point of the page. A corrective action a review can hold anyone to needs an owner, a date, and a way to verify that it happened, and the published account states none of those for any of the four. Those columns read NO DATA rather than being quietly dropped, because an absence that is visible can be chased and an absence that is deleted cannot.

---

# 14_open_questions

Five things this record does not settle. Two are internal inconsistencies in the published timestamps. The opening paragraph says the network began experiencing significant failures at eleven twenty, while the incident timeline records impact starting at eleven twenty-eight; this deck uses eleven twenty-eight for every derived duration and says so wherever a duration appears. And the Workers KV bypass has three times attached to it — thirteen oh four for the patch, thirteen oh five for the bypass in the timeline, thirteen ten for restoration — describing one mitigation. Three are absences. No error count, request volume, affected-customer figure, availability number, or financial figure is published, so the cost of the outage is unknown. No owner, date, or verification method is attached to any corrective action. And the account commits to reviewing failure modes across all core proxy modules without saying whether any other module shares the same unbounded pattern, so that remains unconfirmed. Each item names the evidence that would settle it, and none of them is closed here with a plausible narrative.

---

# 15_sources

Everything in this deck is one click from its source. The primary record is Cloudflare's own post-incident account of the eighteenth of November, written by Matthew Prince, and it supports every page except the comparison. The second of July two thousand nineteen account supports the comparison page: the firewall rule, the Quicksilver propagation path, the global kill switch, and the twenty-seven minute recovery. The Cloudflare status page is listed as the operator's own event record, and it was deliberately not consulted for any figure here, so nothing in this deck depends on a page that was itself unavailable during the incident. The rules the deck follows are on the page. Times are Coordinated Universal Time to the minute, exactly as published. Elapsed durations are arithmetic and are labelled as derived. Nothing originates outside these documents, and where the account states no value the page says NO DATA or marks the item unconfirmed. The schematic chart carries no published magnitudes, and the four severity states used on the strip and in the tables are this review's reading of the published status column, not a scale Cloudflare defines.
