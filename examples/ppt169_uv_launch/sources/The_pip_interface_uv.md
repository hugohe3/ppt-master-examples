<!--
  Source: https://docs.astral.sh/uv/pip/
  Crawled: 2026-09-05T05:57:11.046354
  Author: charliermarsh
-->

# The pip interface | uv

> uv is an extremely fast Python package and project manager, written in Rust.

# [The pip interface](#the-pip-interface)

uv provides a drop-in replacement for common `pip`, `pip-tools`, and `virtualenv` commands. These commands work directly with the virtual environment, in contrast to uv's primary interfaces where the virtual environment is managed automatically. The `uv pip` interface exposes the speed and functionality of uv to power users and projects that are not ready to transition away from `pip` and `pip-tools`.

The following sections discuss the basics of using `uv pip`:

- [Creating and using environments](environments/)
- [Installing and managing packages](packages/)
- [Inspecting environments and packages](inspection/)
- [Declaring package dependencies](dependencies/)
- [Locking and syncing environments](compile/)

Please note these commands do not *exactly* implement the interfaces and behavior of the tools they are based on. The further you stray from common workflows, the more likely you are to encounter differences. Consult the [pip-compatibility guide](compatibility/) for details.

Important

uv does not rely on or invoke pip. The pip interface is named as such to highlight its dedicated purpose of providing low-level commands that match pip's interface and to separate it from the rest of uv's commands which operate at a higher level of abstraction.

 Back to top