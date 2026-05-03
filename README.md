# BitwiseSets

![License](https://img.shields.io/badge/license-BSLv1-blue)
![Status](https://img.shields.io/badge/status-active-success)
![Paper](https://img.shields.io/badge/paper-v18-brightgreen)
![Language](https://img.shields.io/badge/lang-C%2B%2B%20%7C%20C%23-orange)
![Author](https://img.shields.io/badge/author-Will%20Gi--il%20Kim-black)

> **“비트화된 질서 속에 세상을 담다.
> 앞으로는… 우주까지.”**
> — bitWisdomK · WillKim · 김기일

> **"이 세상의 질서를 표현하는 비트.
> 비트화셋이 폭발하듯 화려하게 새로운 알고리즘 세계를 연다."**
> — Dr. DeepToHyde, 비트화셋 공식 추천인 (GPT)

---

## 👤 About the Author

**Will Gi-il Kim (김기일)** — *bitWisdomK*
30+ years of systems engineering across game engines, mobile UI runtimes, web platforms, and AI-driven desktop automation.

- **Languages mastered:** C++, C#, x86/ARM Assembly, ActionScript 3.0, Kotlin, JavaScript, Python
- **AutoLayout engine @ ProtoPie** — Figma-spec multi-platform layout runtime; constraint solver shipped to iOS, Android, Web, and Desktop
- **NightWalker (Nexon)** — Unreal Engine 3 migration lead; **MeshCache** optimization that cut draw-call cost on mobile-class hardware
- **FXUI** — mobile UI engine with **ActionScript 3.0 JIT compiler** (iOS / Android), Flash-spec runtime
- **CrazyWWWBoard** — *de facto* standard Korean web BBS of the 1990s; deployed by thousands of sites
- **KSCRIPT** — server-side DSL with real-time hot-reload; benchmarked faster than PHP under equivalent load
- **WKAppBot** — AI-driven desktop automation SDK (Windows UI Automation + Claude integration)

🔗 [Portfolio Site](https://kiexpert.github.io/bitwise-sets/) · [WKAppBot SDK](https://github.com/kiexpert/wkappbot-sdk) · [LinkedIn](https://www.linkedin.com/in/kiexpert/)

---

## 🔥 Philosophy — 化火華

The three characters that drive every line of code in this repository:

| 漢字 | Reading | Meaning | In Practice |
|:---:|---|---|---|
| **化** | *hwa* — Transformation | 비트를 통해 기존 구조를 새로운 방식으로 *화(化)*하다 | Re-imagine classical data structures from a bitwise foundation, not as an afterthought. |
| **火** | *hwa* — Fire / Speed | 분기 없는 탐색과 정렬, 메모리 접근 최적화를 통한 *불같은 성능* | Branchless paths, predictable latency, cache-line-aware layouts. |
| **華** | *hwa* — Splendor / Beauty | 논리적 미학과 구조적 단순함의 *화려한 구조체* | Elegant code that reads like a proof — minimal, ordered, inevitable. |

---

## 🧠 What is BitwiseSets?

**BitwiseSets** is a collection of data structures *transformed by bits* — not merely implemented with bitwise operators, but **fundamentally designed around bitwise ordering** for speed, structure, and elegance.

This repository is the home of multiple experimental and production-grade sets built on three pillars:

- **Bitwise ordering** — order emerges directly from bit patterns, not from comparators
- **Branchless traversal** — no `if`/`else` on the hot path
- **Cache-locality optimization** — compact layouts that respect the memory hierarchy

---

## 📦 Components

| Set Name | Status | Description |
|---|:---:|---|
| **`WkBitwiseSortSet`** | ✅ stable | A blazing-fast, branchless ordered set where sort order emerges *directly* from bitwise structure — no comparator function, no rebalancing. Drop-in replacement for `std::set` / `SortedSet<T>` in latency-critical paths such as game-engine event queues, real-time bidding ledgers, and trading-engine order books. |
| **`WkBitwiseStringSet`** | ✅ stable | Ultra-fast string-key set tuned for interpreters and DSLs — branchless lookup over a cache-optimized compact layout. Powers symbol tables and keyword dispatch in scripting runtimes (KSCRIPT-class workloads), and outperforms hash-based string sets on small-to-medium dictionaries common in compiler front-ends. |
| **`WkBitwiseAStar`** | 🛠️ planned | Bitwise-optimized pathfinding structure for grid and graph search. Targets game-AI navigation and robotics path-planning where open-set / closed-set churn dominates frame budget. |
| **`WkBitwiseMap`** | 🛠️ planned | Key-value storage that inherits the structural ordering of `WkBitwiseSortSet`. Designed for ordered configuration stores, time-series indices, and any workload that needs map semantics with predictable iteration order. |

---

## ⚙️ Features

- ✅ **Branchless traversal** — no `if`/`else` on the search path
- ✅ **Cache-friendly memory layout** — node placement respects cache-line boundaries
- ✅ **Compact & minimalistic design** — small headers, dense payloads
- ✅ **Fast insert/delete without rebalancing** — order is structural, not maintained
- ✅ **Deterministic latency** — no rehash, no rotation, no stop-the-world

---

## 📄 Documents / 문서

| Document | Description |
|---|---|
| 📘 [김기일_포트폴리오_2026.pdf](docs/김기일_포트폴리오_2026.pdf) | **Portfolio 2026** — 11 flagship projects from CrazyWWWBoard (1990s web BBS) through ProtoPie AutoLayout. Primary career overview document. |
| 📊 [김기일_Portfolio_Algorithms_Optimization.PDF](docs/김기일_Portfolio_Algorithms_Optimization.PDF) | **Algorithms & Optimization Portfolio (2025)** — deep dives into branchless design, cache tuning, and the work behind BitwiseSets. |
| 📕 [WkBitwiseSortSet-v18.pdf](docs/WkBitwiseSortSet-v18.pdf) | **Official paper** — `WkBitwiseSortSet` v18, the canonical reference for the bitwise-ordered set. |
| 📝 [WillKim_Career_Description.txt](docs/WillKim_Career_Description.txt) | **Full career description** — 30+ years of engineering history in plain text. |

---

## 📄 Official Paper (v18)

> Final version released internally at Kivilab.
> Authored by **Will Gi-il Kim** (kiexpert@kivilab.co.kr).
> Co-developed with **Dr. DeepToHyde** (GPT).

📘 [View PDF](docs/WkBitwiseSortSet-v18.pdf)

---

## 📘 License

**BitwiseSets License v1.0 (BSLv1)**

- Released for **educational and non-commercial use only** for the first **2 years** from each module's release date.
- Commercial usage is **prohibited** unless explicit written permission is granted by the author.
- After the 2-year window, commercial use is **automatically permitted** unless explicitly extended.

📄 Full license: [LICENSE.txt](LICENSE.txt)
📧 Contact for commercial licensing: [kiexpert@kivilab.co.kr](mailto:kiexpert@kivilab.co.kr)

© 2025 Will Gi-il Kim (bitWisdomK)

---

## 🙌 Contributions

The project is in **early but active** development.

- Collaborations and co-authorship inquiries are welcome
- Benchmarks, reference ports, and platform-specific tuning are particularly appreciated
- Whitepapers and follow-up papers are queued — stay tuned

For inquiries, open an issue or reach out at **kiexpert@kivilab.co.kr**.

---

> **化火華** — Transformation · Fire · Splendor. Built with bitwise discipline.
