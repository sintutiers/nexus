---
uid: xjyb3kt4om5k3hixtfyfx
title: Deans Idea List for
modified: Tuesday, September 29th 2026, 7:30 pm
created: Sunday, September 20th 2026, 8:57 pm
---

# Deans Idea List for
<https://itch.io/jam/b1t-jam-5>

for music we can use a programmable things

it will be one of these 4
<https://tidalcycles.org/>
<https://supercollider.github.io/>
<https://sonic-pi.net/>
<https://tonejs.github.io/>
after extensive research(20 minutes) i will go with tidalcycles because the ecosystem is just way bigger

---

# Game Ideas

a game where platforms are 3 states, 
- either they are invicible, visible, or need a certain activation to trigger them. this activation could either be triggering it twice
something like this: 

![Drawing 2026-07-30 17.29.58.excalidraw](<../static_files/Drawing 2026-07-30 17.29.58.excalidraw.md>)
[XOR](<../static_files/references/Exclusive or.md>)
![Drawing 2026-07-30 17.29.58.excalidraw 1](<../static_files/Drawing 2026-07-30 17.29.58.excalidraw 1.md>)

and when we have that, we can add collectables in the game.
- make it a colectable game
- make it a roughlite, where you can upgrade shit
- make it a puzzle game
top down 2d

### Crunched together Idea:

a light source that reveals hidden/darked paths,
light source also reveals hidden collectables/items that let you progress further.

items can also upgrade you light source to be bigger.(roughlite element)

damage system for player, with environment damage.(squid game glass walk?)

goal of the game:
- is the progress further with collecting objects [XOR](<../static_files/references/Exclusive or.md>) obtaining objects that unlock further areas



![Drawing 2026-07-31 13.41.09.excalidraw](<../static_files/Drawing 2026-07-31 13.41.09.excalidraw.md>)
---

for next gamejam, change: signals out, no method calls in
Movement and Dialogue call into other components and change their state directly. Instead they should just emit a signal about what happened, and let the other component listen and react on its own.