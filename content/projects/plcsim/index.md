---
title: "PLCsim"
date: 2026-11-11
draft: false
weight: 40
summary: "A free, in-browser ladder logic trainer for students in an introductory PLC course."
description: "A free, in-browser ladder logic trainer for students in an introductory PLC course."
tags: ["vibecoding", "plc", "education"]
---

A free, in-browser practice environment for Allen-Bradley-style ladder logic as programmed in RSLogix 500, built for students in an introductory PLC course who don't have the software or a trainer at home. The default controller is the MicroLogix 1000.

Code: [github.com/sinkomr/PLCsim](https://github.com/sinkomr/PLCsim)

## What it does

- **Lessons from zero:** what a PLC is, number systems, addressing, the scan cycle, contacts and coils, seal-in circuits, latches, timers, counters, and on through subroutines, sequencers and troubleshooting. Each lesson has quizzes and examples you can load and run.
- **A ladder editor** in the RSLogix 500 style, with branches, drag and drop, rung comments and text rung editing.
- **A scan-accurate simulator:** input scan, program scan, output scan, with the real data files, timer and counter status bits, math flags and major faults.
- **Animated machines** wired to the I/O: motor start/stop, a traffic light, a parking garage, tank fill and mix, a box conveyor.
- **Auto-graded challenges:** a written job spec plus automated tests that operate the machine and report pass or fail with a timing diagram.

No install, no build step, no server. It is plain HTML, CSS and JavaScript, and it works offline once loaded.

PLCsim is an independent educational project, not affiliated with or endorsed by Rockwell Automation. It does not talk to real PLCs.
