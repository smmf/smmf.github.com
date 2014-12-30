---
layout: page
title: Software
permalink: /software/
---

Some interesting software that I have either created or taken part in the
development.

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

# Main projects

* [JVSTM].  A Java Software Transactional Memory (STM) library. I redesigned
  the original lock-based implementation to produce the first lock-free
  multi-version STM implementation. This removed a performance bottleneck of
  the original version, allowing it to scale for a high number of CPU
  cores. Tests on a machine with more than 200 cores have shown continuous
  scalability of the new algorithm.

* [Fénix Framework].  An object-oriented framework that allows the development
  of transactional Java applications with transparent persistence and strong
  consistency. Having been involved with the Fénix Framework from its
  inception, I became in charge of a complete overhaul of the framework,
  resulting in a major milestone release (version 2). The architectural
  redesign focused on supporting multiple data storage systems and transaction
  engines. I reimplemented all of its core modules, as well as several new
  modules for multiple backends.  Some of these modules have been used to
  support the [Cloud-TM] stack.
  
Both the [JVSTM] and the [Fénix Framework] are currently used as part of the
[FenixEDU] platform, which in turn is deployed in several production
environments.  A significant part of my involvement with these two projects
has been included in
[my Ph.D. dissertation]({{site.url}}/permalinks/publications/2014-fernandes-phd.pdf).

* [WorkSCo].  A workflow engine and a programming framework providing reusable
  workflow building blocks in Java. I defined the system’s micro-kernel
  architecture and implemented its core components.

# Benchmarking et al.

* [TPC-W] benchmark.  A transactional web e-Commerce benchmark specified by
  the [Transaction Processing Performance Council](http://www.tpc.org/). I
  converted the original Java implementation of TPC-W to use it with the
  [Fénix Framework]. Since then, I have performed several enhancements to it:
  build process improvements; support for alternative storage backends
  (relational vs. key-value); collection of additional statistics; deployment
  configurations; etc.

* [PubSub] benchmark.  I developed a micro-benchmark aimed at measuring the
  performance of a publish/subscribe architecture in a distributed system.  I
  used it during my Ph.D. to evaluate concrete implementation alternatives.

* [jvstm-benchmarks].  While working on the [JVSTM], I often needed to compare
  the its performance between different versions.  I developed a Bash
  framework that allows for the execution of multiple STM benchmarks over
  multiple variants of the JVSTM: It supports running the benchmarks,
  processing the output and generating plots with the results.
  
* [Array] (now published as part of the [jvstm-benchmarks]).  A
  highly-configurable micro-benchmark application.  I wrote it mainly to
  stress test the [JVSTM]'s transactions.

* [P-Array].  A variant of the [Array] adding an exchangeable persistent data
  storage.  It is built with the [Fénix Framework].

## Data Grids

* [Additional plugins][RadarGun smf extras] for [RadarGun].  I've implemented
  the following plugins:
  
     * [jvstm1][RadarGun-jvstm1] and [jvstm2][RadarGun-jvstm1], respectively,
       for the [lock-based][JVSTM-lb] and [lock-free][JVSTM-lf] JVSTMs.  These
       use a ConcurrentHashMap to model a trivial key-value data store and
       they only support deployment to a single node.  I used these plugins to
       compare the performance of the two JVSTM implementations, using
       RadarGun's workloads.
       
     * [ff2][RadarGun-ff2] and [ff2-lf][RadarGun-ff2-lf] for the
       [Fénix Framework] using, respectively, the [lock-based][JVSTM-lb] and
       [lock-free][JVSTM-lf] JVSTMs.  Both plugins use the [Fénix Framework]
       to decorate **any** other RadarGun plugin, i.e. they use the
       [Fénix Framework] and configure its [backend][ff-backend-doc] to use
       the decorated RadarGun plugin of choice, for data storage.  With these
       two plugins it becomes possible to compare the performance of any data
       grid with and without the [Fénix Framework] installed, without any
       changes to the application under test.

     * [tdmock][RadarGun-tdmock].  This is a Mock Data Grid implementation.
       It simulates a data grid that does not involve any synchronization
       costs between its nodes.  This is useful to compare data grid
       performance with and without inter-node communication.
     
<!-- # Misc -->

<!-- * [Advice] -->

<!--   A Java library to support a simple -->
<!--   [method advising](http://en.wikipedia.org/wiki/Advice_(programming)) -->
<!--   technique. -->

<!-- * [csv_average.sh] -->

<!-- * [deal_poker.sh] -->

[Array]: https://github.com/inesc-id-esw/jvstm-benchmarks/tree/master/array
[Advice]: http://inesc-id-esw.github.io/advice/
[Cloud-TM]: http://www.cloudtm.eu/
[FenixEDU]: http://fenixedu.org/
[Fénix Framework]: http://fenix-framework.github.io/
[JVSTM]: http://inesc-id-esw.github.io/jvstm/
[WorkSCo]: http://sourceforge.net/projects/worksco/
[TPC-W]: https://github.com/fenix-framework/examples/tree/develop/tpcw
[PubSub]: https://github.com/smmf/pubsub-bench
[jvstm-benchmarks]: https://github.com/inesc-id-esw/jvstm-benchmarks
[P-Array]: https://github.com/smmf/p-array
[RadarGun]: https://github.com/radargun/radargun
[RadarGun smf extras]: https://github.com/smmf/radargun


[RadarGun-tdmock]: https://github.com/smmf/radargun/tree/feature/stm-plugins/plugins/tdmock
[RadarGun-jvstm1]: https://github.com/smmf/radargun/tree/feature/stm-plugins/plugins/jvstm1 
[RadarGun-jvstm2]: https://github.com/smmf/radargun/tree/feature/stm-plugins/plugins/jvstm2
[RadarGun-ff2]: https://github.com/smmf/radargun/tree/feature/stm-plugins/plugins/ff2
[RadarGun-ff2-lf]: https://github.com/smmf/radargun/tree/feature/stm-plugins/plugins/ff2-lf
[RadarGun-tdmock]: https://github.com/smmf/radargun/tree/feature/stm-plugins/plugins/tdmock
[JVSTM-lb]: https://github.com/inesc-id-esw/jvstm/tree/jvstm-lock-based
[JVSTM-lf]: https://github.com/inesc-id-esw/jvstm
[ff-backend-doc]: http://fenix-framework.github.io/BackEnds.html
