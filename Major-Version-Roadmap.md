# GrimSuite — Major Version Roadmap

## Purpose
This document tracks the long-term direction of GrimSuite at the major-version
level. It focuses on major systems and architectural milestones rather than
individual bug fixes, polish items, or minor feature work.

Detailed work for a specific version should be maintained in that version's
separate development planning document.


## Version Philosophy
GrimSuite is designed to remain lightweight by selectively rebuilding the
functionality the author actually wants from multiple existing ESO addons,
while leaving out unwanted features and unnecessary complexity.

Major versions represent meaningful changes in GrimSuite's capabilities,
architecture, or overall customization experience.


## v1.x — Foundation
Build out and stabilize the core GrimSuite combat experience.

Major areas:
- Custom Action Bar
- Resource Bars
- GCD tracking
- Delay / weaving tracking
- Ultimate tracking
- Class mechanics
- Stack tracking
- Lightweight combat information
- Reliability and performance refinement

Status:
- In active development


## v2.x — GrimSuite UI Framework
Major customization and UI architecture overhaul.

Goals:
- Develop a custom GrimSuite settings framework
- Replace LibAddonMenu as the foundation for GrimSuite's own settings UI
- Keep each major GrimSuite system in its own intuitive settings section
- Provide a unified custom control system
- Introduce a visual UI customization / edit mode
- Allow GrimSuite UI elements to be moved and customized
- Allow selected vanilla ESO UI elements to be repositioned
- Add grid snapping and alignment
- Add UI scaling controls where appropriate
- Persist UI positions and layout settings
- Handle resolution and ESO UI-scale changes reliably
- Provide reset/default layout functionality

Design philosophy:
The UI framework should make GrimSuite easier to customize without turning
the settings menu into one enormous configuration dump. Each major system
should remain independently understandable and configurable, while the
underlying UI framework provides consistent positioning, controls, and
customization behavior.

Architecture direction:
The initial framework should be built internally as part of GrimSuite rather
than prematurely extracted into a standalone library. If the framework later
proves useful as a general-purpose ESO UI framework, it may be extracted into
a separate library in a future version.


## v3.x — Grim Wardrobe
Major loadout and organization system inspired by the useful functionality
of Wizard's Wardrobe, rebuilt from the ground up as a GrimSuite-native system.

Core concept:
Grim Wardrobe uses a simple three-level organization model:

    Tab → Page → Setup

Tabs are broad user-defined collections. Pages are user-created workspaces
inside a tab. Setups are the individual configurations saved within a page.

Goals:
- Provide easy-to-click top-level tabs
- Allow users to create as few or as many tabs as they need
- Allow users to create as few or as many pages within each tab as they need
- Keep the left side of the interface dedicated to saved setup pages
- Display the setups belonging to the currently selected page in the main area
- Allow users to organize pages and setups however they prefer
- Avoid forcing a rigid ESO-content hierarchy or predefined organizational
  structure
- Rebuild the useful Wizard's Wardrobe-style functionality within GrimSuite's
  own architecture and UI framework
- Integrate naturally with the GrimSuite UI framework introduced in v2

Example organization:

    TRIALS
        Monday vDSR Core
        Tuesday vLC Core
        Wednesday vRG Prog

    DUNGEONS
        Veteran DPS
        Tank
        Healer

    MISC
        Solo
        PvP
        Parsing

Within a selected page, users can create whatever setups make sense for them,
for example:

    Setup 1 — Trash 1.1 Nuke
    Setup 2 — Trash 1.2 + 1.3 Sul-Xan
    Setup 3 — Boss Pre-Buff
    Setup 4 — Boss Setup

Design philosophy:
Grim Wardrobe provides organizational tools without imposing an
organizational philosophy. Tabs and pages are containers chosen by the user;
GrimSuite does not dictate where a setup belongs or require users to follow a
specific trial, dungeon, boss, role, or activity hierarchy.

The system should remain flexible enough to work for both users with only a
few saved setups and users with large collections of highly specialized
configurations.


## v4.x — Future Development
Major direction to be determined.

Details will be established based on GrimSuite's needs and the direction of
the project at that time.


## v5.x — Future Development
Major direction to be determined.

Details will be established closer to development.


## v6.x — Future Development
Major direction to be determined.

Details will be established closer to development.


## Roadmap Principles
- Major versions should represent meaningful milestones, not arbitrary
  collections of minor features.
- Detailed implementation plans belong in version-specific planning files.
- Features should be purpose-built around GrimSuite's goals rather than added
  simply because another addon provides them.
- Avoid unnecessary dependencies and duplicated functionality.
- Preserve GrimSuite's lightweight philosophy as the project grows.
- New architecture should be introduced deliberately and tested before being
  treated as stable.
- Future versions remain intentionally flexible until their direction becomes
  clear.
