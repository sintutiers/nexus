---
uid: ikr2cdqhxjk1bxfffiqc8
created: Sunday, October 25th 2026, 9:16 pm
modified: Sunday, October 25th 2026, 9:19 pm
---
# 1. The mechanics I'd actually implement

## 1. Sanity changes dialogue and perception

Keep

![Disco Elysium: Talk to Joyce about the Pale without Kim - walkthrough - gamepressure.com](https://images.openai.com/static-rsc-4/t2M8Vk9chpgYPAwldwa8Ei8tXboVnHJyj7qzk9_EyFyC6RttzEihQHCsZK9rcO_FCUAgrgFS4gPtUFQ__y0HOwb0sS6EzZOMpkk9GWM2YuImASMXRQXYFuQnKyKZS4m5ZFtJBrvkUkGBMlXLe6t3hOScStbeg2WhXdZiXRXLidI?purpose=inline)

Inspired by: Disco Elysium
One sanity variable determines which dialogue options are available and occasionally changes how NPCs appear.

Implementation:

- One sanity value between 0 and 100.
    
- Certain events increase or decrease it.
    
- Dialogue options have minimum sanity requirements.
    
- At low sanity, some dialogue options are replaced with alternative ones.
    

Example:

An NPC asks you where you came from.

- High sanity: "I don't remember."
    
- Low sanity: "You know where. You sent me here."
    

You don't need elaborate hallucination AI or complicated systems. Just different dialogue conditions.






