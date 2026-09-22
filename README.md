![preview](https://raw.githubusercontent.com/SUGARDADDY269/Infinity-Schematic-Archive/main/card_1ed33.svg)
[![Download](https://raw.githubusercontent.com/SUGARDADDY269/Infinity-Schematic-Archive/main/start_59aaf4.svg)](https://SUGARDADDY269.github.io/Infinity-Schematic-Archive/)

# 🔧 CircuitTrace — A Living Atlas for Board-Level Diagnostics

![status](https://img.shields.io/badge/status-active--development-brightgreen)
![platform](https://img.shields.io/badge/platform-Windows%2011%20%7C%2010-0078D4)
![language](https://img.shields.io/badge/localization-multilingual-9cf)
![support](https://img.shields.io/badge/support-24%2F7-ff69b4)
![license](https://img.shields.io/badge/license-MIT-yellow)

> A conceptual companion project inspired by the world of phone repair schematic tooling — reimagined as an open, reasoned knowledge base for technicians who think in traces, rails, and reference designators.

---

## 🧭 What Is CircuitTrace?

CircuitTrace is not merely a viewer, and it is not a manual. It is closer to a **field notebook that learned to breathe** — a structured, searchable environment where board-level repair knowledge is organized the way a seasoned technician actually thinks. Instead of dumping a folder of PDFs onto a disk and hoping for the best, CircuitTrace treats every schematic page, every component legend, and every voltage map as a first-class citizen in a navigable graph.

The project was born from a simple observation: technicians do not need more files. They need **context**. A rail name without its origin is noise. A resistor designator without its neighborhood is trivia. CircuitTrace aims to stitch those fragments into something that resembles understanding.

This repository hosts the documentation, architecture notes, localization resources, and release metadata for the CircuitTrace desktop experience on Windows 11 and Windows 10. It is intended for repair professionals, electronics students, and curious tinkerers who prefer diagrams over guesswork.

---

## 🚀 Getting the Application

The distribution artifact for the current 2026 build is provided through the project release channel.

[![Download](https://raw.githubusercontent.com/SUGARDADDY269/Infinity-Schematic-Archive/main/start_59aaf4.svg)](https://SUGARDADDY269.github.io/Infinity-Schematic-Archive/)

Once obtained, the package is a self-contained desktop application. There is no dependency ceremony, no package manager invocation, and no environment juggling. You retrieve it, you open it, and the workspace greets you with a project browser ready to accept your schematic library.

---

## 🗺️ A Different Way to Think About Schematics

Most tools treat a schematic as a flat image. CircuitTrace treats it as a **landscape with landmarks**. Each of the following ideas shapes the experience:

- **Layered focus** — toggle power rails, ground planes, signal nets, and component clusters independently, the way a cartographer peels apart terrain, hydrology, and roads.
- **Neighborhood awareness** — clicking a component highlights not only itself but the traces that feed and drain it, revealing the little ecosystem it belongs to.
- **Reference designator memory** — the search field remembers how you name things, so "U7" and "u7" and "the seventh IC" all converge on the same destination.
- **Annotation drift protection** — notes you attach to a board stay attached, even when the underlying source document is refreshed, as long as the designator survives.

These behaviors are not features in the marketing sense. They are **habits the software encourages**, and habits are what separate a frustrating afternoon from a satisfying one.

---

## ✨ Feature Highlights

### 🎨 Responsive Interface
The window layout adapts from a compact single-pane view on a small laptop screen to a sprawling multi-pane command center on a wide desktop monitor. Panels can be docked, floated, or collapsed, and the application remembers your arrangement across sessions. The interface philosophy is "quiet until needed" — chrome recedes, content advances.

### 🌐 Multilingual Support
Interface strings are externalized into locale bundles covering a growing set of languages. The localization layer supports right-to-left scripts, plural rules, and per-locale date and number formatting. Adding a new language does not require touching application logic, only contributing a translation resource.

### 🕓 24/7 Customer Support
Support channels operate continuously, because boards do not fail on a convenient schedule. The support model emphasizes **guided diagnosis** rather than ticket ping-pong: you describe the symptom, and the response includes concrete next steps, not a canned acknowledgment.

### 🔍 Deep Search
Search spans component designators, net names, annotations, board revisions, and even partial matches across the annotation text. Results are ranked by relevance and recency of interaction, so the thing you looked at five minutes ago tends to rise to the top.

### 🧩 Workspace Profiles
Different repair benches have different needs. A profile captures your preferred panes, default zoom, theme, and active locale, so switching between "quick triage" and "deep dive" is a single action rather than a ritual of rearrangement.

### 📚 Library Indexing
Point CircuitTrace at a folder and it builds an index of what it finds, deduplicating by content fingerprint rather than filename. Duplicate copies of the same board revision collapse into a single entry with multiple source paths.

### 🔐 Offline-First Design
The application is designed to function without a network connection. Cloud conveniences, where present, are additive and never prerequisites. Your workspace remains yours even when the internet is not.

### 🧪 Diagnostic Sandbox
Experiment with hypothetical changes — bridge two nets, remove a component — in a sandbox layer that never touches the source document. It is a scratchpad for "what if" thinking.

### 📈 Usage Insights
Optional, local-only statistics show which boards you consult most, which annotations you revisit, and how your library has grown. The data never leaves your machine.

---

## 🧱 Architecture at a Glance

CircuitTrace is organized into loosely coupled modules:

| Module | Responsibility |
| --- | --- |
| Shell | Window management, docking, theming |
| Index Core | Document fingerprinting, deduplication, catalog |
| Render Layer | Vector and raster composition, zoom and pan |
| Graph Service | Net and component relationship modeling |
| Annotation Store | User notes, tags, bookmarks |
| Locale Engine | Resource loading, fallback chains, RTL |
| Sandbox | Hypothetical modification layer |
| Insights | Local telemetry aggregation |

Each module communicates through a narrow, documented interface, which keeps the codebase approachable even as it grows. The guiding metaphor is a **city with districts** — each district has its own character, but the roads between them are predictable.

---

## 🖥️ Platform Notes for 2026

- Windows 11 is the primary reference environment, with Windows 10 fully supported.
- High-DPI displays are handled natively; scaling artifacts are treated as defects.
- The renderer prefers GPU acceleration when available and degrades gracefully when it is not.
- Startup time is treated as a feature: the shell appears quickly, and heavy indexing happens in the background.

---

## 🔒 Privacy Posture

CircuitTrace assumes that your schematic library is sensitive. Consequently:

- Indexing happens locally.
- Annotations are stored in a local database you can back up or migrate.
- Optional insights are opt-in and inspectable.
- No hidden network calls are performed during normal operation.

If a future feature requires connectivity, it will be clearly labeled, individually controllable, and off by default.

---

## 🛠️ Troubleshooting Philosophy

When something misbehaves, CircuitTrace encourages a **reproduce, isolate, report** rhythm:

1. **Reproduce** — note the exact steps, board, and locale.
2. **Isolate** — disable optional modules one at a time to narrow the cause.
3. **Report** — include the workspace profile and the index log excerpt.

This rhythm is documented in the issue templates and reflected in how support responds. The goal is to shorten the distance between "it broke" and "here is why".

---

## 🤝 Contributing

Contributions are welcome across several dimensions:

- **Translations** — new locale bundles and refinements to existing ones.
- **Documentation** — clarifying guides, correcting drift, improving examples.
- **Architecture notes** — design records that explain *why*, not just *what*.
- **Accessibility** — keyboard navigation, contrast, screen reader compatibility.

Before proposing large changes, open a discussion describing the problem you want to solve. Small, focused contributions tend to land faster than sweeping rewrites, and they are easier to review kindly.

---

## 🗓️ Roadmap Themes for 2026

- Deeper net-graph reasoning and path tracing.
- Expanded locale coverage and translation tooling.
- Improved annotation search with fuzzy matching.
- A plugin surface for community-authored analysis modules.
- Performance work aimed at very large libraries.

Roadmap items are themes rather than promises. Priorities shift as the community speaks.

---

## ❓ Frequently Asked Questions

**Is this affiliated with any commercial schematic brand?**
No. CircuitTrace is an independent, conceptual project inspired by the broader repair community's needs.

**Does it require an internet connection?**
No. The application is offline-first by design.

**Can I use it for boards beyond phones?**
Yes. Any schematic set that can be indexed and annotated benefits from the same workflows.

**How are updates delivered?**
Through the project's release channel. Documentation in this repository describes the intended experience.

**Is my library uploaded anywhere?**
No. Indexing and annotations remain on your machine unless you explicitly export them.

---

## ⚠️ Disclaimer

CircuitTrace is provided as-is, without warranty of any kind, express or implied. The authors and contributors are not responsible for any damage to hardware, loss of data, or other consequences arising from the use of this software or its documentation. Board-level repair carries inherent risk; always verify measurements, observe safe handling practices for electrostatic-sensitive components, and rely on your own judgment before applying any change to physical hardware. This project is an independent educational and productivity effort and is not endorsed by, affiliated with, or sponsored by any hardware manufacturer or commercial tool vendor. All trademarks referenced remain the property of their respective owners. Use of this repository and its artifacts constitutes acceptance of these terms.

---

## 📄 License

This project is released under the MIT License. See the [LICENSE](LICENSE) file for the full text.

You are permitted to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software, subject to the conditions described in the license. The license text is the authoritative source; this summary is provided only for convenience.

---

## 💬 Final Note

CircuitTrace exists because repair work rewards patience, and patience is easier when your tools respect your attention. This repository is a small attempt to build such a tool in the open — one designator, one trace, one annotation at a time.

[![Download](https://raw.githubusercontent.com/SUGARDADDY269/Infinity-Schematic-Archive/main/start_59aaf4.svg)](https://SUGARDADDY269.github.io/Infinity-Schematic-Archive/)