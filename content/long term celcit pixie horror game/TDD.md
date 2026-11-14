---
uid: 4um2r409vhplswwy95ul8
title: Technical Design Document
modified: Saturday, November 14th 2026, 7:26 pm
created: Thursday, October 8th 2026, 2:31 pm
author:
  - "[Dean](https://deanlemans.github.io/)"
  - Mink
---

# Technical Design Document

> see also: [FDD](<./FDD.md>)

> [!NOTE] foreword
> this is for a 1 person programmer, maybe in the future more, but for now that is the constraint

Godot 4.8
	- [GDScript Formatter 0.27.0](https://github.com/GDQuest/GDScript-formatter/releases/tag/0.27.0)
	- [Antz's Debug Menu 1.3.0](https://github.com/antzGames/Antz-Debug-Menu/releases/tag/v1.3.0)
	- [LimboConsole 0.8.0](https://github.com/limbonaut/limbo_console/releases/tag/v0.8.0)
	- [Dialogue Manager 4.2.0](https://github.com/nathanhoad/godot_dialogue_manager/releases/tag/v4.2.0)
	- [health, hitboxes and hitscans 5.0.4](https://github.com/cluttered-code/godot-health-hitbox-hurtbox/releases/tag/v5.0.4)
	- [Godot State Charts 0.22.5](https://github.com/derkork/godot-statecharts/releases/tag/v0.22.5)
	- [Maaack's Game Template Addon 1.7.1](https://github.com/Maaack/Godot-Game-Template/releases/tag/v1.7.1)
		- [Godot-UI-Sound-Controller 1.7.1](https://github.com/Maaack/Godot-UI-Sound-Controller/releases/tag/v1.7.1)
		- [Godot-Scene-Loader 1.7.1](https://github.com/Maaack/Godot-Scene-Loader/releases/tag/v1.7.1)
		- [Godot-Music-Controller 1.7.1](https://github.com/Maaack/Godot-Music-Controller/releases/tag/v1.7.1)
	- [Script-IDE 2.2.5](https://github.com/Maran23/script-ide/releases/tag/2.2.5)
	- [sound manager 2.6.2](https://github.com/nathanhoad/godot_sound_manager/releases/tag/v2.6.2)
	- [phantom camera 0.11.0.4](https://github.com/ramokz/phantom-camera/releases/tag/v0.11.0.4)
	- [SpacetimeDB Client SDK 0.3.2](https://github.com/flametime/Godot-SpacetimeDB-SDK/releases/tag/v0.3.2)
	- [Plugin Updater 0.5.1](https://github.com/Maaack/Godot-Plugin-Updater/releases/tag/v0.5.1)
	- [Project Time Tracker 3.0.1](https://github.com/Fifut/project-time-tracker/releases/tag/v3.0.1)

## CORE Programming Rules
GAME DEV CORE PROGRAMMING AND CODING PRINCIPLES
- main design pattern (but not only one present): godot flavored component-based architecture
	- but its not perfect, consider this:
	- components adds a good bit of complexity over simply making a class, and communication between components becomes more challenging. making everything components would be stupid, some things can just be classes or such.
	- over-application can be solved with the golden rule, everything in balance. even the rule itself. (applies to all the rules)
- Less code is a feature.
- if considering abstraction, also consider deletion or merging scripts into one.
	- First of all trying to keep it simple, but secondly when adding complexity how much benefit is coming from that complexity? is this abstraction earning its keep?
- Fail loudly. A bad item ID should call `push_error`, and `_on_setup()` should report missing wiring. Never continue silently.
- Clear, descriptive names over shortened or abbreviated names. (mostly relevant for functions, but not only) see FUNCTION NAMING below.
- Signals up, methods down.
- Event driven. react to signals, dont poll every frame when signal exists.
- Never nester. early return / guard clause instead of nested ifs.
- small, composable scenes, not a framework layered on top.
- Separate machine-independent and machine-dependent code. That’s what makes the code hackable, not cleverness. `PlatformerMovementBase`, with its abstract 2D and 3D functions, is an example.
- Use narrow interfaces where change is expected. `PlayerApi` (`give_item`, `has_item`, `set_level_flag`, `set_fact`, etc.) hides components, so you can rewrite them without touching dialogue files.
- Make code easy to grep. Use one class per file, name file after class, and use stable IDs (item ID is the file name).
- Write the minimum. Add a narrow interface only where you already expect change.
- if its not necessary, make sure not to handroll our own logic, use godots inbuilt logic and functions and methods instead.
- AUDIT, REVIEW, REPEAT: make sure old code is up to date with current codebase/code conventions, design patterns could have changed, things evolve and change. make sure stuff doesn't get left behind
- GENERAL:
	- keep code like netbsd; easy to inspect, modify, and extend. and like
	- openbsd; simple, clear, and consistent.
	- suckless: Clarity, frugality and small enough for one person to read and rewrite.

FUNCTION NAMING
- Descriptive names. Longer is good when clearer.
	- add() -> add_inventory_item()
- Full words.
	- _read_move() -> _get_movement_input()
- Name the actual behavior.
	- _find_closest() -> _find_nearest_interactable()
- Add system/target/result when it clarifies.
	- get_ratio() -> get_current_sanity_ratio()
- Readable at call site.
	- run(by) -> execute_interaction_for_actor(actor)
- Related names consistent.
	- pause() -> pause_sanity_drain(), unpause() -> resume_sanity_drain()
- Context from class alone isn't always enough.
	- set_value() -> set_current_sanity_value()
- No filler words.
	- get_frame() stays get_frame() when it returns InputFrame.
- Rename declarations, overrides, call sites together.
- Preserve Godot-defined method names.

## Rules for Documentation and Comments
GAME DEV DOCUMENTATION AND COMMENT PRINCIPLES

- Comment the surprising, not the obvious with inline comments.
- be direct and concise, skip the word "the" and "a" and "'" even if it's less pretty (keeps things more direct)
- Explain why, not what.
- Code shows what it does. Comments show reasoning, decisions, and/or constraints.
- Code documents implementation; comments document intent.
	- If intent changes, update comment.
- Don't duplicate code in comments.
	- If a comment just restates code, delete it.
- Use two comment types, two jobs.
	- Double-hash doc comments for public API docs (parsed by editor and shown
	  in class reference).
	- Single-hash comments for inline implementation notes
	  (ignored by documentation system).

API DOCS
Use double-hash doc comments for public functions, signals, `@export` variables,
`class_name`, and modules. A doc comment must sit immediately above member it
documents. Members starting with `_` are treated as private and skipped by docs.

- `#` = why. `##` = public API contract (shows in Inspector). Don't mix them.
- Document the contract: what it does, parameters,
  return values, and side effects.
- Link related symbols with [member health], [method take_damage], [signal died].
  These become clickable in editor.
- Add a short usage example for non-trivial functions.

Example:

> Emitted when the Ball Reaches Peak Height.
> @experimental: Timing May Change.
	signal ball_peak_changed(in_peak: bool)

INLINE COMMENTS
Use single-hash comments inside function bodies.
- Comment the surprising, not the obvious.
	- Good for: engine workarounds, ordering requirements, magic numbers,
	  and warnings like "changing this breaks saves".
- Write for future fixer and extender.
	- Explain invariants, pitfalls, and non-obvious choices.
- Keep them short.
	- Long explanations belong in API docs or design docs.

Example:

> Peak Entry Still Fires Legacy Max-speed Event Cadence Latches On.
> func _on_ball_peak_changed(in_peak: bool) -> void:

HYGIENE
- Fix code, not comments.
	- Don't use comments to patch bad names or messy GDScript. Rewrite it.
- Update outdated doc comments.
	- Editor hover and class reference will show stale docs. An incorrect
	  comment is worse than no comment.
- Be consistent.
	- Example: capital letter, end with period, put comments above code.

## System Architecture

Game (for now) is divided into these main components:

- Components (extend `Component`, wired by body, never looked up themselves)
	- Input (`InputComponent`, `PlayerInputComponent`, `InputFrame`)
	- Facing (`FacingComponent`)
	- Movement (`PlatformerMovementBase` > `Movement3DComponent` / `Movement2DComponent`)
		- Walk, run, jump, dash, crouch, wall slide
		- Ground, Air, Wall Slide, Dash and Crouch states, driven by Godot State Charts
		- `MovementProfile` resource holding all tunable values (speed, jump, dash, etc.)
		- 3D player uses `AnimatedSprite3D` (2D-style sprites on 3D plane); 2D twin `Movement2DComponent` for pure 2D player
	- Animation (`AnimationComponent`)
	- Interaction (`InteractionComponent`, finds and runs closest `InteractableThing`)
	- Inventory (`InventoryComponent`)
	- Sanity (`SanityComponent`, `SanityVisualsComponent`)
	- Net sync (`NetSyncComponent`)
- Bodies (own and wire components)
	- `PlayerBody` (3D), `PlayerBody2D` (2D)
	- `PlayerSpawner` places player in level (a `Marker3D`)
- Player API
	- `PlayerApi` is one way dialogue, interactables and debug commands talk to player, 2D or 3D
- Dialogue
	- Talk to NPCs with Dialogue Manager
- Items and Quests
	- `ItemData` and `QuestData` resources, one `.tres` each, id is file name
	- Quest progress is fact in `GameState`
- Animations
	- `Animations` name constants, driven by movement signals
- Game State
	- `GameState` and `LevelState` resources
	- Level progress, checkpoints, per level flags and global facts
	- Saving through `GlobalState`
- Level Management
	- `LevelManager` extended with state saving (`level_and_state_manager.gd`)
	- `InteractableThing` for things player interacts with (optional `persistent_id` keeps `free_after` pickups gone after reload)
	- `Sanctuary` (Area3D pauses sanity drain while player is inside)
- Multiplayer
	- `Net` autoload with SpacetimeDB, server module is in `server/`
	- `RemotePlayer` / `RemotePlayer2D` show other players, scene picked by local body dimension
	- Offline should still works if connection fails(why tf would it not? some idiots bad desin probbly, or in case of big companies; Greed)
- Debug
	- `DebugCommands` adds commands to LimboConsole
	- `StateEvents` holds event names `PlatformerMovementBase` sends to state chart.

### Component Wiring

Every component extends `Component`. Two hooks run in order:

1. `_on_ready` runs inside `Node._ready`. Dependencies already set, but sibling `_ready`s may not be.
2. `_on_setup` runs deferred (idle time after all `_ready`s). Check dependencies here with `_require_dependencies({ "label": value })`, which collects every null into a single error and returns true/false so component can bail out.

Body (`PlayerBody` / `PlayerBody2D`) is only place dependencies are assigned. It runs in `_enter_tree`, finds every component and the sprite with `Component.find_descendant_of_type(self, Type)`, and assigns the typed fields before hooks run. Components never look each other up. Adding component is two steps: add node to scene, wire it in body. Missing wiring is reported once, in `_on_setup`, by every component that depends on it.

Components communicate through signals (`jumped`, `landed`, `dashed`, `flipped`, etc.). Input is read once per frame into an `InputFrame`, so movement never reads `Input` directly. `Component.find_descendant_of_type()` exists only for body's own wiring. It is not a service locator.
### Technical Stack

Godot 4.8, GDScript, Compatibility renderer. Exported for desktop and web.

Server is a SpacetimeDB module in Rust, in `server/`. Schema changes regenerate client SDK types (`SpacetimeDB.Faerie`, `FaerieNetPlayer`); only `Net` reads them.

Autoloads: `GlobalState`, `DialogueManager`, `Net`, `DebugCommands`, `LimboConsole`. Nothing else is singleton. Order matters where one calls another (`GlobalState` before anything that calls `GlobalState.save()`).

Addons by role:
- Movement states; Godot State Charts
- Dialogue and choices; Dialogue Manager
- Level loading, saving, scene loading, music and UI sound Maaack's Game Template (`GlobalState`, `LevelManager`, `SceneLoader`, `MusicController`, `UISoundController`)
- Camera; Phantom Camera (`PlayerSpawner.camera`)
- Debug; LimboConsole (via `DebugCommands`), Antz's Debug Menu
- Sound; sound manager
- Multiplayer; SpacetimeDB Client SDK
- Tool stuff; Script-IDE, GDScript Formatter, Project Time Tracker

`PlayerApi` is not an autoload. `PlayerBody`/`PlayerBody2D` create it in `_enter_tree`, store it on body, and expose it through `PlayerApi.find_local_player_api()`. Dialogue and `InteractableThing` get it as extra game state, never as a global.

**Deployment**

Game will be exported from Godot as build for as much platforms as reasonably possible

## Technical Specifications

Game makes use of Godot's built-in API (`CharacterBody3D`, `Resource`, signals) plus addons listed above.

- Movement values are tweaked in a `MovementProfile` resource, not in code.
- State chart's state nodes must be named `%Ground`, `%Air`, `%WallSlide`, `%Dash` and `%Crouch`. Chart itself is injected.
- New input source is made by extending `InputComponent` and overriding `_build_frame()`.
- 2D version is made by extending `PlatformerMovementBase` and implementing its abstract functions.
- New component extends `Component`, goes in body scene and gets wired in body.
- New item or quest is a `.tres` in `scenes/items/` or `scenes/quests/`.
- New interactable thing is `Node3D` scene with `InteractableThing` script on root. Zone `Area3D` is built in `_ready`, player sensor detects.

**Performance**

- Game should not lag or drop below 45 FPS on web. absolute rule, if we keep at this then other platform are likely to be optimised as well

**Platform**

- For now just use Godot compatibility renderer, if need more advanced features we will use that then, not sooner.

### User Acceptance Test (UAT)

Check whether game meets all functional, design and code quality requirements from perspective of end user.

- [ ] Player can walk and run
- [ ] Player can jump, with variable height and a double jump
- [ ] Player can wall slide and wall jump
- [ ] Player can dash, with a cooldown
- [ ] Player can crouch
- [ ] Character faces direction it moves in
- [ ] Movement values can be changed through movement profile
- [ ] Player can talk to NPCs with dialogue and choices
- [ ] Player can interact with things, and gated ones stay blocked until item or flag is there
- [ ] Player can carry, use and give items
- [ ] Picked up items stay gone after reload
- [ ] Quest progress is saved and restored
- [ ] Sanity drains and the screen changes per sanity zone
- [ ] Checkpoints and level progress are saved and restored on continue
- [ ] Other players show up in the same level, and game still works offline
- [ ] Game does not lag or drop below 45 FPS on web.