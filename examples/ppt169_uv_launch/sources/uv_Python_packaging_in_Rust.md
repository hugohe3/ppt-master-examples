<!--
  Source: https://astral.sh/blog/uv
  Crawled: 2026-09-05T05:57:19.720763
-->

# uv: Python packaging in Rust

> uv is an extremely fast Python package installer and resolver, designed as a drop-in alternative to pip and pip-tools.

- [](/blog/rss.xml)
- [](https://x.com/share?text=uv: Python packaging in Rust&url=https://astral.sh/blog/uv&via=astral_sh)
- [](https://news.ycombinator.com/submitlink?u=https://astral.sh/blog/uv&t=uv: Python packaging in Rust)
- [](https://www.reddit.com/submit?url=https://astral.sh/blog/uv&title=uv: Python packaging in Rust)[Back to blog](/blog)

 February 15, 2024

# uv: Python packaging in Rust

![Charlie Marsh](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

##### Charlie Marsh

[@charliermarsh](https://x.com/charliermarsh)

**TL;DR:**[uv](https://github.com/astral-sh/uv) is an **extremely fast Python package installer and resolver**, written in Rust, and designed as a drop-in replacement for `pip` and `pip-tools` workflows.

[uv](https://github.com/astral-sh/uv) represents a milestone in our pursuit of a ["Cargo for Python"](https://blog.rust-lang.org/2016/05/05/cargo-pillars.html#pillars-of-cargo): a comprehensive Python project and package manager that's fast, reliable, and easy to use.

As part of this release, we're also taking stewardship of [Rye](https://github.com/mitsuhiko/rye), an experimental Python packaging tool from [Armin Ronacher](https://github.com/mitsuhiko). We'll maintain [Rye](https://github.com/mitsuhiko/rye) as we expand [uv](https://github.com/astral-sh/uv) into a unified successor project, to fulfill our [shared vision](https://rye-up.com/philosophy/) for Python packaging.

---

At Astral, we build high-performance developer tools for the Python ecosystem. We're best known for [Ruff](https://github.com/astral-sh/ruff), an extremely fast Python [linter](https://notes.crmarsh.com/python-tooling-could-be-much-much-faster) and [formatter](https://astral.sh/blog/the-ruff-formatter).

Today, we're releasing the next tool in the Astral toolchain: **[uv](https://github.com/astral-sh/uv), an extremely fast Python package resolver and installer, written in Rust**.

0s 1s 2s 3s uv poetry pip-compile pdm 0.60s 1.56s 3.37s 0.01s 0s 2s 4s uv poetry pdm pip-sync 0.99s 1.90s 4.63s 0.06s 0s 1s 2s 3s uv poetry pip-compile pdm 0.60s 1.56s 3.37s 0.01s 0s 2s 4s uv poetry pdm pip-sync 0.99s 1.90s 4.63s 0.06s 

Resolving (left) and installing (right) the[Trio](https://github.com/python-trio/trio)dependencies with awarmcache, to simulaterecreating a virtual environment or adding a dependency to an existing project([source](https://github.com/astral-sh/uv/blob/main/BENCHMARKS.md)).

Resolving (top) and installing (bottom) the[Trio](https://github.com/python-trio/trio)dependencies with awarmcache, to simulaterecreating a virtual environment or adding a dependency to an existing project([source](https://github.com/astral-sh/uv/blob/main/BENCHMARKS.md)).

[uv](https://github.com/astral-sh/uv) is designed as a drop-in replacement for `pip` and `pip-tools`, and is ready for production use today in projects built around those workflows.

Like [Ruff](https://github.com/astral-sh/ruff), uv's implementation was grounded in our core product principles:

- **An obsessive focus on performance.** In the above [benchmarks](https://github.com/astral-sh/uv/blob/main/BENCHMARKS.md), uv is **8-10x faster** than `pip` and `pip-tools` without caching, and **80-115x faster** when running with a warm cache (e.g., recreating a virtual environment or updating a dependency). uv uses a global module cache to avoid re-downloading and re-building dependencies, and leverages Copy-on-Write and hardlinks on supported filesystems to minimize disk space usage.
- **Optimized for adoption.** While we have big aspirations for the future of Python packaging, uv's initial release is centered on supporting the `pip` and `pip-tools` APIs behind our `uv pip` interface, making it usable by existing projects with zero configuration. Similarly, uv can be used as "just" a resolver (`uv pip compile` to lock your dependencies), "just" a virtual environment creator (`uv venv`), "just" a package installer (`uv pip sync`), and so on. It's both unified and modular.
- **A simplified toolchain.** uv ships as a single static binary capable of replacing `pip`, `pip-tools`, and `virtualenv`. uv has no direct Python dependency, so you can install it separately from Python itself, avoiding the need to manage `pip` installations across multiple Python versions (e.g., `pip` vs. `pip3` vs. `pip3.7`).

While uv will evolve into a **complete Python project and package manager** (a ["Cargo for Python"](https://blog.rust-lang.org/2016/05/05/cargo-pillars.html#pillars-of-cargo)), the narrower `pip-tools` scope allows us to solve the low-level problems involved in building such a tool (like package installation) while shipping something immediately useful with minimal barrier to adoption.

You can install [uv](https://github.com/astral-sh/uv) today via our standalone installers, or from [PyPI](https://pypi.org/project/uv/).

curlwinpippipx

```
$ curl -LsSf https://astral.sh/uv/install.sh | sh
```

```
$ powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

```
$ pip install uv
```

```
$ pipx install uv
```

[uv](https://github.com/astral-sh/uv) supports everything you'd expect from a modern Python packaging tool: editable installs, Git dependencies, URL dependencies, local dependencies, constraint files, source distributions, custom indexes, and more, all designed around drop-in compatibility with your existing tools.

[uv](https://github.com/astral-sh/uv) supports **Linux**, **Windows**, and **macOS**, and has been tested at-scale against the public PyPI index.

### A drop-in compatible API[#](#a-drop-in-compatible-api)

This initial release centers on what we refer to as uv's `pip` API. It'll be familiar to those that have used `pip` and `pip-tools` in the past:

- Instead of `pip install`, run `uv pip install` to install Python dependencies from the command line, a requirements file, or a `pyproject.toml`.
- Instead of `pip-compile`, run `uv pip compile` to generate a locked `requirements.txt`.
- Instead of `pip-sync`, run `uv pip sync` to sync a virtual environment with a locked `requirements.txt`.

By scoping these "lower-level" commands under `uv pip`, we retain space in the CLI for the more "opinionated" project management API we intend to ship in the future, which will look more like [Rye](https://github.com/mitsuhiko/rye), or [Cargo](https://github.com/rust-lang/cargo), or [Poetry](https://github.com/python-poetry/poetry). (Imagine `uv run`, `uv build`, and so on.)

uv can also be used as a virtual environment manager via `uv venv`. It's about 80x faster than `python -m venv` and 7x faster than `virtualenv`, with no dependency on Python.

uv virtualenv venv uv virtualenv venv 0s 0.02s 0.04s 0.06s 0.08s 74.4ms 24.1ms 4.1ms 0s 0.5s 1s 1.5s 141.4ms 1.54s 18.2ms  0s  0.5s  1s  1.5s  uv  virtualenv  venv 141.4ms 1.54s 18.2ms  0s  0.02s  0.04s  0.06s  0.08s  uv  virtualenv  venv 74.4ms 24.1ms 4.1ms 

Creating a virtual environment, with (top) and without (bottom) seed packages like pip and setuptools ([source](https://github.com/astral-sh/uv/blob/ea13d94c57149a8fc6ebfcef46149252e869269f/scripts/benchmarks/venv.sh)).

Creating a virtual environment, with (left) and without (right) seed packages like pip and setuptools ([source](https://github.com/astral-sh/uv/blob/ea13d94c57149a8fc6ebfcef46149252e869269f/scripts/benchmarks/venv.sh)).

uv's virtual environments are standards-compliant and work interchangeably with other tools — there's no lock-in or customization.

Building our own package management stack from scratch also opened up room for new capabilities. For example:

- **uv supports alternate resolution strategies.** By default, uv follows the standard Python dependency resolution strategy of preferring the latest compatible version of each package. But by passing `--resolution=lowest`, library authors can test their packages against the lowest-compatible version of their dependencies. (This is similar to Go's [Minimal version selection](https://go.dev/ref/mod#minimal-version-selection).)
- **uv allows for resolutions against arbitrary target Python versions.** While `pip` and `pip-tools` always resolve against the currently-installed Python version (generating, e.g., a Python 3.12-compatible resolution when running under Python 3.12), uv accepts a `--python-version` parameter, enabling you to generate, e.g., Python 3.7-compatible resolutions even when running under newer versions.
- **uv allows for dependency “overrides”.** uv takes pip's “constraints” concepts a step further via overrides (`-o overrides.txt`), which allow the user to guide the resolver by overriding the declared dependencies of a package. Overrides give the user an escape hatch for working around erroneous upper bounds and other incorrectly-declared dependencies.

In its current form, uv won't be the right fit for all projects. `pip` is a mature and stable tool, with extensive support for an extremely wide range of use cases and a focus on compatibility. While uv supports a large fraction of the `pip` interface, it lacks support for some of its legacy features, like `.egg` distributions.

Similarly, uv does not yet generate a platform-agnostic lockfile. This matches `pip-tools`, but differs from Poetry and PDM, making uv a better fit for projects built around the `pip` and `pip-tools` workflows.

For those deep in the packaging ecosystem, uv also includes standards-compliant Rust implementations of [PEP 440](https://peps.python.org/pep-0440/) (version identifiers), [PEP 508](https://peps.python.org/pep-0508/) (dependency specifiers), [PEP 517](https://peps.python.org/pep-0517/) (a build-system independent build frontend), [PEP 405](https://peps.python.org/pep-0405/) (virtual environments), and more.

### A "Cargo for Python": uv and Rye[#](#a-cargo-for-python-uv-and-rye)

uv represents an intermediary milestone in our pursuit of a ["Cargo for Python"](https://blog.rust-lang.org/2016/05/05/cargo-pillars.html#pillars-of-cargo): a unified Python package and project manager that is extremely fast, reliable, and easy to use.

Think: a single binary that bootstraps your Python installation and gives you everything you need to be productive with Python, bundling not only `pip`, `pip-tools`, and `virtualenv`, but also `pipx`, `tox`, `poetry`, `pyenv`, `ruff`, and more.

Python tooling can be a low-confidence experience: it's a significant amount of work to stand up a new or existing project, and commands fail in confusing ways. In contrast, when working in the Rust ecosystem, you trust the tools to succeed. The Astral toolchain is about bringing Python from a low-confidence to a high-confidence experience.

This vision for Python packaging is not far off from that put forward by [Rye](https://github.com/mitsuhiko/rye), an experimental project and package management tool from [Armin Ronacher](https://github.com/mitsuhiko).

In talking with Armin, it was clear that our visions were closely aligned, but that fulfilling them would require a significant investment in foundational tooling. For example: building such a tool requires an extremely fast, end-to-end integrated, cross-platform resolver and installer. **In uv, we've built that foundational tooling.**

We saw this as a rare opportunity to team up, and to avoid fragmenting the Python ecosystem. **As such, in collaboration with Armin, we're excited to be taking over [Rye](https://github.com/mitsuhiko/rye).** Our goal is to evolve uv into a production-ready ["Cargo for Python"](https://blog.rust-lang.org/2016/05/05/cargo-pillars.html#pillars-of-cargo), and to provide a smooth migration path from Rye to uv when the time is right.

Until then, we'll be maintaining Rye, migrating it to use uv under-the-hood, and, more generally, treating it as an experimental testbed for the end-user experience we're building towards.

While merging projects comes with its own challenges, we're committed to building a single, unified tool under the Astral banner, and to supporting existing Rye users as we evolve uv into a suitable and comprehensive successor project.

### Our Roadmap[#](#our-roadmap)

Following this release, our first priority is to support users as they consider [uv](https://github.com/astral-sh/uv), with a focus on improving compatibility, performance, and stability across platforms.

From there, we'll look towards expanding uv into a complete Python project and package manager: a single binary that gives you everything you need to be productive with Python.

We have an ambitious roadmap for uv. But even in its current form, I think it will feel like a very different experience for Python. I hope you'll give it a try.

### Acknowledgements[#](#acknowledgements)

Finally, we'd like to thank all those that contributed directly or indirectly to the development of uv. Foremost among them are [Jacob Finkelman](https://github.com/Eh2406) and [Matthieu Pizenberg](https://github.com/mpizenberg), the maintainers of [pubgrub-rs](https://github.com/pubgrub-rs/pubgrub). uv uses PubGrub as its underlying version solver, and we're grateful to Jacob and Matthieu for the work they put into PubGrub in the past, and for the way they've engaged with us as collaborators throughout the project.

We'd also like to thank those projects in the packaging space that've inspired us, especially [Cargo](https://github.com/rust-lang/cargo), along with [Bun](https://github.com/oven-sh/bun), [Orogene](https://github.com/orogene/orogene), and [pnpm](https://github.com/pnpm/pnpm) from the JavaScript ecosystem, and [Posy](https://github.com/njsmith/posy), [Monotrail](https://github.com/konstin/monotrail-resolve), and [Rye](https://github.com/mitsuhiko/rye) from the Python ecosystem. In particular, thanks to [Armin Ronacher](https://github.com/mitsuhiko) for collaborating with us on this effort.

Finally, we'd like to thank the maintainers of [pip](https://github.com/pypa/pip) and the members of the PyPA more broadly for all the work they do to make Python packaging possible.