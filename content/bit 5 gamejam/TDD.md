## technical design document

- built with godt 4.7.1, when blazium support for 4.7 comes out we will switch to that.
- for pixel art we wil use pixelorama 1.2
- for music i will use strudel 1.13.4
- for documentation we will use obsidian 
- for version control we will use git 2.55.0, lazygit 0.63.1, and github desktop 
- for code we use the [GPL2+](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)
- for assets we use [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

### plugins
1. use [Maaack's Godot-Game-Template](https://github.com/Maaack/Godot-Game-Template/releases/tag/v1.5.0) v1.5 as template
2. use [Debug Menu](https://github.com/antzGames/Antz-Debug-Menu) v1.2 for in-game debugging
3. use [Phantom Camera](https://github.com/ramokz/phantom-camera/releases/tag/v0.11.0.3) v0.11.0.3 for better camera
4. use [Script IDE](https://github.com/Maran23/script-ide/releases/tag/2.2.3) v2.2.3 for better UX 
5. use [Godot Resource Cleaner](https://github.com/ijoschek/GodotResourceCleaner/releases/tag/v0.7.1-beta) v0.7.1 for cleanup
6. use [Dialogue Manager](https://github.com/nathanhoad/godot_dialogue_manager/releases/tag/v3.10.5) v3.10.5 for dialogue 
7. use [Godot Rapier Physics](https://github.com/appsinacup/godot-rapier-physics/releases/tag/v0.8.40) v0.8.40 for better 2D physics (cross-platform sync) 
8. use [GDScript Formatter](https://github.com/GDQuest/GDScript-formatter/releases/tag/0.24.0) v0.24.0 for code styling 
9. use [Project Time Tracker](https://github.com/Fifut/project-time-tracker/releases/tag/v2.0.8) v2.0.8 for work time 
10. use [Godot Health / Hitbox / Hurtbox](https://github.com/cluttered-code/godot-health-hitbox-hurtbox/releases/tag/v5.0.4) v5.0.4 for template hitbox 
### maybe for future
1. https://godotneers.github.io/G.U.I.D.E/
2. https://github.com/bitbrain/beehave
3. https://github.com/cashew-olddew/Universal-Transition-Sh
4. https://github.com/SirRamEsq/SmartShape2D
5. https://github.com/jitspoe/godot-console
6. https://github.com/Oen44/Godot-Inventory
7. https://github.com/TaloDev/godot
8. https://github.com/glass-brick/Scene-Manager
9. https://github.com/foxssake/netfox 
10. https://github.com/Nokorpo/gato-godot-accessibility-toolkit
11. https://github.com/Koisuji02/GodotShaderWarmup
12. https://github.com/NodotProject/godot-torrent


---


![[usefull links for b1t jams]]


---
# code

code must be:
[OOP](https://en.wikipedia.org/wiki/Object-oriented_programming)
[loose coupling](https://en.wikipedia.org/wiki/Loose_coupling)
[gdscript style guide](https://docs.godotengine.org/en/latest/tutorials/scripting/gdscript/gdscript_styleguide.html)
readable by regular mortals

---

code must be:
[OOP](https://en.wikipedia.org/wiki/Object-oriented_programming)
[loose coupling](https://en.wikipedia.org/wiki/Loose_coupling)
readable by regular mortals

i want a system for managing, collectables, and battary system, and inventory, and healthbar, progestion system, safe system
- i dont need a one size fit all, i need a one size fit some, can i use database? sqlite?
- make everything a different component?
- autoload for every system/script?