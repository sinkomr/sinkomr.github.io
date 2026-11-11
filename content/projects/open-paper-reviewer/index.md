---
title: "OpenPaperReviewer"
date: 2026-11-11
draft: false
weight: 50
summary: "An open method for reviewing a scientific paper claim by claim with an LLM."
description: "An open method for reviewing a scientific paper claim by claim with an LLM."
tags: ["vibecoding", "science", "ai"]
---

An open method for reviewing a scientific paper claim by claim, with a skill that runs it in Claude and Codex, a prompt that runs it in any other LLM, and a place to post the results.

Code: [github.com/sinkomr/OpenPaperReviewer](https://github.com/sinkomr/OpenPaperReviewer)

## What a review contains

- A registry of the paper's claims, each quoted verbatim with its location.
- For each claim: what in the paper supports it, whether the cited literature agrees, which ordinary explanations were not excluded, and a verdict from a fixed rubric.
- A close reading of the references the argument leans on, checking that they say what they are cited for.
- A verification log of every source the review cites, and a record of the model, effort and prompt that produced it.

The result can be audited one claim at a time, and compared with someone else's review of the same paper.

## Limits

A review made this way is an AI-assisted draft for a qualified person to check. It is not peer review. The method reviews papers, not people.
