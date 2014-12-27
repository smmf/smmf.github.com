---
layout: page
title: Software
permalink: /software/
---

<!-- I have been involved in the development of the following software: -->

<!-- Below is a list with my most relevant contributions to software development -->
<!-- projects. -->

<!-- #Here's some of the software to which I've made significant contributions. -->

<!-- ***Here is a list of the most important (some) software products to whose -->
<!-- development I've contributed to.*** -->

<!-- **Here is a list of software to 'whose' development I’ve contributed to.** -->

<!-- In my software development activity I've contributed to the following ( -->

<!-- I've contributed to the development of the following software. -->

<!-- # Software -->

* [JVSTM]

  A Java Software Transactional Memory (STM) library. I redesigned the original
  lock-based implementation to produce the first lock-free multi-version STM
  implementation. This removed a performance bottleneck of the original
  version, allowing it to scale for a high number of CPU cores. Tests on a
  machine with more than 200 cores have shown continuous scalability of the
  new algorithm.

* [Fénix Framework]

  An object-oriented framework that allows the development of transactional
  Java applications with transparent persistence and strong
  consistency. Having been involved with the Fénix Framework from its
  inception, I became in charge of a complete overhaul of the framework,
  resulting in a major milestone release (version 2). The architectural
  redesign focused on supporting multiple data storage systems and transaction
  engines. I reimplemented all of its core modules, as well as several new
  modules for multiple backends.  Some of these modules have been used to
  support the [Cloud-TM] stack.
  
Both the [JVSTM] and the [Fénix Framework] are currently used as part of the
[FenixEDU] platform, which in turn is deployed in several production
environments.

* [WorkSCo]

  A workflow engine and a programming framework providing reusable workflow
  building blocks in Java. I defined the system’s micro-kernel architecture
  and implemented its core components.

[Cloud-TM]: http://www.cloudtm.eu/
[FenixEDU]: http://fenixedu.org/
[Fénix Framework]: http://fenix-framework.github.io/
[JVSTM]: http://inesc-id-esw.github.io/jvstm/
[WorkSCo]: http://sourceforge.net/projects/worksco/
