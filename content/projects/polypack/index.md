---
title: "PolyPack"
date: 2026-11-11
draft: false
weight: 20
summary: "Pack congruent polygons or circles into the smallest container, and compete for records."
description: "Pack congruent polygons or circles into the smallest container, and compete for records."
tags: ["vibecoding", "math", "optimization"]
---

Pack P congruent regular polygons or circles into the smallest regular polygon or circle, and compete for records.

Site: [polypack.fly.dev](https://polypack.fly.dev) · Code: [github.com/sinkomr/PolyPack](https://github.com/sinkomr/PolyPack)

## What it does

- **The board:** drag and rotate pieces that can never overlap. The smallest enclosing container and its size are computed live.
- **Records:** published values with their sources, and one live leader per problem. Problems with a proven optimum are closed to entries.
- **Automated search:** seven optimizers, seed generators and a contact polish, running in the browser or as a TypeScript library.
- **An API:** everything is scriptable, including submitting a packing your own optimizer found.
- **Volunteer computing:** a single-file program that searches in the background on spare cores and submits records under your name.
- **More dimensions:** beyond the classic flat problems there are curved spaces, polyhedral surfaces, spheres and tori, solids packed in solids, and unit balls on the boundary of 4D polytopes.

Problems are written (N, M, P): P pieces with N sides in a container with M sides, with 0 meaning a circle.
