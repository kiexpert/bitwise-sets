# BitwiseSets

![License](https://img.shields.io/badge/license-BSLv1-blue)
![Status](https://img.shields.io/badge/status-active-success)
![Paper](https://img.shields.io/badge/paper-v18-brightgreen)
![Language](https://img.shields.io/badge/lang-C%2B%2B%20%7C%20C%23-orange)
![Author](https://img.shields.io/badge/author-Will%20Gi--il%20Kim-black)

> **"비트화된 질서 속에 세상을 담다.**
> **앞으로는… 우주까지."**
> — bitWisdomK · WillKim · 김기일
>
> *"Encode the order of this world in bits — and let BitwiseSets blaze open a new universe of algorithms."*
> — Dr. DeepToHyde, Official Endorser (GPT)

---

## About the Author

**Will Gi-il Kim (김기일)** — *bitWisdomK*

36 years of C++ and a 26-year engineering career spanning game engines, mobile UI runtimes, web platforms, and AI-driven desktop automation.

| Dimension | Detail |
|---|---|
| **Languages** | C++, C#, x86/ARM Assembly, ActionScript 3.0, Kotlin, JavaScript, Python |
| **Career span** | 36 yr C++ · 26 yr industry · CTO/Founder at 4 companies |
| **Team-fit signal** | Mentored junior co-owner of FXUI engine (now co-IP-holder via KIVILAB); set TDD culture at ProtoPie (300+ unit tests); led 64-bit engine migration team at Wonderpeople |

### Flagship Contributions

- **FXUI Real-time UI Engine** — mobile UI runtime deployed to **100 M+ consumer-electronics devices** (NTT PLALA / SHARP / JVC Kenwood / LG Electronics). Contribution of ~half the codebase legally recognised on departure; IP now co-owned via KIVILAB with mentored protege vidkidz. Original design at Digital Aria (SIMD 5–10× perf gain over reference); continued and expanded at PiaiSoft as CTO with full OpenGL ES graphics pipeline.
- **AutoLayout Engine @ ProtoPie (StudioSeed Korea)** — first complete in-house Figma-spec multi-platform layout runtime; WRAP / FILL / HUG modes, child-to-parent constraint propagation, 100× integer coordinate system; shipped to iOS, Android, Web, and Desktop. 300+ unit test TDD architecture.
- **NightWalker (Nexon) · NightmareBreaker (NetEase)** — full UE3 + Scaleform 64-bit migration lead for both global MMORPG launches at Wonderpeople. MeshCache crash deep-trace analysis; Scaleform RefCount race eliminated via lock-free solution. JIT bytecode-to-native optimisation: **7× frame-rate improvement** on target hardware.
- **KSCRIPT Server-side Script Engine** — designed and implemented from scratch at Sunny Y&K (now Playwith) in 2003: hot-reload without server restart (~10 years before Node.js), ECMA JavaScript 99%+ compatible, 3-stage optimisation, **2.5× PHP throughput**, threading built in. Powered the LemonBall game portal cross-site integration modules.
- **CrazyWWWBoard** — *de facto* standard Korean web BBS of the 1990s; deployed to Chollian, Hitel, NowNuri, NEC Japan and thousands of sites.
- **WKAppBot** — AI-driven desktop automation SDK (Windows UI Automation + Claude/GPT/Gemini integration), built 2024–present.
- **이든크루 Senior Freelance R&D (2025–2026)** — HTS Security & QA Automation: WkLeakDump (LoadLibrary-hook CRT-dbg interceptor, zero source change), secure keypad (financial-sector audit), KCMVP pipeline end-to-end automation.

---

## Philosophy — 化火華

The three characters that drive every line of code in this repository:

| Kanji | Reading | Meaning | In Practice |
|:---:|---|---|---|
| **化** | *hwa* — Transformation | Re-imagine classical data structures from a bitwise foundation, not as an afterthought. | Bitwise ordering replaces comparator-driven order — the structure itself encodes order. |
| **火** | *hwa* — Fire / Speed | Branchless paths, predictable latency, cache-line-aware layouts. | No `if`/`else` on the hot path; no rehash; no rebalancing; deterministic frame budget. |
| **華** | *hwa* — Splendor / Beauty | Elegant code that reads like a proof — minimal, ordered, inevitable. | Logical aesthetics + structural simplicity; a "gorgeous structure" that earns its complexity. |

---

## What is BitwiseSets?

**BitwiseSets** is a collection of data structures *transformed by bits* — not merely implemented with bitwise operators, but **fundamentally designed around bitwise ordering** for speed, structure, and elegance.

This repository is the home of multiple experimental and production-grade sets built on three pillars:

- **Bitwise ordering** — order emerges directly from bit patterns, not from comparators
- **Branchless traversal** — no `if`/`else` on the hot path
- **Cache-locality optimization** — compact layouts that respect the memory hierarchy

---

## Components

| Set Name | Status | Description |
|---|:---:|---|
| **`WkBitwiseSortSet`** | stable | A blazing-fast, branchless ordered set where sort order emerges *directly* from bitwise structure — no comparator function, no rebalancing. Drop-in replacement for `std::set` / `SortedSet<T>` in latency-critical paths such as game-engine event queues, real-time bidding ledgers, and trading-engine order books. |
| **`WkBitwiseStringSet`** | stable | Ultra-fast string-key set tuned for interpreters and DSLs — branchless lookup over a cache-optimized compact layout. Powers symbol tables and keyword dispatch in scripting runtimes (KSCRIPT-class workloads), and outperforms hash-based string sets on small-to-medium dictionaries common in compiler front-ends. |
| **`WkBitwiseAStar`** | planned | Bitwise-optimized pathfinding structure for grid and graph search. Targets game-AI navigation and robotics path-planning where open-set / closed-set churn dominates frame budget. |
| **`WkBitwiseMap`** | planned | Key-value storage that inherits the structural ordering of `WkBitwiseSortSet`. Designed for ordered configuration stores, time-series indices, and any workload that needs map semantics with predictable iteration order. |

---

## Features

- **Branchless traversal** — no `if`/`else` on the search path
- **Cache-friendly memory layout** — node placement respects cache-line boundaries
- **Compact & minimalistic design** — small headers, dense payloads
- **Fast insert/delete without rebalancing** — order is structural, not maintained
- **Deterministic latency** — no rehash, no rotation, no stop-the-world

---

## Documents

| Document | Description |
|---|---|
| [김기일_포트폴리오_2026.pdf](docs/김기일_포트폴리오_2026.pdf) | **Portfolio 2026 (OFFICIAL)** — comprehensive career overview: 11 flagship projects from CrazyWWWBoard (1990s web BBS) through ProtoPie AutoLayout and FXUI 100M-device engine. Primary document for recruiters. |
| [김기일_Portfolio_Algorithms_Optimization.PDF](docs/김기일_Portfolio_Algorithms_Optimization.PDF) | **Algorithms & Optimization Portfolio (2025)** — deep dives into branchless design, cache tuning, and the work behind BitwiseSets. |
| [WkBitwiseSortSet-v18.pdf](docs/WkBitwiseSortSet-v18.pdf) | **Official paper** — `WkBitwiseSortSet` v18, the canonical reference for the bitwise-ordered set. |
| [WillKim_Career_Description.txt](docs/WillKim_Career_Description.txt) | **Full career description** — 26-year engineering history in plain text. |

**Official Portfolio PDF (2026):**
[https://kiexpert.github.io/bitwise-sets/docs/김기일_포트폴리오_2026.pdf](https://kiexpert.github.io/bitwise-sets/docs/김기일_포트폴리오_2026.pdf)

---

## Official Paper (v18)

> Final version released internally at Kivilab.
> Authored by **Will Gi-il Kim** (kiexpert@naver.com).
> Co-developed with **Dr. DeepToHyde** (GPT).

[View PDF](docs/WkBitwiseSortSet-v18.pdf)

---

## License

**BitwiseSets License v1.0 (BSLv1)**

- Released for **educational and non-commercial use only** for the first **2 years** from each module's release date.
- Commercial usage is **prohibited** unless explicit written permission is granted by the author.
- After the 2-year window, commercial use is **automatically permitted** unless explicitly extended.

Full license: [LICENSE.txt](LICENSE.txt)
Contact for commercial licensing: [kiexpert@naver.com](mailto:kiexpert@naver.com)

© 2025–2026 Will Gi-il Kim (bitWisdomK)

---

## Contributions

The project is in **early but active** development.

- Collaborations and co-authorship inquiries are welcome
- Benchmarks, reference ports, and platform-specific tuning are particularly appreciated
- Whitepapers and follow-up papers are queued — stay tuned

For inquiries, open an issue or reach out at **kiexpert@naver.com**.

---

> **化火華** — Transformation · Fire · Splendor. Built with bitwise discipline.
