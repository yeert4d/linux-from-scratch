## 📌 Table of Contents

1. [Overview](#linux-from-scratch)
2. [Scope and Intent](#scope-and-intent)
3. [Environment](#environment)
4. [Structure](#structure)
5. [Status](#status)
6. [Next Steps](#next-steps)


# Linux-from-scratch - Build Log

This repository documents my build of a linux system from first principles by
following the Linux from scratch (LFS) methodology.

The goal of this project is educational: to understand how a Linux system is constructed
at a low level, including toolchains, libraries, the kernel, and the boot process.

This is a **build log and learning record**, not a production distribution.

---

## Scope and intent 
This section is current, and subject to expansion.

This project focuses on:
  -Understanding the Linux boot process;
  -Building a toolchain from source;
  -Learning how core system components interact;
  -Documenting decisions, mistakes, and fixed.

Out of scope:
  -Desktop environments;
  -Package managers;
  -Usability or polish;
  -Long term maintenance as a distro.

---

## Environment
  -**Host OS:** Debian (stable);
  -**Environment:** VirtualBox virtual machine (BIOS mode)
  -**Approach:** Minimal host system, terminal-based workflow

Virtualisation is used to ensure isolation, reproducibility and safe experimentation. 

---

## Structure
  -"docs/" - high level explanations and rationale.
  -"notes/" - cronological build notes and observations.

This repository prioritieses **clarity over completeness**.

---

## Status

This project is in process. 
As the build proceeds notes will be added incrementally.

## Next steps

The next items planned for this project are:
  -Document host toolchain setup (Debian host);
  -Begin LFS Chapter 2 build notes;
  -Capture errors and fixes as they occur;
  -Write up lessons learned after initial system build.

  


