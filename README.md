# Data-Oriented Integrity Architecture PoC

## Overview

This repository contains a **non-operational, educational proof-of-concept**
demonstrating an **architectural limitation** common to applications that rely on
local integrity checks combined with watchdog-style enforcement.

The purpose of this project is to support:
- Security architecture discussion
- Defensive design reviews
- Academic collaboration

This repository does **not** contain exploits, bypass techniques, or tooling.

---

## Core Idea

Many protected applications follow this high-level pattern:

1. Perform an integrity or environment check
2. Store the result as program state
3. Make an enforcement decision based on that state
4. Preserve code integrity and control flow

This PoC illustrates a key design reality:

> When enforcement depends on mutable program state, the *decision data* becomes
> a critical dependency—even when code integrity is intact.

This is a **design constraint**, not a vulnerability in isolation.

---

## What This Repository Demonstrates

- Separation of integrity *measurement* and *enforcement*
- Decision gates implemented via ordinary program logic
- Reliance on transient data rather than immutable code
- Why this pattern exists in real systems

The code is intentionally simple and self-contained.

---

## What This Repository Explicitly Does NOT Include

- No real applications or services
- No platform- or vendor-specific APIs
- No hooking, patching, or interception logic
- No instruction on altering runtime behavior
- No offsets, breakpoints, or timing strategies
- No discussion of evasion or persistence

Any operational details are **deliberately omitted**.

---

## Simplified Architectural Flow

