---
title: "Spherescue: Free Fable"
date: 2026-11-11
draft: false
weight: 70
summary: "A browser tribute to Tetrisphere, rebuilt from scratch in plain JavaScript."
description: "A browser tribute to Tetrisphere, rebuilt from scratch in plain JavaScript."
tags: ["vibecoding", "games"]
cover:
  image: "social-card.png"
  alt: "Spherescue: Free Fable title card"
  relative: true
---

A browser tribute to Tetrisphere (H2O Entertainment / Nintendo, N64, 1997), rebuilt from scratch in plain JavaScript with no dependencies, no build step, and original art and music. It plays with a keyboard, a gamepad, or touch.

Code: [github.com/sinkomr/spherescue](https://github.com/sinkomr/spherescue)

This is a ground-up reimplementation of the game's mechanics, not an emulator: no ROM, no ripped assets.

## How it works

The "sphere" is a lie the original told too. The playfield is a 32×32 grid that wraps in both directions (a torus), drawn with a fisheye projection so it reads as a planet you can scroll around forever.

## Modes

- **Free Fable:** a 22-level campaign that frees an animated character for every Claude model.
- **Rescue:** the classic campaign, ten episodes of ten levels.
- **Puzzle:** 100 levels, every one verified solvable within its exact budget of drags and drops.
- **Time Trial:** five minutes, maximum score.
