# GrimSuite

**GrimSuite** is a lightweight, purpose-built ESO combat UI addon focused on useful information, clean customization, and minimal overhead.

The project began with a simple idea: rebuild the parts of multiple popular ESO addons that are actually useful to me, leave out the features and complexity I do not need, and bring the result together into a single cohesive addon.

## What GrimSuite Is

GrimSuite is being developed as a focused alternative to running many separate addons for overlapping pieces of combat information.

Rather than reproducing every feature of an existing addon, GrimSuite selectively rebuilds the functionality that fits its design goals. This allows related systems to share infrastructure instead of maintaining multiple independent implementations.

Current major areas include:

- Custom action bar
- Health, Magicka, and Stamina resource bars
- Shield tracking
- GCD tracking
- Delay / weaving tracking
- Ultimate tracking
- Class-specific mechanic tracking
- Stack tracking
- Lightweight combat information

The project is intentionally opinionated: less UI clutter, less unnecessary configuration, and more useful information.

## Design Philosophy

### Lightweight by Design

“Lightweight” does not mean “few features.”

GrimSuite is intended to provide useful functionality that might otherwise require multiple separate addons, while avoiding unwanted features, duplicated systems, and unnecessary complexity.

The goal is to maximize useful functionality while minimizing the amount of code and overhead required to provide it.

### Purpose-Built

Features are designed specifically around the way GrimSuite is intended to be used rather than copied wholesale from other addons.

### User-Controlled

Customization should be straightforward and intuitive. Major systems should remain independently understandable rather than being buried in one enormous settings menu.

## Development Roadmap

GrimSuite is actively developed through version-specific planning documents.

For the long-term direction of the project, see:

**[Major Version Roadmap](Major-Version-Roadmap.md)**

The major roadmap currently defines:

- **v1.x — Foundation**
- **v2.x — GrimSuite UI Framework**
- **v3.x — Grim Wardrobe**
- **v4.x–v6.x — Future development**

Detailed work for individual releases is maintained separately so the major roadmap can remain focused on larger architectural milestones.

## Version Roadmap

### v1.x — Foundation

Build and stabilize the core GrimSuite combat experience.

### v2.x — GrimSuite UI Framework

A major customization and UI architecture overhaul, including a custom GrimSuite settings framework, visual UI edit mode, movable GrimSuite elements, and support for repositioning selected vanilla ESO UI elements.

### v3.x — Grim Wardrobe

A GrimSuite-native loadout and organization system inspired by the useful functionality of Wizard's Wardrobe, rebuilt from the ground up around the GrimSuite UI framework.

The core organizational model is:

**Tab → Page → Setup**

Tabs and pages are user-defined. GrimSuite provides organization tools without forcing users into a rigid hierarchy.

## Development

The project follows a deliberate development cycle:

**Development → Testing → Known-good checkpoint → Refactoring → Retesting → Release**

Changes are tested in ESO before being considered stable.

The repository's Git history is used to preserve meaningful development milestones and release history.

## AI-Assisted Development

GrimSuite is developed collaboratively with AI assistance. The author actively participates in the coding process, directs implementation, reviews and modifies generated code, and extensively tests and debugs the addon in ESO.

AI is used as a development partner for coding, troubleshooting, refactoring, and brainstorming.

All changes are tested and validated in-game by the author before being considered part of GrimSuite. The final code, implementation, and maintenance remain the author's responsibility.

## Project Status

**Current major version:** v1.x  
**Current development:** v1.3.x  
**Long-term direction:** v2.x UI Framework → v3.x Grim Wardrobe

GrimSuite is an active development project. Features, architecture, and future roadmap items may evolve as the addon is tested and refined.
