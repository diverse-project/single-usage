# Single Usage Diversification

## Context

Extreme modularity and high level of reuse based on shared repositories results in an emergent phenomenon: the popularity of some libraries is growing extremely rapidly, leading to a situation of monopoly that homogenize software stacks. 
For example, there are many implementations of Java libraries, but Guava and Apache Commons artifacts are *de facto* [standard solutions](https://www.javaworld.com/article/2924315/open-source-tools/javas-top-20-the-most-used-java-libraries-on-github.html). 
Similarly, NodeJS and JQuery are real monocultures in the JavaScript world.
Software artifact monoculture represents a threat to large systems, which face risks in terms of dependability, i.e., safety, [security](https://www.infoworld.com/article/3003197/security/library-misuse-exposes-leading-java-platforms-to-attack.html), performance,  or maintainability.

This project defends the idea that behind this problem there is a real opportunity, created by the open source software infrastructure for DevOps software engineering tools and techniques. Indeed, software engineering tools used in DevOps provide API, models, or domain-specific languages to drive the automation. 
- Dependency managers, coupled with artifact repositories,  such as Node.js/npm, Yarn, Maven/Gradle have a model to describe the list of dependencies. 
- Configuration managers such as Ansible, Chef, or Vagrant  propose their own domain-specific language to describe software provisioning and configuration. 
- The Docker container technology also provides domain-specific languages for describing image provisioning as well as the application architecture, taking advantage of emerging technologies such as SDN and NFV. At the infrastruture level, the use of TOSCA along with MANO, YANG/Netconf, and other standards are important factor of success in NFV adoption to help deliver orchestration and interoperability of services. 

This project has one main objectives: providing continuous software evaluation and diversification integrated in Continuous Integration and Continuous Deployment pupeline. We aim at illustrating the combined used of novel program/model analysis and code/model transformation techniques to dynamically evaluate software quality and to automatically diversify applications (from implementation to deployment) to decrease software monoculture.


Our goal is to leverage from the existing software engineering work that aims at handling imposed software variability and synthesize large quantities of variants (not only at the source code level) that relax rigidities and reduce the risks of massive hacks. 
**We claim that the  apparition of a very high degree of automation at multiple stages of the software engineering life cycle hand over a good context for dynamic quality evaluation and automated diversity at multiple stages of this life cycle**. 

We believe that the domain-specific languages and the models supplied with the recent software engineering tools provide an abstraction level that, combined with software artifact repositories and with SDI and loosely coupled software architectures based on micro-services, create an affordable context for creating software that can be diversified at different life cycle phases and whose operation quality can be dynamically evaluated.

This repository contains pointers to **single-usage** diversification projects to create this continuous diversification pipeline. 

## Software 

This repositoru contains a set of tools to automatically generate mutants for standard Java project build using maven and deploy using docker as shown in figure below. 

![](https://hackmd.diverse-team.fr/uploads/upload_068d78b0ca8306f458605e955c306e7b.png)

In this toolchain, we propose six main projects.
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
