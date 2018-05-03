# Single Usage Diversification

This repository contains pointers to **single-usage** diversification projects.

## Content
  - `tools/`
    - `diversification/`
      - [`sosiefier`](https://github.com/DIVERSIFY-project/sosiefier) is a project that aims at exploring the space of sosie of a Java program (ie. program variants that passes the original test suite)
      - [`diversify-mvn`](https://github.com/maxleiko/diversify-mvn) is a CLI that will automate the creation of mutants of a given Maven project by modifying its dependencies versions, and by validating the project behavior using a Docker sandbox.
      - [`liven`](https://github.com/diverse-project/liven) is a diversity hypervisor. It enable continuous diversification in software life cycle.
    - `monitoring/`
      - [`yajta`](https://github.com/diverse-project/yajta) is an extensible library for byte code probe insertion. Its built on top of javassist. It allows to build tracing agent but is not limited to this task
      - [`syscall`](https://gist.github.com/nharrand/6f73d26d0ea1ece5a301c8b68eff556c) sysdig chysel that log Docker container syscalls
  - `xp/`
    - [`diversify-jicofo`](https://github.com/maxleiko/diversify-jicofo) is an example use-case for **diversify-mvn**