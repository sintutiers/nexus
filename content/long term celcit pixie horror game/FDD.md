---
uid: o1pk0ngezrjc2a372yc9w
title: Functional Design Document
modified: Sunday, November 15th 2026, 10:09 pm
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

## Content in Doc

- [General Info](<#General Info>)
- [How to Write Requirement](<#How to Write Requirement>)
- [Functional Requirements](<#Functional Requirements>)
	- [Sanity](<#Sanity>)
	- [Dialogue + Choices](<#Dialogue + Choices>)
	- [NPCs](<#NPCs>)
	- [Quests + Favors](<#Quests + Favors>)
	- [Combat](<#Combat>)
	- [Movement + Controls](<#Movement + Controls>)
	- [Camera](<#Camera>)
	- [Interaction](<#Interaction>)
	- [Inventory + Items](<#Inventory + Items>)
	- [Tutorial + Onboarding](<#Tutorial + Onboarding>)
	- [Map + Journal](<#Map + Journal>)
	- [Save + Menus](<#Save + Menus>)
- [Non-functional Requirements](<#Non-functional Requirements>)
	- [Platform & Performance](<#Platform & Performance>)
	- [Accessibility](<#Accessibility>)
	- [Multiplayer](<#Multiplayer>)
- [User Acceptance Test](<#User Acceptance Test>)

## General Info

- FDD = what game does: rules + numbers. why/vibe in [GDD](<./GDD.md>), code in [TDD](<./TDD.md>)
- sections = decided only. 
- open stuff in [Open Questions](<#Open Questions>)
- status: done = works in game / designed = decided, not built / open = needs decision
- priority: must / should / could

## How to Write Requirement

1. what player does
2. numbers
3. done when: how to check it
4. short + simple, prefered for now

## Functional Requirements

### Sanity

core pillar, so concrete, not just "you lose sanity" with no consequenses.

- 0 to 100, 4 stages at 25/50/75 
- drain:
	- flat per second in world
	- wrong dialogue choices, witnessing certain story events
	- proximity to certain objects
- pauses: during locking interactions + inside sanctuaries
- restore:
	- items (books, food etc), amount = per item
	- first time entering sanctuary, +10 (see below)
	- completing quest steps/objectives
	- NPC favors
- encounters, random + set: gain or lose sanity depending on choices
- lower stage = more world change:
	- stage 0 (75-100): baseline
	- stage 1 (50-75): minor unease. visuals in
	- stage 2 (25-50): stronger distortion, some NPC lines change, fake enemies may show up
	- stage 3 (0-25): heavy distortion, more fake enemies, some real threats
	- fake enemies: you dont know which are fake
- sanity 0: not decided, see [Open Questions](<#Sanity#Open Questions>)

must not be minor annoyance, must not make game unplayable

sanctuaries (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Darkwood):

> status: half done (drain pause works)
> priority: must

- first entry: +10 sanity, once per sanctuary
- some objects inside restore extra sanity
- each sanctuary = 1 NPC or interesting interaction
- fixed locations, handcrafted
- never randomly become unsafe. only scripted (dying tree in tutorial)
- done when: enter sanctuary first time, sanity +10, second time nothing

sanity loop:

```mermaid
flowchart TD
	A[Explore / talk to NPCs] --> B[Sanity drains]
	B --> C[Low sanity changes the world]
	C --> D[Restore via items / NPCs / favors]
	D --> A
```

#### Sanity Questions

- [ ] drain: flat per second, how much
- [ ] drain: wrong dialogue choices/story events, how much per event
- [ ] drain: interacting with enemies? (running, fighting back etc)
- [ ] restore: quest steps/objectives, how much
- [ ] restore: NPC favors, which, how much
- [ ] sanctuary objects, how much extra sanity
- [ ] stage 1: sound ?
- [ ] numbers: how many fake enemies in stage 2+3, how many real threats in stage 3
- [ ] sanity 0: this = big open one. things:
	- fail forward: teleport to last sanctuary, lose progress (how much, not save), world remembers. no game over screen. fits hopeless vibe
	- checkpoint reload at reduced sanity (how much). standard, boring
	- sanity 0 = one of endings. aggressive, needs fake-ending system first
	- unlocking whole different world when your a dick? 
- [ ] (or maybe must make it inplayable if player ignores everything?)
- [ ] sanity affects combat?

---
### Dialogue + Choices

- nonlinear story/dialogue
- [x] choices change NPC opinion + story

sanity in dialogue (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Disco Elysium):
- dialogue options can need minimum sanity
- low sanity replaces some options with other ones
- example, NPC asks where you came from:
	- high sanity: "I dont remember."
	- low sanity: "You know where. You sent me here."

#### Dialogue + Choices Questions

- [ ] (hidden fairy meter? like FUN value) opinion. keep as fairy meter or rename, same thing
- [ ] everything = consequence, nothing = fake choice
	- minimum consequence per choice: every player-facing choice writes at least 1 of fact, opinion delta, quest stage, item grant/removal, level flag, sanity delta. if it writes nothing, its fake choice, cut it or make it write something
- [ ] endings + true ending gating: see ending structure + Decisions in [GDD](<./GDD.md>)
- [ ] hallucination AI + just dialogue conditions ?

---
### NPC

> status: done (basic)
> priority: must

- talk, pick dialogue choices
- NPCs remember player actions ("world remembers")

#### NPC Questions

- [ ] NPCs move/schedule, or stand still?
- [ ] NPCs remember player actions: which ones, how long?
- [ ] how NPCs show opinion
- [ ] low sanity changes some lines (stage 2+). alt lines for every NPC or some?

---
### Quests + Favors

# RAW Brainstorming Systems, Im Brainstorming This Part Heavily

what is a favor?
- its a point you get from a quest
- a social depts for mythical entities
- a transaction point.
	- they are a confusing and contradicting mess. ass that is how those creatures operate.

fairies for example, are cheaters and lyers. if they own you a favor, they will do everything in their power to pay it back minimally. if you by example saved their life, and you own them a favor, then them just giving you a coockie or some shit is considered a favor paid, but the other example is that a favor can also be used to get them to join you in a quest in destroying the world.

Debt Ledger

- Debts have size and direction. A small debt is not a big debt.
- A dialogue choice can use debt.
- Unpaid debt gets called in at a bad time.
- This makes the world remember you.

Favor Terms

- A favor's rules are stored as facts.
- "Done" means the rules are met, not just the task.
- A fairy can twist it: task done, rules not met, debt stays.
- The player can twist it too: bluff, argue, or lie.

failure states? :
	- forfeit, betrayal, bankruptcy. Debt bankruptcy = NPCs refuse to deal = soft fail-forward into a different zone path, not a game over.

FACTS THAT ARE DECIDED FOR THE FDD
- economy: is the favors and deps. favors = economy. favor = currency
- 4-5 important NPCs
- player can own and be owned by same NPC
- each has 1 relationship value (= fairy meter)
- each gives 1-2 favors, depending on the NPC
- NPC dialogue changes with relationship
- player can hold multiple deps and favors
- a favor is spent when used
- some quests give favors, some dont.
- fairy meter/opinion changes by way of dialogue, dialogue is also how you can trick fairies and how fairies trick you

#### Quest + Favor Questions

- [ ] NPCs give favors/quests
	- define structure + tracking (quests have stages, game remembers current stage. journal UI ?)
- [ ] rewards: item/info/sanity/new location access

---
### Combat

> [!failure] Blocker
> Decisions in [GDD](<./GDD.md>), options in [Open Questions](<#Combat#Open Questions>). (create moodboard for that, combatboard?)

#### Combat Questions

options:
- A) no combat. threats = dialogue/choice encounters. fighting back = dialogue option, costs sanity. fake vs real enemies resolved by interacting, not hitting. fits input surface + horror tone. buildable on what exists
	- encounters (from [Gameplay moodboard thingie](<./Gameplay moodboard thingie.canvas>), Little Nightmares):
		- 5-8 handcrafted encounters
		- 2-3 choices each: decide, escape, or interact with dangerous thing
		- choices hit sanity, NPC relationship, or inventory
		- some only at certain sanity levels
		- scripted, no enemy AI
- B) small + tactical. whole new system, not built
	- [ ] turn-based Undertale/Omori like. input = choices + maybe timed minigame
	- [ ] fire emblem or cadence of hyrule like (sanity can be way more challenging there)
- C) real time
	- [ ] real time combat, you have button to swing weapon to deal damage
	- [ ] enemy touch/hit = lose sanity
	- [ ] enemy dies after few hits
- combat/interaction FDD:
	- you have like a branch + when fighting, almost always moving

---
### Movement + Controls

walk, run, jump (double, variable height on release), wall slide, wall jump, dash (cooldown, limited airtime), crouch. all in.

> status: done (keyboard movement + controls)
> priority: must

keyboard for now, gamepad + touchscreen later

#### Movement + Control Questions

- [ ] which abilities stay per zone 
	- [ ] tie to level design?
- [ ] web: keyboard only ok?
- [ ] list all actions (move, run, jump, dash, crouch, interact, pause, journal?)

---
### Camera

> status: done
> priority: could

- third person, 2.5D, perspective
- third-person perspective follow camera with damping
- a level can leave camera unassigned for fixed camera
- no free look, no player orbit
- slight mouse lean, see [GDD](<./GDD.md>)

#### Camera Questions

- [ ] camera changes per zone or low sanity (tilt, zoom)?

---

### Interaction

> status: done
> priority: must

- press interact near something, closest one reacts
- things can be gated by item/flag, blocked until present
- picked up things stay gone after reload
- done when: gate opens with right item, stays open after reload

#### Interaction Questions

- [ ] interact prompt: look, shown at low sanity or lies?
- [ ] two things equally close?
- [ ] interact while dashing/in air?

---
### Inventory + Items

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

#### Inventory + Items Questions

- [ ] inventory size limit?
- [ ] inventory UI. see [inventory ideas](<./inventory ideas.canvas>). like minecraft hotbar or point n click HUD
- [ ] pick up by interact or walking over it, which one, or both per item
- [ ] drop items?
- [ ] fake items at low sanity?
- [ ] "shit equipment": what = equipment, does it do anything

---
### Tutorial + Onboarding

> status: half designed
> priority: must

- story: see Tutorial in [GDD](<./GDD.md>)
- teach by doing: movement, interact, talk, choice, sanity drain, sanctuary, sanity restore
- no text popups if tree can say it
- done when: new player leaves forest w/o asking us

#### Tutorial + Onboarding Questions

- [ ] list what = taught where

---
### Map + Journal

> status: open
> priority: could (map) / should (journal)

both are stubs. see [Open Questions](<#Open Questions>).

#### Map + Journal Questions

- [ ] map? no map = more lost, but people get stuck
- [ ] if yes, lies at low sanity?
- [ ] journal UI, exists at all? helps, but fits badly with lost/hopeless vibe. maybe diary unreliable at low sanity
- [ ] next objective shown or nothing

### Save + Menus

> status: done
> priority: must (save) / should (menus)

**Save + Load:**
- checkpoints, level progress, quest progress saved
- picked up items, per level flags saved
- checkpoints only, no manual save
- done when: continue puts you at checkpoint with same items, sanity

**Menus + Settings:**
- main menu, pause, options

#### Save + Menus Questions

- [ ] old saves after updates add/change items/quests
- [ ] web saves: browser storage, can get wiped. warn player? print warning that player should clear cache? perhaps player can export json file with save?
- [ ] settings: volume, fullscreen + accessibility toggles (list in [GDD](<./GDD.md>))
- [ ] art style, wait for Erin

## Non-functional Requirements

### Platform & Performance

- dev/test on small formfactor laptop for now
- ship to desktop + web. web = perf target
- Compatibility renderer, heavier only if needed
- 45 fps min on web, always
- languages + save compat: see [Open Questions](<#Open Questions>)

#### Platform & Performance Questions

- [ ] load time target, esp web (max first download size?)
- [ ] sanity visuals must hold 45 fps
- [ ] languages: english only
- [ ] save compatibility between versions

### Accessibility

- see accessibility list in [GDD](<./GDD.md>). every toggle gets a line here once decided

### Multiplayer

- other players show in same level, works offline (done)

## User Acceptance Test

Check if game meets all functional, design + game requirements in perspective of player.

- [ ] Player can walk + run
- [ ] Player can jump, with variable height + double jump
- [ ] Player can wall slide + wall jump
- [ ] Player can dash, with cooldown
- [ ] Player can crouch
- [ ] Character faces direction it moves in
- [ ] Movement values can be changed through movement profile
- [ ] Player can talk to NPCs with dialogue + choices
- [ ] Player can interact with things, + gated ones stay blocked until item/flag is there
- [ ] Player can carry, use + give items
- [ ] Picked up items stay gone after reload
- [ ] Quest progress = saved + restored
- [ ] Sanity drains + screen changes per sanity stage
- [ ] Checkpoints + level progress = saved + restored on continue
- [ ] Other players show up in same level, + game still works offline
- [ ] Game does not lag or drop below 45 FPS on web.