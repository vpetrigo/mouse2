
mouse2
======

This is a fork of the [mouse][mouse_pkg] library.

Take full control of your mouse with this small Python library. Hook global events, register hotkeys, simulate mouse
movement and clicks, and much more.

[mouse_pkg]: https://github.com/boppreh/mouse

## Features

**TBD!**
- Global event hook on all mice devices (captures events regardless of focus).
- **Listen** and **sends** mouse events.
- Works with **Windows** and **Linux**.
- Works with **MacOS** (requires granting accessibility permissions to terminal/python in System Preferences -> Security \& Privacy)
- **Pure Python**, no C modules to be compiled.
- **Zero dependencies** on Windows and Linux. Trivial to install and deploy, just copy the files.
- Includes **high level API** (e.g. [record] and [play]).
- Events automatically captured in separate thread, doesn't block main program.
- Tested and documented.

[record]: #mouse.record
[play]: #mouse.play

This program makes no attempt to hide itself, so don't use it for keyloggers.

## Usage

Install the [PyPI package](https://pypi.python.org/pypi/mouse/):

    $ sudo pip install mouse

or clone the repository (no installation required, source files are sufficient):

    $ git clone https://github.com/boppreh/mouse

Then check the [API docs](https://github.com/boppreh/mouse#api) to see what features are available.


## Known limitations:

- Events generated under Windows don't report device id (`event.device == None`). [#21](https://github.com/boppreh/keyboard/issues/21)
- To avoid depending on X the Linux parts reads raw device files (`/dev/input/input*`) but this requries root.
- Other applications, such as some games, may register hooks that swallow all key events. In this case `mouse` will be unable to report events.



# API
#### Table of Contents

- [mouse.**ButtonEvent**](#mouse.ButtonEvent)
- [mouse.**DOUBLE**](#mouse.DOUBLE)
- [mouse.**DOWN**](#mouse.DOWN)
- [mouse.**LEFT**](#mouse.LEFT)
- [mouse.**MIDDLE**](#mouse.MIDDLE)
- [mouse.**MoveEvent**](#mouse.MoveEvent)
- [mouse.**RIGHT**](#mouse.RIGHT)
- [mouse.**UP**](#mouse.UP)
- [mouse.**WheelEvent**](#mouse.WheelEvent)
- [mouse.**X**](#mouse.X)
- [mouse.**X2**](#mouse.X2)
- [mouse.**version**](#mouse.version)
- [mouse.**is\_pressed**](#mouse.is_pressed)
- [mouse.**press**](#mouse.press) *(aliases: `hold`)*
- [mouse.**release**](#mouse.release)
- [mouse.**click**](#mouse.click)
- [mouse.**double\_click**](#mouse.double_click)
- [mouse.**right\_click**](#mouse.right_click)
- [mouse.**wheel**](#mouse.wheel)
- [mouse.**move**](#mouse.move)
- [mouse.**drag**](#mouse.drag)
- [mouse.**on\_button**](#mouse.on_button)
- [mouse.**on\_click**](#mouse.on_click)
- [mouse.**on\_double\_click**](#mouse.on_double_click)
- [mouse.**on\_right\_click**](#mouse.on_right_click)
- [mouse.**on\_middle\_click**](#mouse.on_middle_click)
- [mouse.**wait**](#mouse.wait)
- [mouse.**get\_position**](#mouse.get_position)
- [mouse.**hook**](#mouse.hook)
- [mouse.**unhook**](#mouse.unhook)
- [mouse.**unhook\_all**](#mouse.unhook_all)
- [mouse.**record**](#mouse.record)
- [mouse.**play**](#mouse.play) *(aliases: `replay`)*


<a id="mouse.ButtonEvent"/>

## class mouse.**ButtonEvent**

ButtonEvent(event_type, button, time)


<a id="ButtonEvent.button"></a>

### ButtonEvent.**button**

Alias for field number 1


<a id="ButtonEvent.count"></a>

### ButtonEvent.**count**(self, value, /)

Return number of occurrences of value.


<a id="ButtonEvent.event_type"></a>

### ButtonEvent.**event\_type**

Alias for field number 0


<a id="ButtonEvent.index"></id>

### ButtonEvent.**index**(self, value, start=0, stop=9223372036854775807, /)

Return first index of value.

Raises ValueError if the value is not present.


<a id="ButtonEvent.time"></a>

### ButtonEvent.**time**

Alias for field number 2




<a id="mouse.DOUBLE"></a>

## mouse.**DOUBLE**
```py
= 'double'
```

<a id="mouse.DOWN"></a>

## mouse.**DOWN**
```py
= 'down'
```

<a id="mouse.LEFT"></a>

## mouse.**LEFT**
```py
= 'left'
```

<a id="mouse.MIDDLE"></a>

## mouse.**MIDDLE**
```py
= 'middle'
```

<a id="mouse.MoveEvent"></a>

## class mouse.**MoveEvent**

MoveEvent(x, y, time)


<a id="MoveEvent.count"></a>

### MoveEvent.**count**(self, value, /)

Return number of occurrences of value.


<a id="MoveEvent.index"></a>

### MoveEvent.**index**(self, value, start=0, stop=9223372036854775807, /)

Return first index of value.

Raises ValueError if the value is not present.


<a id="MoveEvent.time"></a>

### MoveEvent.**time**

Alias for field number 2


<a id="MoveEvent.x"></a>

### MoveEvent.**x**

Alias for field number 0


<a id="MoveEvent.y"></a>

### MoveEvent.**y**

Alias for field number 1




<a id="mouse.RIGHT"></a>

## mouse.**RIGHT**
```py
= 'right'
```

<a id="mouse.UP"></a>

## mouse.**UP**
```py
= 'up'
```

<a id="mouse.WheelEvent"></a>

## class mouse.**WheelEvent**

WheelEvent(delta, time)


<a id="WheelEvent.count"></a>

### WheelEvent.**count**(self, value, /)

Return number of occurrences of value.


<a id="WheelEvent.delta"></a>

### WheelEvent.**delta**

Alias for field number 0


<a id="WheelEvent.index"></a>

### WheelEvent.**index**(self, value, start=0, stop=9223372036854775807, /)

Return first index of value.

Raises ValueError if the value is not present.


<a id="WheelEvent.time"></a>

### WheelEvent.**time**

Alias for field number 1




<a id="mouse.X"></a>

## mouse.**X**
```py
= 'x'
```

<a id="mouse.X2"></a>

## mouse.**X2**
```py
= 'x2'
```

<a id="mouse.version"></a>

## mouse.**version**
```py
= '0.7.1'
```

<a id="mouse.is_pressed"></a>

## mouse.**is\_pressed**(button=&#x27;left&#x27;)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L78)

Returns True if the given button is currently pressed.


<a id="mouse.press"></a>

## mouse.**press**(button=&#x27;left&#x27;)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L83)

Presses the given button (but doesn't release).


<a id="mouse.release"></a>

## mouse.**release**(button=&#x27;left&#x27;)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L87)

Releases the given button.


<a id="mouse.click"></a>

## mouse.**click**(button=&#x27;left&#x27;)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L91)

Sends a click with the given button.


<a id="mouse.double_click"></a>

## mouse.**double\_click**(button=&#x27;left&#x27;)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L96)

Sends a double click with the given button.


<a id="mouse.right_click"></a>

## mouse.**right\_click**()

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L101)

Sends a right click with the given button.


<a id="mouse.wheel"></a>

## mouse.**wheel**(delta=1)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L105)

Scrolls the wheel `delta` clicks. Sign indicates direction.


<a id="mouse.move"></a>

## mouse.**move**(x, y, absolute=True, duration=0, steps_per_second=120.0)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L109)


Moves the mouse. If `absolute`, to position (x, y), otherwise move relative
to the current position. If `duration` is non-zero, animates the movement.
The fps of the animation is determined by 'steps_per_second', default is 120.


<a id="mouse.drag"></a>

## mouse.**drag**(start\_x, start\_y, end\_x, end\_y, absolute=True, duration=0)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L143)


Holds the left mouse button, moving from start to end position, then
releases. `absolute` and `duration` are parameters regarding the mouse
movement.



<a id="mouse.on_button"></a>

## mouse.**on\_button**(callback, args=(), buttons=(&#x27;left&#x27;, &#x27;middle&#x27;, &#x27;right&#x27;, &#x27;x&#x27;, &#x27;x2&#x27;), types=(&#x27;up&#x27;, &#x27;down&#x27;, &#x27;double&#x27;))

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L156)

Invokes `callback` with `args` when the specified event happens.


<a id="mouse.on_click"></a>

## mouse.**on\_click**(callback, args=())

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L170)

Invokes `callback` with `args` when the left button is clicked.


<a id="mouse.on_double_click"></a>

## mouse.**on\_double\_click**(callback, args=())

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L174)


Invokes `callback` with `args` when the left button is double clicked.



<a id="mouse.on_right_click"></a>

## mouse.**on\_right\_click**(callback, args=())

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L180)

Invokes `callback` with `args` when the right button is clicked.


<a id="mouse.on_middle_click"></a>

## mouse.**on\_middle\_click**(callback, args=())

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L184)

Invokes `callback` with `args` when the middle button is clicked.


<a id="mouse.wait"></a>

## mouse.**wait**(button=&#x27;left&#x27;, target\_types=(&#x27;up&#x27;, &#x27;down&#x27;, &#x27;double&#x27;))

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L188)


Blocks program execution until the given button performs an event.



<a id="mouse.get_position"></a>

## mouse.**get\_position**()

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L199)

Returns the (x, y) mouse position.


<a id="mouse.hook"></a>

## mouse.**hook**(callback)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L203)


Installs a global listener on all available mouses, invoking `callback`
each time it is moved, a key status changes or the wheel is spun. A mouse
event is passed as argument, with type either `mouse.ButtonEvent`,
`mouse.WheelEvent` or `mouse.MoveEvent`.

Returns the given callback for easier development.



<a id="mouse.unhook"></a>

## mouse.**unhook**(callback)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L215)


Removes a previously installed hook.



<a id="mouse.unhook_all"></a>

## mouse.**unhook\_all**()

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L221)


Removes all hooks registered by this application. Note this may include
hooks installed by high level functions, such as [`record`](#mouse.record).



<a id="mouse.record"></a>

## mouse.**record**(button=&#x27;right&#x27;, target\_types=(&#x27;down&#x27;,))

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L228)


Records all mouse events until the user presses the given button.
Then returns the list of events recorded. Pairs well with [`play(events)`](#mouse.play).

Note: this is a blocking function.
Note: for more details on the mouse hook and events see [`hook`](#mouse.hook).



<a id="mouse.play"></a>

## mouse.**play**(events, speed\_factor=1.0, include\_clicks=True, include\_moves=True, include\_wheel=True)

[\[source\]](https://github.com/boppreh/mouse/blob/master/mouse/__init__.py#L242)


Plays a sequence of recorded events, maintaining the relative time
intervals. If speed_factor is <= 0 then the actions are replayed as fast
as the OS allows. Pairs well with [`record()`](#mouse.record).

The parameters `include_*` define if events of that type should be inluded
in the replay or ignored.
