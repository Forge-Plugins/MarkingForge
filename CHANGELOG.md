# Release notes

```
MarkingForge - Release notes
===============================================================================

1.0.0 - first release
-------------------------------------------------------------------------------
Marking menus, a hotbox and gesture sliders for Autodesk 3ds Max 2027.

DIALS
  - 24 dials, each opened by holding a key: Alt+1..8, Ctrl+Alt+1..8,
    Shift+Alt+1..8. Hold to see the dial, flick to run without it, release in
    the centre (or press Esc / the right mouse button) to cancel.
  - Eight directions per dial plus a list of up to twelve rows under it.
  - Submenus up to three levels deep.
  - Commands with a settings dialog (Chamfer, Extrude, Inset...) open it on an
    ordinary release; moving past the ring runs them without it - per command
    configurable.
  - Any dial can also open on a mouse button with a modifier key.

BUILT-IN LAYOUT
  - 24 ready-made dials: Modelling, Hotbox, Create, View, Selection, Modifier
    stack, Undo, Recent commands, Transform, Modifiers, Show and hide,
    Viewports, Viewport display, Snaps and grid, Align and pivot, Render,
    Materials, Animation, Scene, File, Selection sets, UV mapping, Tools and
    setup, Lights and cameras.
  - Context variants: the Modelling dial converts and adds modifiers on a plain
    object and switches to vertex / edge / border / polygon / element tools on
    an Editable Poly or under Edit Poly (the same operation in the same
    direction on both), to spline tools on a shape, and to Slate, Track View,
    Particle View, Scene Explorer and command-panel commands when the cursor is
    over those windows. Create, Selection, Show and hide, Modifiers, Materials,
    Animation, Scene, UV mapping and Lights and cameras follow the context too.
  - Every command in the built-in layout was verified against a stock 3ds Max
    2027 (603 of 603 identifiers).

LIVE DIALS
  - Modifier stack of the selected object, Max's undo list by name (undo
    several steps in one move), recently run commands, the scene's named
    selection sets.
  - Hotbox: all of 3ds Max's main menu as tiles, including menus other plugins
    add.

MENU EDITOR
  - Every 3ds Max action and macroscript (4000+) searchable and assignable by
    click, double-click or drag.
  - Context variants with conditions on object class and kind, modifier in the
    panel or in the stack, sub-object level, window under the cursor, selection
    count, name pattern and layer - with "Take from selection".
  - Custom MAXScript items, gesture value sliders, labels, per-item colours.
  - Colour editor for all dials or one dial (56 colours, live preview).
  - Keyboard shortcuts and mouse buttons set from the editor, with backup and
    undo; "Fill the free slots" with the standard scheme.
  - Presets: save and share a layout; loading removes other people's scripts by
    default and shows the contents first.
  - Printable cheat sheet (HTML + PDF) of every dial, sorted by key.
  - Usage counters per direction with suggestions - nothing is ever rearranged
    automatically.

INSTALLATION
  - Installer as a .mzp (drag onto a viewport) or a script (Scripting > Run
    Script); manual copy also supported. Installs into Application Plugins for
    the current user or all users; updates and repairs in place, even while the
    old version is loaded; uninstalls keeping the user's settings.
  - Optional standard shortcuts on the first start (free keys only).
  - Checks the 3ds Max version and warns about a second copy of the plugin.

DOCUMENTATION
  - Installation and Configuration Guide, QuickStart (17 tutorials),
    Reference, MarkingForge for Maya Users, Studio Deployment Guide, Preset
    Packs, one-page Shortcut Card - installed with the plugin and opened from
    MarkingForge > Documentation.

PERFORMANCE
  - A dial opens in about 3 ms to the first pixel (median, measured in 3ds Max
    2027) - including the very first one after 3ds Max starts, which the
    plugin prepares off screen in the background.
  - The menu editor opens faster when reopened (the action catalogue is kept
    for the session) and its catalogue search no longer stutters while typing.

HELP AND SUPPORT
  - MarkingForge > Report a bug... copies the 3ds Max and plugin details to the
    clipboard and opens an e-mail; works even when the plugin failed to load.
  - MarkingForge > Suggest a feature... for ideas and requests.
  - Bug reports and feature requests: https://github.com/looki666/MarkingForge/issues
    (forms that ask for exactly what is needed); support by e-mail:
    forgeplugins@gmail.com

EXPERIMENTAL FEATURES (switch on in the editor or the MarkingForge menu)
  - On by default: multiple picks in one gesture (a chain run as one undo),
    menu of the object under the cursor, undo / recent / selection-set dials,
    modifier under the cursor, operation-pair learning, chains saved as items.
  - Off by default: value sliders, type-to-search, menus carried by scenes.

KNOWN LIMITATIONS
  - 3ds Max 2027 only. Other versions need their own build.
  - A mouse binding requires a modifier key (a bare button would take the button
    away from 3ds Max). 3ds Max uses several modifier + button combinations for
    navigation and quad menus - choose a free one.
  - "Recent commands" records commands run through MarkingForge (dials, taps,
    search), not commands run from 3ds Max's own menus.
  - Script items from scenes are always rejected; from presets they are removed
    unless you allow them.
```
