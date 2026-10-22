---
uid: 4um2r409vhplswwy95ul8
title: Technical Design Document
modified: Thursday, October 22nd 2026, 6:35 pm
created: Thursday, October 8th 2026, 2:31 pm
author:
  - "[Dean](https://deanlemans.github.io/)"
  - Mink
---

# Technical Design Document

see also: [FDD](<./FDD.md>)

- Godot 4.7.2 (possible that there will be version differences between the version currently used and this document)
	- GDScript Formatter 0.27.0
	- Antz's Debug Menu 1.3.0
	- Dialogue Manager 4.1.0
	- Godot State Charts 0.22.5
	- Maaack's Game Template Addon 1.7.0
	- Project Time Tracker 3.0.1
	- Script-IDE 2.2.5

## Performance

- The game should not lag or drop below 60 frames per second.

## Platform

- For now just use Godot's compatibility renderer, if we need more advanced features we will use that then, not sooner.

## System Architecture

We use a component-based architecture.

Game can be divided into these main components that will need to be programmed:
- Components (all extend `Component`, found via `get_component()`)
	- Input (`InputComponent`, `PlayerInputComponent`, `InputFrame`)
	- Facing (`FacingComponent`)
	- Movement (`MovementBase` > `PlatformerMovementBase` > `Movement3DComponent`)
		- Walk, run, jump, dash, crouch, wall slide (already in the movement component, unfinished movement system exists)
		- Ground, Air, Wall Slide, Dash and Crouch states, driven by Godot State Charts
		- `MovementProfile` resource holding all tunable values (speed, jump, dash, etc.)
		- 2D sprites move on a 3D plane (`Movement3DComponent`)
	- Abilities, Launch and Interact (optional, found at runtime)
- Dialogue and choices
	- Talk to NPCs with Dialogue Manager
- Animations
	- `Animations` and `Motions` name constants, driven by movement signals
- Game State
	- `GameState` and `LevelState` resources
	- Level progress and checkpoints
	- Saving through `GlobalState`
- Level Management
	- `LevelManager` extended with state saving (`level_and_state_manager.gd`)

Components communicate through signals (`jumped`, `landed`, `dashed`, `flipped`, etc.) and find each other with `get_component()` instead of hard references. Input is read once per physics frame into an `InputFrame`, so movement never reads `Input` directly.

## Technical Stack

This will be a Godot 4.7.2 game, written in GDScript. We use the addons listed at the top of this document. Dialogue and choices use Dialogue Manager.

## Deployment

The game will be exported from Godot as a build for the target platform. Exact platform and distribution method are not yet clear.

## Technical Specifications

The game makes use of Godot's built-in API (`CharacterBody3D`, `Resource`, signals) plus the addons listed above.

- Movement values are tweaked in a `MovementProfile` resource, not in code.
- The state chart expects the nodes `%StateChart`, `%Ground`, `%Air`, `%WallSlide`, `%Dash` and `%Crouch`.
- A new input source (for example AI) is made by extending `InputComponent` and overriding `_build_frame()`.
- A 2D version is made by extending `PlatformerMovementBase` and implementing its abstract functions.

### User Acceptance Test (UAT)

Check whether the game meets all functional, design and code quality requirements from the perspective of the end user.

- [ ] The player can walk and run
- [ ] The player can jump, with variable height and a double jump
- [ ] The player can wall slide and wall jump
- [ ] The player can dash, with a cooldown
- [ ] The player can crouch
- [ ] The character faces the direction it moves in
- [ ] Movement values can be changed through the movement profile
- [ ] The player can talk to NPCs with dialogue and choices
- [ ] Checkpoints and level progress are saved and restored on continue
- [ ] The game does not lag or drop below 60 frames per second