
```Quote from main README
The official documentation is hosted on Read the Docs. It is maintained by the Godot community in its own GitHub repository.
```
This frames the manual as a separate side-project, not a core part of the engine. No wonder new contributors don't think to update it alongside their PRs.

---
- if size for cloning is an issue cant we use a 
- for the ci size issue, cant we just filter for the doc repo and make that run on a separate commit?

I'm in favor of moving the docs to the main repo. I agree with Ivorforce that the separate repo creates extra friction and discourages new contributors from writing docs.

Look at the main README:
``` main repo readme
The official documentation is hosted on Read the Docs. It is maintained by the Godot community in its own GitHub repository.
```
That framing alone tells me 'everything', the documentation is treated as a separate side-project, not a core part of the engine. I think reframing the README would solve part of it, at least.

On the technical side:
- Clone size? Use a subrepo ( submodule or subtree), can also serve as a middleground for  putting a subrepo in the main repo linking to the doc repo.
- CI bloat? Filter the docs folder and create a separe ci for that

this feel like solvable problems to me.