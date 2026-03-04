# wm_dev_sys_tos__wmrtos

<p align="center">
<!-- ![WMRTOS image](./img/wmrtos500.png "WMRTOS image") -->
<!-- !img src="./img/wmrtos500.png" alt="WMRTOS image" /-->
</p>

Clean-room multi-architecture reimplementation of 90s **Atari** **TOS** and **MultiTOS**, updated for current usage.

* Home

https://github.com/wenuam/wm_dev_sys_tos__wmrtos

* Also

[atari-tos] contains software documentations.

[atari-tos]: https://github.com/Kochise/atari-tos

## Purpose

This operating system is aimed at embedded capable devices (200 MHz `CPU`, 32 MB `RAM`), with or without graphic interface.

Its legacy comes from the original [Atari] [TOS] architecture circa 1985-1993. However adapted to nowadays technologies and protocols.

[Atari]: https://en.wikipedia.org/wiki/Atari_Corporation
[TOS]: https://en.wikipedia.org/wiki/Atari_TOS

Considering the "evolution" of recent operating systems being mostly cosmetic ([Liquid Glass], dark mode, more "simplified" user interface, AI agent), there is hardly nothing new that a 2000s system wasn't capable of from a daily usage point of view: still browsing the web, manipulating files, watching video, playing games, doing office/dev/2D/3D works, etc.

[Liquid Glass]: https://www.nngroup.com/articles/liquid-glass/

Only better monitor, mouse and sound system.

So with the advent of the "AI" craze rendering perfectly capable systems obsolete (*cough* **Windows 11** *cough*) an updated **TOS** could just suffice to run these system back to life again. Yeah, [BSD] could probably do it too to an extend, but that's not the point...

[BSD]: https://en.wikipedia.org/wiki/Berkeley_Software_Distribution

The only "problem" being software support, what made the yet ill-fated `x86` architecture so prominent thank to its almost impeccable backward compatibility.

## History

In our days and ages (2026) never has been the operating system landscape so fragmented. While people could argue we now only have to deal with [Windows], [Linux] and [MacOS], however it couldn't be further from the truth.

[Windows]: https://en.wikipedia.org/wiki/Microsoft_Windows
[Linux]: https://en.wikipedia.org/wiki/Linux
[MacOS]: https://en.wikipedia.org/wiki/MacOS

Just take a look by yourself (scroll left-right, up-down): https://eylenburg.github.io/os_familytree.htm

While many "branches" stalled and even disappeared, there are many more open now than previously. You may find the **Atari** **TOS** around the middle vertically, a short grey line spanning from 1985 to 1995.

Its root comes from [Digital Research Inc] the then leader in operating system development and distribution. You may find the **DRI** [CP/M] around the first third vertically, a light blue tree spanning from 1974 to around 2005. Yet [DR-DOS] still have up-to-date descendants.

[Digital Research Inc]: https://en.wikipedia.org/wiki/Digital_Research
[CP/M]: https://en.wikipedia.org/wiki/CP/M
[DR-DOS]: https://en.wikipedia.org/wiki/DR-DOS

While seemingly dead, many unlinked yet directly inspired operating systems are sharing common "DNA" with its original architecture. The general concepts of resource management and process creation remains about 90% the same despite the age difference.

Just like wheels haven't changed much through time.

For a more complete and in-depth analysis of the **TOS** you may follow the [atari-tos] link above.

Thus **WMRTOS** basically resumes where **TOS** stopped around version 4.92 (1993 beta) and leaps forward restarting at version 5.00.

Versions with fewer functionalities will have number lower than 5.00, following a very precise and detailed numbering scheme though, to avoid collisions.

## Features

The main feature of **WMRTOS** is having a virtual `CPU` support through the use of the [Motorola]/[NXP] [68000] `ISA` as "universal byte-code" execution engine. Mostly because its features defined most of legacy **TOS** architecture (16 bits, big endian, flat memory model, etc).

[Motorola]: https://en.wikipedia.org/wiki/Motorola
[NXP]: https://en.wikipedia.org/wiki/NXP_Semiconductors
[68000]: https://en.wikipedia.org/wiki/Motorola_68000

This also prevent fragmenting the various `SDK` support like many short lived `CPU` did, rendering yet capable hardware obsolete because of no more software update available. Who remember the [S3C2440] ?

[S3C2440]: https://www.google.com/search?q=S3C2440

The choice of **68000** over more recent `ISA` like [ARM] or [RISC-V] also takes into account the large documentation and knowledge base acquired through its wide spread usage in various computers, video game systems, industrial controllers, etc.

[ARM]: https://en.wikipedia.org/wiki/ARM_architecture_family
[RISC-V]: https://en.wikipedia.org/wiki/RISC-V

At one point the world turned [RISC] to "simplify" the compilers' development yet there never have been so many incompatible `CPU` declinations and extensions ([AVX], [Neon], etc) rendering the process completely pointless.

[RISC]: https://en.wikipedia.org/wiki/Reduced_instruction_set_computer
[AVX]: https://en.wikipedia.org/wiki/Advanced_Vector_Extensions
[Neon]: https://www.arm.com/technologies/neon

So a virtualization engine leverage the diverse `CPU` architectures to a range of updated **68000**-like `ISA`, preserving the original philosophy, yet still gaining access to recent features synthetically factored and simplified. But not censored "for the kids" though.

At first it started like a [fantasy] `CPU` evolution in an [alternative timeline], yet the idea grew into a more plausible approach to modern computing folding back to its root, like an ancient "black hole" growing when merging less capable or short lived system, becoming a multi-purpose behemoth.

[fantasy]: https://github.com/paladin-t/fantasy
[alternative timeline]: https://github.com/Kochise/m68140

The underlying `CPU` still providing the power to run the system though, but "unified" from an `ISA` standpoint, just like [Java] with its [JVM] on a middleware level.

[Java]: https://en.wikipedia.org/wiki/Java_(programming_language)
[JVM]: https://en.wikipedia.org/wiki/JVM_bytecode

However a **68000** emulation is infinitely lighter and faster to run if correctly "virtualized" through the use of [JIT].

[JIT]: https://en.wikipedia.org/wiki/Just-in-time_compilation
