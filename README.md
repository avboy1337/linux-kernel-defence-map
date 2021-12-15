# Linux Kernel Defence Map

## Intro

Linux kernel security is a very complex topic.

There are many concepts that have interesting relationships with each other:
 - Vulnerability classes
 - Exploitation techniques
 - Bug detection mechanisms
 - Defence technologies

Some defence technologies are provided by the Linux kernel mainline.
Others are going out‑of‑tree for various reasons (some of them are commercial, for example).
Moreover, there are kernel defences that depend on special hardware features.

It would be convenient to have a graphical representation of Linux kernel security.
That's why I have created a __Linux Kernel Defence Map__ showing the relationships between all these concepts.

The node connections don't mean "full mitigation." Rather, each connection represents some kind of relationship.
So the Linux Kernel Defence Map should help to navigate the documentation and Linux kernel sources.
It also provides the Common Weakness Enumeration (CWE) numbers for vulnerability classes.

This map describes kernel security hardening. It doesn't cover cutting attack surface, userspace security features
and policies enforced by various Linux Security Modules (LSM).

## How this Map is made

This map is written in the DOT language, which makes maintenance and updating in Git very convenient.
The diagram is generated using GraphViz with the following command:
```
dot -Tsvg linux-kernel-defence-map.dot -o linux-kernel-defence-map.svg
```

## Do you want to check your kernel configuration?

So there are plenty of security hardening options in the Linux kernel. A lot of them are
not enabled by the major distros. We have to configure these options ourselves to
make our systems more secure.

But nobody likes verifying configs manually. So I've created the [__kconfig-hardened-check__][1]
that checks security hardening options of the Linux kernel.
You are welcome to try it.

## Documentation

- Grsecurity features:

  https://grsecurity.net/features.php

- The State of Kernel Self Protection by Kees Cook:

  https://outflux.net/slides/2018/lca/kspp.pdf

- Linux kernel security documentation:

  https://www.kernel.org/doc/html/latest/security/self-protection.html

- Linux kernel mitigation checklist by Shawn C:

  https://github.com/hardenedlinux/grsecurity-101-tutorials/blob/master/kernel_mitigation.md

- Trends, challenge, and shifts in software vulnerability mitigation by MSRC:

  https://github.com/Microsoft/MSRC-Security-Research/tree/master/presentations/2019_02_BlueHatIL

- Pursuing Durable Safety for Systems Software by Matt Miller [@mamillmsft][2]:

  https://www.sstic.org/2020/presentation/ouverture_2020/

- A Decade of Linux Kernel Vulnerabilities, their Mitigation and Open Problems by Abhilash Raj:

  https://github.com/maxking/linux-vulnerabilities-10-years

- Linux Kernel Runtime Guard (LKRG) threat model:

  https://openwall.info/wiki/p_lkrg/Threat_model

- Spectre & Meltdown Checker by Stéphane Lesimple [@speed47][3]

  https://github.com/speed47/spectre-meltdown-checker

## Map for Linux kernel v5.13

![Linux Kernel Defence Map](./linux-kernel-defence-map.svg)

[1]: https://github.com/a13xp0p0v/kconfig-hardened-check
[2]: https://github.com/mamillmsft
[3]: https://github.com/speed47
