# Scenes

A scene is almost like a screen. At the end of a scene, the console is cleared (unless otherwise specified).

## FAQ

### What if I want to remove a character or characters?

In our guidelines, scenes should not be cleared until the end of the scene. You can do this, but it is not recommended.

Use ANSI escape codes.

Help with ANSI escape codes:

<https://gist.github.com/fnky/458719343aabd01cfb17a3a4f7296797>
<https://en.wikipedia.org/wiki/ANSI_escape_code>

## Hello World Scene

```py
from oopsie import Scene

class Hello_World_Scene(Scene):
    def __init__(self):
        self.message = "Hello World!"
        self.oopsie_init() # Learn more about this below.
    def run(self, out, inp, oc):
        out(self.message())
        out(inp()) # Output input
        oc("The time is : ") # Sends without adding a new line.
        inp() # Input for the about line.
```

> ⚠️ **Limitations:** You can not define functions named `start` or `replay`.

## Using The Scene Manager

The scene manager controls scenes in a queue.

### Setup

Instead of

```py
scene1.start()
scene2.start()
```

use

```py
from oopsie import SceneManager
scene_manager = SceneManager
scene_manager.add(scene1, scene2)
scene_manager.start()
```
