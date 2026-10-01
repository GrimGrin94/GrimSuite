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


## v3.x — Grim Wardrobe & GrimSuite Automation
Major loadout, setup, and player-automation system inspired by the useful
functionality of Wizard's Wardrobe and selected automation features from
PersonalAssistant, rebuilt from the ground up as a GrimSuite-native system.

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

Shared GrimSuite automation layer:
- Introduce reusable automation services that can be called by Grim Wardrobe
  and later GrimSuite Inventory
- Support useful automation such as:
  - Auto-consume
  - Auto-charge
  - Auto-repair
  - Other setup-aware player maintenance actions as justified
- Keep automation rules centralized rather than implementing the same action
  independently in multiple GrimSuite systems
- Allow a saved setup to define or invoke relevant automation behavior where
  appropriate
- Keep automation opinionated and streamlined rather than recreating the full
  configuration surface of PersonalAssistant or Wizard's Wardrobe

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

The automation layer should likewise provide reusable actions without forcing
the user through a giant rules engine. Features should be shared internally
when multiple GrimSuite systems need the same behavior.

The system should remain flexible enough to work for both users with only a few
saved setups and users with large collections of highly specialized
configurations.


## v4.x — GrimSuite Inventory & Item Management
Major inventory, item-organization, and item-automation system inspired by the
useful functionality of FCO Item Saver, Auto Category, and selected
PersonalAssistant features, rebuilt from the ground up as a simplified,
GrimSuite-native system.

Core direction:
- Provide the useful item-marking/protection functionality of FCO Item Saver
  without reproducing its large configuration surface
- Provide the useful inventory categorization functionality of Auto Category
  without reproducing unnecessary complexity
- Selectively absorb useful PersonalAssistant inventory, junk, selling, banking,
  loot, repair, or restock behavior where it fits GrimSuite's goals
- Reuse the shared automation layer introduced in v3 instead of duplicating
  auto-repair, auto-charge, auto-consume, or similar actions
- Keep the system opinionated, lightweight, and easy to understand
- Integrate naturally with the GrimSuite UI framework introduced in v2
- Integrate naturally with Grim Wardrobe and other GrimSuite systems

FCO Item Saver-inspired functionality:
- Simple user-defined item markers/tags
- Useful role or purpose markers such as Damage, Tank, Healer, Sell, and Decon
- Clear visual markers on items
- Simple bottom-of-inventory marker/filter controls for showing or hiding marker
  categories when desired
- Optional protection/warning behavior for marked items
- Avoid reproducing FCO Item Saver's large settings system or hardcoding the
  author's personal marking rules

Auto Category-inspired functionality:
- Automatic inventory categorization using a streamlined category system
- Keep categories useful and predictable rather than exposing unnecessary
  configuration
- Allow categories to work naturally with GrimSuite item markers and filters
- Preserve a clean inventory presentation without requiring users to manage a
  large hierarchy of category settings

PersonalAssistant-inspired functionality:
- Selectively incorporate useful item/inventory automation
- Potential areas include:
  - Junk and sell automation
  - Banking/deposit assistance
  - Loot handling
  - Repair/restock support where appropriate
- Reuse shared GrimSuite automation primitives instead of creating separate
  implementations for actions already supported elsewhere in the suite
- Only include functionality that fits GrimSuite's simplified philosophy

Design philosophy:
GrimSuite Inventory should provide the genuinely useful parts of FCO Item Saver,
Auto Category, and selected PersonalAssistant functionality while removing
configuration overhead and duplicated systems.

The goal is not to recreate any of those addons feature-for-feature. The goal is
to create one cohesive GrimSuite item system in which marking, categorization,
inventory presentation, and useful automation can share the same underlying
data and services.

v3 establishes shared automation primitives.
v4 builds inventory and item management on top of those primitives.


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
