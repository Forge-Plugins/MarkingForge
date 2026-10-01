# Release notes

```
MarkingForge - Release notes
===============================================================================

1.0.5 - clean exit, quick gestures counted, two dial entries fixed
-------------------------------------------------------------------------------
  - Closing 3ds Max no longer ends in an error. At exit MarkingForge touched its
    dial window after 3ds Max had already destroyed it, and Windows stopped the
    process on the spot - without a message, but also without the rest of the
    shutdown, so plugins stopped after MarkingForge never got to finish.
  - Quick gestures count in the editor's "Usage" column. Only held dials were
    counted before, so the column missed the way a marking menu is used most.
  - "-> Editable Spline" works on a Line. A Line used to stay a Line; it is now
    converted like every other shape.
  - "+ Normalize Spline" adds the current Normalize Spline modifier. The old one
    it asked for can no longer be created, so the entry failed with an error.

1.0.4 - a flick does what the dial shows
-------------------------------------------------------------------------------
  - A quick gesture (and a tap) reads its context where it BEGAN: the variant,
    the window and the object under the cursor are those at the moment the key
    was pressed - exactly what the held dial would have shown. Before, they were
    read where the flick ended, so a flick from an object into empty space, or
    onto another object, could pick another variant and act on another object.
  - While the command of a quick gesture opens a window, another dial does not
    start inside it - as for every other way of running a command.

1.0.3 - hotbox follows the menu bar
-------------------------------------------------------------------------------
  - The hotbox follows 3ds Max's menu bar: a menu added after start-up (by a
    plugin, a script or a workspace change) shows up without restarting
    3ds Max. A hotbox open while 3ds Max rebuilds its menus closes safely.
  - The hotbox opens faster: entry widths are measured once per menu change,
    not at every opening.

1.0.2 - final review
-------------------------------------------------------------------------------
  - Pinned dial: Enter or a click no longer runs a second command when the
    dial's key is still held afterwards.
  - Releasing over a submenu tile or a broken (red) entry is a cancel: the
    selection is no longer changed and no empty undo entry is left.
  - Selecting the object under the cursor is part of undo. The Undo and
    Selection-sets dials no longer select it first.
  - Context rules that count the selection ("one", "many") treat the object
    under the cursor as the selection it is about to become.
  - Hotbox: an open list is no longer replaced by another menu when the cursor
    crosses a title lying under it; a submenu row is no longer a click target
    that closes the hotbox.
  - Lists under a dial: lower rows no longer flip the settings choice, the
    centre is not painted as "cancel" while a row is lit, and a list made
    longer in the editor is no longer clipped inside a submenu.
  - Shortcuts: Apply keeps extra keys a dial has in 3ds Max's Hotkey Editor,
    keys are compared regardless of modifier order, unapplied shortcuts are
    offered for applying on close, Undo restores into the active shortcut
    file, and a missing shortcut file is detected instead of wiping your
    other shortcuts.
  - Editor: editing a script or value item keeps its colours and settings;
    loading a preset says it replaces the default menu; changing a shortcut
    keeps you in the variant or submenu you were editing.
  - Type-to-search runs outside the keyboard hook; the "Set shortcut" key
    capture stops safely in every case.
  - Uninstalling: the guidance keeps the folder with your shortcut file; a
    file in use is renamed so 3ds Max does not load it. Studio deployment
    checks the layout before installing and restores the previous version
    reliably.

1.0.1 - maintenance
-------------------------------------------------------------------------------
  - Editor 0.7.2: controls wrap when panes narrow; long contents remain scrollable.
  - Printable cheat sheets use saved menus and freshly exported keyboard bindings,
    include all keys and assigned mouse buttons, and identify unsaved editor changes.
  - Hotbox and search commands leave your selection alone; only dial entries act
    on the object under the cursor.
  - Shortcuts: "Set shortcut..." opens a small window - press the keys there.
    Shift combinations work, Backspace removes the shortcut, and neither the
    dials nor 3ds Max react to the keys while it is open, so a key that already
    opens a dial can be recorded; it moves to the dial you are editing.
  - Detect configuration changes made while the editor or chain dialog is open.
  - Reject stale shortcut exports and preserve unrelated shortcut records.
  - Preserve context predicates and explicit per-dial colours; Cancel discards edits.
  - Taps and the Hotbox follow the same context variants as the dials.
  - Correct search cancellation, value state, list picks and command history.
  - Preserve complete menu structure when saving menus into a scene.
  - Handle installer copy exceptions through rollback and protect studio settings.
  - Reject malformed action table IDs and unsupported nested context rules.
  - Read current caddy diagnostics and preserve unreadable usage statistics.

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
    add. Point at a title, then at an entry, and release - or click the entry
    with the left mouse button, as in Maya.

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
  - This download is for 3ds Max 2027. MarkingForge is available for 3ds Max
    2025-2027, each version with its own download; 3ds Max 2024 and earlier
    may follow if enough users ask for them.
  - A mouse binding requires a modifier key (a bare button would take the button
    away from 3ds Max). 3ds Max uses several modifier + button combinations for
    navigation and quad menus - choose a free one.
  - "Recent commands" records commands run through MarkingForge (dials, taps,
    search), not commands run from 3ds Max's own menus.
  - Script items from scenes are always rejected; from presets they are removed
    unless you allow them.
```
