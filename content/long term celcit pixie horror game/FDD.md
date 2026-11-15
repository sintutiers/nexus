---
uid: o1pk0ngezrjc2a372yc9w
title: Functional Design Document
modified: Sunday, November 15th 2026, 6:42 pm
created: Monday, October 19th 2026, 7:34 pm
author:
  - "[Dean](https://deanlemans.github.io/)"
  - "[Erin](https://erwall002.wixsite.com/erin-wall-1)"
  - Mink
---

# Functional Design Document

> see also: [GDD](<./GDD.md>) for vision/story/world, [TDD](<./TDD.md>) for technical

> sources: [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), [inventory ideas](<./inventory ideas.canvas>)

> [!error] to dean, from dean
> becarefull of scope creep, and perfectionism. i love adding ideas (see whole doc)

## Table of Contents

- [Info](<#Info>)
- [How to Write Requirement](<#How to Write Requirement>)
- [Functional Requirements](<#Functional Requirements>)
	- [Sanity](<#Sanity>)
	- [Dialogue and Choices](<#Dialogue and Choices>)
	- [NPCs](<#NPCs>)
	- [Quests / Favors](<#Quests / Favors>)
	- [Combat](<#Combat>)
	- [Movement](<#Movement>)
	- [Controls](<#Controls>)
	- [Camera](<#Camera>)
	- [Interaction](<#Interaction>)
	- [Inventory and Items](<#Inventory and Items>)
	- [Tutorial / Onboarding](<#Tutorial / Onboarding>)
	- [Map](<#Map>)
	- [Journal / Quest Tracker](<#Journal / Quest Tracker>)
	- [Save and Load](<#Save and Load>)
	- [Menus and Settings](<#Menus and Settings>)
- [Non-functional Requirements](<#Non-functional Requirements>)
	- [Platform](<#Platform>)
	- [Performance](<#Performance>)
	- [Compatibility](<#Compatibility>)
	- [Accessibility](<#Accessibility>)
	- [Multiplayer](<#Multiplayer>)
- [Open Questions](<#Open Questions>)
	- [Sanity](<#Open Questions#Sanity>)
	- [Dialogue and Choices](<#Open Questions#Dialogue and Choices>)
	- [NPCs](<#Open Questions#NPCs>)
	- [Quests / Favors](<#Open Questions#Quests / Favors>)
	- [Combat](<#Open Questions#Combat>)
	- [Movement](<#Open Questions#Movement>)
	- [Controls](<#Open Questions#Controls>)
	- [Camera](<#Open Questions#Camera>)
	- [Interaction](<#Open Questions#Interaction>)
	- [Inventory and Items](<#Open Questions#Inventory and Items>)
	- [Tutorial / Onboarding](<#Open Questions#Tutorial / Onboarding>)
	- [Map](<#Open Questions#Map>)
	- [Journal / Quest Tracker](<#Open Questions#Journal / Quest Tracker>)
	- [Save and Load](<#Open Questions#Save and Load>)
	- [Menus and Settings](<#Open Questions#Menus and Settings>)
	- [Performance](<#Open Questions#Performance>)
	- [Compatibility](<#Open Questions#Compatibility>)
- [User Acceptance Test (UAT)](<#User Acceptance Test (UAT)>)

## General Info

- FDD = what game does: rules + numbers. why/vive in [GDD](<./GDD.md>), code in [TDD](<./TDD.md>)
- sections = decided only. 
- open stuff in [Open Questions](<#Open Questions>)
- status: done (works in game) / designed (decided, not built) / open (needs decision)
- priority: must / should / could

## How to Write Requirement

1. what the player does
2. numbers
3. done when: how to check it
4. short and simple, prefered for now

## Functional Requirements

### Sanity

core pillar, so concrete, not just "you lose sanity" with no consequenses.

- 0 to 100, 4 stages at 25/50/75 
- drain:
	- flat per second in the world
	- wrong dialogue choices, witnessing certain story events
	- proximity to certain objects
- pauses: during locking interactions, and inside sanctuaries
- restore:
	- items (books, food etc), amount set per item
	- first time entering sanctuary, +15 (see below)
	- completing quest steps / objectives
	- NPC favors
- encounters, random and set: gain or lose sanity depending on choices
- lower stage changes the world more:
	- stage 0 (75-100): baseline
	- stage 1 (50-75): minor unease. visuals in
	- stage 2 (25-50): stronger distortion, some NPC lines change, fake enemies may show up
	- stage 3 (0-25): heavy distortion, more fake enemies, some real threats
	- fake enemies: you dont know which are fake
- sanity 0: not decided, see [Open Questions](<#Open Questions>)

must not be a minor annoyance, and must not make the game unplayable

sanctuaries (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Darkwood):

> status: half done (drain pause works)
> priority: must

- first entry: +15 sanity, once per sanctuary
- some objects inside restore extra sanity
- each sanctuary has 1 NPC or interesting interaction
- fixed locations, handcrafted
- never randomly become unsafe. only scripted (dying tree in tutorial)
- done when: enter sanctuary first time, sanity +15, second time nothing

sanity loop:

```mermaid
flowchart TD
	A[Explore / talk to NPCs] --> B[Sanity drains]
	B --> C[Low sanity changes the world]
	C --> D[Restore via items / NPCs / favors]
	D --> A
```

### Dialogue and Choices

- nonlinear story/dialogue
- [x] choices change NPC opinion and the story

sanity in dialogue (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Disco Elysium):
- dialogue options can need minimum sanity
- low sanity replaces some options with other ones
- example, NPC asks where you came from:
	- high sanity: "I dont remember."
	- low sanity: "You know where. You sent me here."

### NPCs

> status: done (basic)
> priority: must

- talk, pick dialogue choices
- NPCs remember player actions ("world remembers")

### Quests / Favors

- economy: no. favors are the economy. no shops, no currency. its the celtic-pact thing anyway

numbers (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Majoras Mask):
- 4-5 important NPCs
- each has 1 relationship value (= fairy meter)
- each gives 1-2 favors
- NPC dialogue changes with relationship
- no reputation simulation, few values + conditional dialogue

### Combat

> [!failure] Blocker
> see Decisions in [GDD](<./GDD.md>), options in [Open Questions](<#Open Questions>). (create moodboard for that, combatboard?)

### Movement

walk, run, jump (double, variable height on release), wall slide, wall jump, dash (cooldown, limited per airtime), crouch. all in.

### Controls

> status: done (keyboard)
> priority: must

keyboard for now, gamepad + touchscreen later

### Camera

> status: done
> priority: could

- third person, 2.5D, perspective
- third-person perspective follow camera with damping
- a level can leave the camera unassigned for a fixed camera
- no free look, no player orbit
- slight mouse lean, see [GDD](<./GDD.md>)

### Interaction

> status: done
> priority: must

- press interact near something, closest one reacts
- things can be gated by item or flag, blocked until present
- picked up things stay gone after reload
- done when: gate opens with right item, stays open after reload

### Inventory and Items

> status: done (no visual yet)
> priority: must

- carry, use, give items
- pickup flow (from [inventory ideas](<./inventory ideas.canvas>)):
	- pick up by interact or walking over it
	- text: "you picked up *item*"
	- cant pick up yet (missing other item first): popup says so
	- NPC can give item (quest reward)
	- item shows in inventory
	- use: "you used *item*"
	- one time use: "*item* has been destroyed"
- done when: pick up book, see it, use it, sanity up

### Tutorial / Onboarding

> status: half designed
> priority: must

- story: see Cool Beginning in [GDD](<./GDD.md>)
- teach by doing: movement, interact, talk, choice, sanity drain, sanctuary, sanity restore
- no text popups if tree can say it
- done when: new player leaves forest without asking us

### Map

> status: open
> priority: could

see [Open Questions](<#Open Questions>)

### Journal / Quest Tracker

> status: open
> priority: should

see [Open Questions](<#Open Questions>)

### Save and Load

> status: done
> priority: must

- checkpoints, level progress, quest progress saved
- picked up items, per level flags saved
- checkpoints only, no manual save
- done when: continue puts you at checkpoint with same items, sanity

### Menus and Settings

> status: done (placeholder look)
> priority: should

- main menu, pause, options

## Non-functional Requirements

### Platform

- dev/test on small formfactor laptop for now
- ship to desktop + web . web is the perf target
- Compatibility renderer, heavier only if needed

### Performance

- 45 fps minimum on web, always

### Compatibility

see [Open Questions](<#Open Questions>)

### Accessibility

- see accessibility list in [GDD](<./GDD.md>). every toggle gets a line here once decided

### Multiplayer

- other players show in same level, works offline (done)

## Open Questions

not decided yet. decided? move answer up into its section, delete here.

### Sanity

- [ ] drain: flat per second, how much
- [ ] drain: wrong dialogue choices / story events, how much per event
- [ ] drain: interacting with enemies? (running, fighting back etc)
- [ ] restore: quest steps / objectives, how much
- [ ] restore: NPC favors, which, how much
- [ ] sanctuary objects, how much extra sanity
- [ ] stage 1: sound ?
- [ ] numbers: how many fake enemies in stage 2 and 3, how many real threats in stage 3
- [ ] sanity 0: this is big open one. things:
	- fail forward: teleport to last sanctuary, lose progress (how much, not the save), world remembers. no game over screen. fits the hopeless vibe
	- checkpoint reload at reduced sanity (how much). standard, boring
	- sanity 0 is one of the endings. aggressive, needs the fake-ending system first
	- unlocking a whole different world when your a dick? 
- [ ] (or maybe must make it inplayable if the player ignores everything?)
- [ ] sanity affects combat?

### Dialogue and Choices

- [ ] (hidden fairy meter? like a FUN value) opinion. keep it as the fairy meter or rename, same thing
- [ ] everything has a consequence, nothing is a fake choice
	- minimum consequence per choice: every player-facing choice writes at least one of fact, opinion delta, quest stage, item grant/removal, level flag, sanity delta. if it writes nothing, its a fake choice, cut it or make it write something
- [ ] endings + true ending gating: see ending structure + Decisions in [GDD](<./GDD.md>)
- [ ] hallucination AI + just dialogue conditions ?

### NPCs

- [ ] NPCs move / schedule, or stand still?
- [ ] NPCs remember player actions: which ones, how long?
- [ ] how NPCs show opinion
- [ ] low sanity changes some lines (stage 2+). alt lines for every NPC or some?

### Quests / Favors

- [ ] NPCs give favors/quests
	- define structure and tracking (quests have stages, game remembers current stage. journal UI ?)
- [ ] rewards: item, info, sanity, or access to new location

### Combat

options:
- A) no combat. threats are dialogue/choice encounters. fighting back is a dialogue option that costs sanity. fake vs real enemies resolved by interacting, not hitting. fits the input surface + horror tone. buildable on what exists
	- encounters (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Little Nightmares):
		- 5-8 handcrafted encounters
		- 2-3 choices each: decide, escape, or interact with dangerous thing
		- choices hit sanity, NPC relationship, or inventory
		- some only at certain sanity levels
		- scripted, no enemy AI
- B) small and tactical. whole new system, not built
	- [ ] turn-based Undertale/Omori like. input is choices + maybe a timed minigame
	- [ ] fire emblem or cadence of hyrule like (sanity can be way more challenging there)
- C) real time
	- [ ]  real time combat, you have a button to swing a weapon to deal damage
	- [ ] enemy touches/hits you = lose sanity
	- [ ] enemy dies after few hits
- combat/interaction FDD:
	- you have like a branch and when your fighting, your almost always moving

### Movement

- [ ] which abilities stay per zone 
	- [ ] tie to level design?

### Controls

- [ ] web: keyboard only ok?
- [ ] list all actions (move, run, jump, dash, crouch, interact, pause, journal?)

### Camera

- [ ] camera changes per zone or low sanity (tilt, zoom)?

### Interaction

- [ ] interact prompt: look, shown at low sanity or lies?
- [ ] two things equally close?
- [ ] interact while dashing / in air?

### Inventory and Items

- [ ] inventory size limit?
- [ ] inventory UI. see [inventory ideas](<./inventory ideas.canvas>). like minecraft hotbar or point n click HUD
- [ ] pick up by interact or walking over it, which one, or both per item
- [ ] drop items?
- [ ] fake items at low sanity?
- [ ] "shit equipment": what is equipment, does it do anything

### Tutorial / Onboarding

- [ ] list what is taught where

### Map

- [ ] map? no map feels more lost, but people get stuck
- [ ] if yes, lies at low sanity?

### Journal / Quest Tracker

- [ ] journal UI, exists at all? helps, but fits badly with lost / hopeless vibe. maybe diary unreliable at low sanity
- [ ] next objective shown or nothing

### Save and Load

- [ ] old saves after updates add or change items / quests
- [ ] web saves: browser storage, can get wiped. warn player? print a warning that player should clear cache? perhaps player can export json file with safe?

### Menus and Settings

- [ ] settings: volume, fullscreen + accessibility toggles (list in [GDD](<./GDD.md>))
- [ ] art style, wait for Erin

### Performance

- [ ] load time target, esp web (max first download size?)
- [ ] sanity visuals must hold 45 fps

### Compatibility

- [ ] languages: english only
- [ ] save compatibility between versions

## User Acceptance Test (UAT)

Check if game meets all functional, design and game requirements in perspective of player.

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
- [ ] Sanity drains and the screen changes per sanity stage
- [ ] Checkpoints and level progress are saved and restored on continue
- [ ] Other players show up in the same level, and game still works offline
- [ ] Game does not lag or drop below 45 FPS on web.