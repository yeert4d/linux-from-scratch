# Overview

This document serves as a structured build log and technical journal document and is recorded incrementally as each stage is completed.

The primary goal of this project is educational: to develop a concrete understanding of how a linux system is constructed.

All work is performed within a controlled virtualised environment to ensure reproducibility and isolation from the host system. The build follows:
  - Host system: Debian 12
  - LFS documentation version: 12.4
  - Target architechture: x86_64
  - Firmware mode: BIOS

Documentation within this repository is intentionally chronological and reflective. Alongside commands and configuration steps, it records errors encountered, design decisions made, and the reasoning behind fixes. This approach prioritises understanding and traceability over speed or automation.

This project is not intended to produce a production-ready distribution. Instead, it functions as an artefact for learning and reference for low-level Linux system construction.
