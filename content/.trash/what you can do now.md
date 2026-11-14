---
uid: clxvnf1xzjymjfc6mgemv
title: what you can do now
modified: Thursday, November 12th 2026, 12:09 pm
created: Thursday, November 12th 2026, 1:00 pm
aliases:
  - clxvnf1xzjymjfc6mgemv
---

# what you can do now

> See also: [TDD](<./TDD.md>), [FDD](<./FDD.md>)

A short tour of what the game can do now. It covers the scripts in `scripts/`, not `ARCHIVE SCRIPTS/`.
Use `scenes/game/levels/2.5 test level.tscn` to try it. That level has the player, a camera and one interactable object.

## Controls

| Action | Key |
| --- | --- |
| Move | W A S D (arrow keys work for left, right and up; down is S only) |
| Run | Hold Shift |
| Jump | Space |
| Crouch | Hold Ctrl |
| Dash | Tab |
| Interact | E or left mouse button |
| Console | ` (backtick) |
| Debug menu (FPS etc.) | F3 |

There are no controller bindings yet.

## 1. Moving around

- Walk with WASD. Hold Shift to run, which is twice as fast.
- Turning is quick. Reversing direction uses stronger acceleration than starting from a stop. The sprite does a small squash-flip when you turn.
- Walking into a wall plays the push animation.

## 2. Jumping

- Space jumps. Tap for a short hop. Hold for a full jump. Releasing early cuts the jump.
- Double jump: press Space again in the air. The second jump plays the spin animation.
- Running jump: jumping while running goes 1.5 times higher and further.
- Jump timing has two helpers:
  - Coyote time: you can still jump for a moment after walking off a ledge.
  - Jump buffer: pressing jump just before landing still counts.
- You float a little at the top of a jump.

## 3. Walls

- In the air, hold a direction into a wall to wall slide down it slowly.
- Press Space while sliding to wall jump. You are pushed away from the wall. For a split second your input is ignored so you do not stick back to the wall.
- Touching a wall restores your jumps, so you can chain wall jumps between two walls.

## 4. Dash

- Tab dashes in the direction you are holding. If you hold nothing, you dash forward.
- Dash works on the ground and in the air. You stay level during the dash.
- You get one dash per jump. It refills when you land, with a 0.5 s cooldown.

## 5. Crouch

- Hold Ctrl to crouch. You become half as tall and half as fast.
- Release Ctrl to stand up. Walking off a ledge while crouched makes you fall normally.

## 6. Interacting with Things

- Walk within 2 units of an object and press E or left click.
- Depending on how the object is set up, it can:
  - show dialogue. You cannot move while it is open.
  - give you an item.
  - disappear after use, such as pickups. It stays gone when you return to the level.
  - require an item or flag first. Otherwise it shows a "you can't yet" line or nothing.
  - trigger when you walk into it instead of pressing E, such as auto pickups.
- To try it: in the 2.5 test level, interact with the red sprite. It says "You find ASPECT OF HATE" and adds Aspect of Hate to your inventory.

> [!note]
> Right now that object gives the item twice: once from the object itself and once from `give_item` in `test1.dialogue`. You can keep interacting with it because `free_after` is off.

## 7. Inventory

- You have 8 slots. An item takes one slot per stack. Aspect of Hate does not stack, so each one takes a slot.
- When the inventory is full, nothing is added.
- There is no inventory screen yet. Changes print to the Output panel, for example `[inv] +1 aspect_of_hate (slots 1/8)`.

## 8. Sanity

- The player has a sanity meter from 0 to 100, with zones at 25%, 50% and 75%.
- Items and dialogue can raise or lower sanity.
- Sanity does not drain on its own yet (`drain_per_second` is 0). When drain is on, it pauses during dialogue. There is no sanity bar on screen.

## 9. Multiplayer

- The game connects online automatically when it starts (SpacetimeDB).
- Other players in the same level appear as a ghost of their character, with their position, facing and animation.
- If the connection fails, the game keeps running offline.
- To try it: start two copies of the game and walk around in the same level.

## 10. Saving

- The game remembers which level you are in, your checkpoint, and per-level state such as pickups you already took and dialogue flags for quest state and favours.
- This only works when you play through the menus. A scene run directly from the editor has no save data.

## 11. Cheats and Debug Console

Press ` to open the console:

- `give <item_id> <count>` gives you an item, for example `give aspect_of_hate 3`. Tab autocompletes item names.
- `sanity <value>` sets your sanity, for example `sanity 20`.

Press F3 for the debug menu with FPS and frame times.

## Not in  yet

- No enemies, combat or health.
- No inventory or sanity UI.
- Only one item: Aspect of Hate.
- No controller support.