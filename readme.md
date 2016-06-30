# Source of Quake engine

## Current status:

* GNU/Linux only (for now),
* Compiles! :)
* Sound doesn't work,
* Still relies on xf86dga,
* Mouse support not tested (whole input is X event based...),
* Sometimes corrupted visuals (z-buffer artifacts?),
* Game segfaults at loading first map, only demo from menu could be played.


## Plans:

### Short term
- [x] Remove non-Linux code paths
- [ ] Resolve issues related to map loading (something, something 64bit support)
- [ ] Move to GLFW for window creation and input handling
- [ ] Experiment with different OpenGL versions (4+ ?)
- [ ] New sound lib: SDL/OpenAL?

### Long term
- [ ] Improved AI/or AI in general
- [ ] Scripting
- [ ] Support for shaders from newer OpenGL versions
- [ ] Game editor (fork and modernize GtkRadiant ?)

### Ideas
- [ ] Vulkan?
