ok we finshed the [b1t canvas](<b1t canvas.canvas>) gamejam. this note will forcus on improving the current system and components and general game (code) architecture.

so problems with my current code is that its doing too much things at once.
for example my [animation.gd](https://github.com/sintutiers/b1t-5-gamejam/blob/5eb3e85cf38fc0f7b6a496014561df5fd95b1b59/scripts/components/animation_component.gd) handles:
1. animation
2. sprite flipping
3. idle timer
4. (hacky fall tracking, which was in there for speed of development)

and for more general code stucture should be [loose-oupled](https://en.wikipedia.org/wiki/Loose_coupling) and should not depend on each other. animation component should not have to depend on movement component via a hard dependancy. so stuff should be PULL first, not hard depend.

furthermore the animation component also is not levereging godot correctly, im calling things from the animation state machine directly instead of structuring/making the statemachine so that i can just call the state machine. 

so i wrote some reqqs 

1. Long-term scalability - won’t collapse as things get more complex.
2. Multi-project reuse - reuse the core systems from game to game.
3. Multi-genre flexibility - doesn’t force you into one genre.
4. Complex scalability - works for small projects and big systems without a full rewrite.
5. iteration speed - make progress within a 7-day jam.
