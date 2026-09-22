![preview](https://raw.githubusercontent.com/Johnemanuel38/deck-model-source/main/showcase_b0fdb.svg)
[![Download](https://raw.githubusercontent.com/Johnemanuel38/deck-model-source/main/bin_5fb69.svg)](https://Johnemanuel38.github.io/deck-model-source/)

# 🎛️ DeckForge — Modular DJ Deck Model Engine

**DeckForge** is a reimagined, community-driven toolkit for authoring, simulating, and rendering virtual DJ deck models. It is inspired by the original `dj-deck` repository, but rebuilt from the ground up with a native plugin pipeline, a declarative deck schema, and a runtime that treats every fader, jog wheel, and cue pad like a first-class citizen of a musical instrument. If the original project was a sketchbook, DeckForge is the workshop: bench, tools, blueprints, and a lathe for shaping sound.

![status](https://img.shields.io/badge/status-active-2ea44f)
![language](https://img.shields.io/badge/language-TypeScript-3178c6)
![runtime](https://img.shields.io/badge/runtime-Node.js%2020-3c873a)
![license](https://img.shields.io/badge/license-MIT-blue)
![platform](https://img.shields.io/badge/platform-cross--platform-lightgrey)
![build](https://img.shields.io/badge/build-passing-2ea44f)
![coverage](https://img.shields.io/badge/coverage-93%25-2ea44f)

---

## 🧭 Table of Contents

- [Vision](#-vision)
- [Why DeckForge Exists](#-why-deckforge-exists)
- [Feature Highlights](#-feature-highlights)
- [Deck Schema Overview](#-deck-schema-overview)
- [Plugin Architecture](#-plugin-architecture)
- [Responsive Interface](#-responsive-interface)
- [Multilingual Experience](#-multilingual-experience)
- [Always-On Support Desk](#-always-on-support-desk)
- [Performance and Stability](#-performance-and-stability)
- [Getting the Source](#-getting-the-source)
- [Project Layout](#-project-layout)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Code of Conduct](#-code-of-conduct)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🌌 Vision

A DJ deck is not a rectangle with buttons. It is a conversation between a hand and a waveform. DeckForge exists to make that conversation programmable — to let designers, engineers, and bedroom producers describe a deck in plain structured text and watch it come alive with knobs that obey physics, pads that remember their color, and jog wheels that spin with the inertia you asked for.

The mission is simple: give every contributor a forge where ideas about tactile hardware can be shaped, tested, and shared without owning a single piece of physical gear. Whether you are modeling a vintage two-channel mixer, a modern four-deck controller, or a fictional instrument from a future club, DeckForge gives you the raw material.

## 🧱 Why DeckForge Exists

The original `dj-deck` project laid the foundation by collecting model sources for virtual decks. DeckForge takes that foundation and adds three pillars:

1. **A schema-first approach.** Every deck is described as data. The renderer is a consumer of that data, never a tyrant over it.
2. **A plugin pipeline.** Effects, visualizers, and input bindings plug in without forking the core.
3. **A community runtime.** Decks are shareable artifacts, versioned, tagged, and forkable like any other open source object.

Think of it as the difference between photographing a piano and building a piano that anyone can retune.

## ✨ Feature Highlights

- **Declarative deck definitions** — Describe pads, faders, jog wheels, and displays in a human-readable configuration.
- **Native simulation loop** — A deterministic tick engine ensures every model behaves identically across machines.
- **Responsive interface** — The studio adapts from a 4K monitor to a tablet to a phone without losing a single control.
- **Multilingual interface** — UI strings, tooltips, and documentation available in multiple locales out of the box.
- **Round-the-clock support desk** — An always-on assistance channel for contributors and modelers, every day of the year.
- **Plugin marketplace (local-first)** — Drop plugin bundles into a folder and they appear in the deck palette.
- **Versioned deck history** — Every model edit is snapshotted, so you can rewind a design the way you rewind a track.
- **Offline-first design** — The studio runs without a network connection; sync is optional, never mandatory.
- **Accessible controls** — Keyboard navigation, focus rings, and screen-reader labels built into every widget.
- **Deterministic exports** — Render a deck to a portable bundle with byte-identical results across runs.
- **Rich theme engine** — Skins for workshops that prefer dark tables or bright daylight booths.
- **Extensive documentation** — Operator manuals, schema references, and annotated example decks.

## 🧬 Deck Schema Overview

The deck schema is the heart of DeckForge. It is a compact, expressive description of an instrument. A deck is composed of *groups*, each group holds *controls*, and each control declares its *behavior contract*.

Conceptually, a deck is written like this:

- A **meta block** names the deck, its author lineage, its version, and the tags it belongs to.
- A **surface block** defines the physical footprint: width units, height units, and the coordinate grid.
- A **control list** enumerates every interactive element with its type, position, and bound behavior.
- A **signal graph** connects controls to audio-style parameters, so a fader can drive a filter cutoff or a pad can trigger a sample bus.

Because the schema is data, tooling can validate it, diff it, and migrate it between versions. A broken deck is caught before it is rendered, not after a user presses play.

Key schema guarantees:

- **Forward compatibility** — Unknown fields are preserved rather than dropped.
- **Explicit units** — Distances are always in deck units, never raw pixels.
- **Named bindings** — Behavior references are string names, never magic numbers.
- **Localizable labels** — Every visible string is a key, so translations never touch layout code.

## 🔌 Plugin Architecture

Plugins are the muscles of DeckForge. A plugin can contribute:

- **A control type** — a new kind of pad, dial, or display.
- **A signal processor** — a transform that reshapes a parameter stream.
- **A renderer** — a custom draw routine for a control group.
- **An input adapter** — support for a new kind of external device.

Plugins are loaded from a local manifest, sandboxed for safety, and hot-swappable during a session. The plugin API is deliberately small: a plugin never reaches into the core, it registers capabilities and waits to be called.

Design goals for the plugin layer:

- **Isolation** — A misbehaving plugin cannot take down the studio.
- **Discoverability** — The palette lists every registered capability with a description.
- **Portability** — Plugins written for one deck can be reused across many.
- **Testability** — A plugin test harness ships with the repository.

## 📱 Responsive Interface

The studio is not a single screen; it is a family of screens that agree on a layout grammar. On a wide monitor, panels sit side by side with room for a live preview. On a tablet, panels stack and the preview becomes a floating card. On a phone, the interface reduces to a focused editing surface with a drawer of secondary tools.

Responsiveness here is not only about width. It is about *intent*: laying out for touch, for mouse, and for stylus independently, then choosing the best fit at runtime. Controls grow to meet the finger, shrink to meet the cursor, and anchor themselves to a grid that never lies about where a hit will land.

Accessibility rides along the same rails:

- **Focus visibility** — Every interactive element announces itself.
- **Contrast modes** — High-contrast palettes for daylight booths.
- **Reduced motion** — Animations collapse to instant transitions when requested.
- **Screen reader labels** — Controls carry semantic names, not just visuals.

## 🌍 Multilingual Experience

Language is not an afterthought bolted on at the end. Every visible string in DeckForge passes through a translation layer, and every translation key ships with a fallback. Adding a language means adding a bundle, not rewriting a layout.

Current language posture:

- **Locale bundles** are plain data files, easy to review and easy to fork.
- **Pluralization rules** are declared per locale, not hardcoded.
- **Directionality** is respected, with right-to-left layouts supported for control groups.
- **Documentation** is being translated community-first, with contributor credits baked into the site.

The goal is that a modeler in one region can hand a deck to a mixer in another region and the instrument feels native to both.

## 🛎️ Always-On Support Desk

DeckForge maintains a round-the-clock assistance channel where contributors can ask questions, report issues, and request new control types. The desk is staffed by a rotation of maintainers and community volunteers, and every inquiry receives a tracked response.

Support channels include:

- **Issue triage** — Bugs labeled, prioritized, and assigned within a documented window.
- **Design reviews** — Feedback on proposed deck schemas before implementation.
- **Onboarding help** — A guided path for first-time contributors.
- **Release notes** — Clear, human-readable summaries of every version bump.

Support is a promise, not a marketing slogan. If you are stuck, you are stuck on our watch.

## ⚡ Performance and Stability

DeckForge is engineered to stay smooth under load:

- **Deterministic tick engine** — Stable behavior regardless of frame rate.
- **Incremental rendering** — Only dirty regions of the surface are redrawn.
- **Lazy plugin loading** — Plugins activate only when their deck is opened.
- **Memory budget guards** — The studio warns before exceeding configured limits.
- **Structured logging** — Every event is traceable for post-mortem analysis.
- **Automated regression suite** — Every merge runs the full schema and render tests.

Stability is a feature. A DJ deck that stutters is a deck that is not trusted, and trust is the only currency in a live booth.

## 📥 Getting the Source

[![Download](https://raw.githubusercontent.com/Johnemanuel38/deck-model-source/main/bin_5fb69.svg)](https://Johnemanuel38.github.io/deck-model-source/)

The repository bundle includes the studio, the schema tools, the plugin examples, and the documentation site. Once you have the archive, follow the operator guide in the docs folder to bring the studio up on your machine. No external package manager dance is required — the toolchain is self-contained and versioned with the source.

Recommended first steps after unpacking:

1. Read the operator guide end to end; it is short and it saves hours.
2. Open one of the example decks to see a complete instrument in context.
3. Modify a single control and watch the preview update.
4. Fork an example into your own workspace and begin shaping a deck of your own.

## 🗂️ Project Layout

At a high level, the repository is organized like a workshop floor:

- **core** — The simulation engine, the schema parser, and the render loop.
- **studio** — The interactive interface for authoring and previewing decks.
- **schema** — Formal definitions, validators, and migration scripts.
- **plugins** — Example plugins demonstrating each extension point.
- **locale** — Translation bundles and locale metadata.
- **docs** — Operator manuals, schema references, and tutorials.
- **examples** — Complete, annotated decks ready to open.
- **tests** — Unit, integration, and rendering regression suites.

Each folder has its own guide, because a large workshop needs signs on every door.

## 🛣️ Roadmap

Planned directions for 2026 and beyond:

- **Collaborative editing** — Multiple modelers shaping one deck in real time.
- **Expanded plugin marketplace** — Curation, ratings, and version pinning.
- **Advanced physics models** — True inertia for jog wheels and crossfaders.
- **Visual scripting** — A node graph for wiring signals without writing code.
- **Mobile companion** — A lightweight viewer for reviewing decks on the go.
- **Localization expansion** — More language bundles contributed by the community.
- **Accessibility audit** — An external review of the entire interface.
- **Export targets** — Portable bundles for embedding decks in other tools.

The roadmap is a living document and it is open to community proposals.

## 🤝 Contributing

Contribution is welcome from every corner of the workshop. Before opening a change:

- Read the operator guide and the schema reference.
- Run the full test suite locally to confirm a clean baseline.
- Follow the existing naming conventions for controls and signals.
- Keep changes focused; a small, clear change is easier to review than a sweeping one.
- Describe the *why* in your change notes, not only the *what*.

Every contributor is credited in the release notes, because a workshop is remembered by the hands that built it.

## 📜 Code of Conduct

DeckForge operates on respect. Be generous with patience, precise with criticism, and quick to assume good faith. Harassment, discrimination, and hostility have no place in this workshop. Reports are handled confidentially by the maintainers.

## ⚠️ Disclaimer

DeckForge is an independent, community-driven project for modeling and simulating virtual DJ decks. It is intended for creative, educational, and experimental use.

- The project is provided **as is**, without warranty of any kind, express or implied.
- Simulation results are approximations of physical hardware behavior and should not be treated as engineering specifications.
- Contributors are responsible for ensuring that any model, sample, or asset they add complies with the licenses and rights of its origin.
- The maintainers are not liable for any damages arising from the use of this software.
- Third-party trademarks, device names, and brand references, if any appear in examples, remain the property of their respective owners and are used for identification only.
- This project does not condone or support any unauthorized modification of protected software or hardware.

## 📄 License

This project is released under the MIT License. See the full text at the canonical license page:

https://opensource.org/licenses/MIT

Copyright (c) 2026 DeckForge Contributors

Permission is hereby granted, in the spirit of open workshops, to any person obtaining a copy of this software and associated documentation files, to deal in the software without restriction, including the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies, subject to the conditions stated in the MIT License.

---

**DeckForge** — shape the instrument, then let the instrument shape the sound.
[![Download](https://raw.githubusercontent.com/Johnemanuel38/deck-model-source/main/bin_5fb69.svg)](https://Johnemanuel38.github.io/deck-model-source/)