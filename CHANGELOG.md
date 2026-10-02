# Release notes

```
MarkingForge - Release notes
===============================================================================

1.2.2 - muted editor colours
-------------------------------------------------------------------------------
  - The menu editor's panes no longer sit on a wash of their colour. Over
    3ds Max's dark grey the green and amber washes read as faded olive and
    mustard, and the text on them was hard to read. Every pane now stands on
    the same neutral grey; its colour - muted slate blue, lavender, sand and
    clay - is on the bar along its top edge, its frame and its title.
  - The Editor Guide's colour swatches are read from the editor itself, so the
    guide and the window cannot show different colours again.

1.2.1 - adding a set keeps the key
-------------------------------------------------------------------------------
  - Adding a set to a dial - "Add as a new set" in the dial library, the new
    dial wizard, "Load dial..." or "New set..." - no longer changes what the
    key opens. Until now the new set went on the key at once: adding "Build"
    to Menu 1 made Alt+1 open Build instead of Modelling, although the button
    promised to keep what the dial showed. The new set is the dial's next page
    (the mouse wheel on the open dial) and its tab opens in the editor; "Put
    this set on the key" moves it to the key when you want that.

1.2.0 - the pages of a dial: the mouse wheel and tabs
-------------------------------------------------------------------------------
  - A dial with sets has PAGES. Hold its key and turn the mouse wheel: the
    dial shows its next set (towards you) or the previous one, at the same
    place; release over a command to run it. The next press opens the set on
    the key again. The footer says "page 2 of 3 - mouse wheel". The wheel is
    taken only while such a dial is open - zooming and scrolling are as before.
  - In the editor the sets of a dial are tabs over its contents. Click a tab
    to see and edit that set; the key keeps opening the set marked "on the
    key" until "Put this set on the key".

1.1.0 - every dial as a file, extra dials, keys from the first start
-------------------------------------------------------------------------------
  - Keyboard shortcuts from the first start, however MarkingForge was
    installed: when no dial has a key yet, the first start gives each its
    standard key (Alt / Ctrl+Alt / Shift+Alt + 1..8), skipping keys used by
    something else. Until now only the installer's tick box did this - a
    copied folder or a studio installation left every dial without a key.
    The tick box cleared now tells the first start to leave the keys alone;
    the studio script has -NoShortcuts for the same.
  - The dial library: every dial as a .mfdial file of its own - the 24
    built-in dials as shipped, 8 new extra dials and the 15 dials of the
    preset packs - in the plugin's "dials" folder and in "Dials" in the
    download. "Dial library..." in the editor puts one on a dial, adds it as
    a new set, or restores the original of a dial you changed in one click.
  - Eight extra dials: Mesh cleanup, Pivot and placement, Clone and
    instance, Smoothing and subdivision, Retopology, Quick look, Links and
    helpers (rigging) and Build (walls, doors, windows, stairs, railings,
    foliage).
  - "Save every dial..." in the editor writes each of the 24 dials - and every
    other set of a dial - to a file of its own in a new dated folder.
  - In 3ds Max 2025 and 2026, "Smart Bevel" showed as a missing command (red)
    on the Modifiers dial and in the Modelling pack: that modifier exists in
    3ds Max 2027 only. It is replaced by Quadify Mesh (Modifiers > Geometry)
    and Slice (the pack). Every command of every built-in, extra and pack dial
    was checked in 3ds Max 2025, 2026 and 2027.

1.0.9 - sets of one dial, a bigger centre, submenus
-------------------------------------------------------------------------------
  - Sets: one dial can keep several named contents - "Modelling", "UV",
    "Retopo" - and switch between them in place. In the editor: "Sets of
    this dial" under the slot list (New set..., Show this set, Rename...,
    Delete set). On the dial: "Add 'Next set >' to the dial" puts a row that
    switches to the next set. Under a key: Customize > Hotkey Editor,
    category MarkingForge, "Menu 1 - next set" ... "Menu 24 - next set".
  - One dial in a file: "Save dial..." and "Load dial..." save and load a
    single dial (.mfdial) - as a new set or in place of what it shows.
    Scripts in a file from somebody else are removed unless you keep them.
  - The editor draws the dial you are editing beside the form. Click a wedge
    to select that direction; double-click a submenu to step inside.
  - New dial wizard: which dial, eight commands typed by name (3ds Max
    commands and the ready-made scripts), done - as a new set, so what the
    dial showed is kept.
  - "From a template..." next to "Add a variant..." adds any context variant
    of the built-in dials - Editable Poly and Edit Poly by level, splines,
    cameras, lights - with its condition.
  - The centre that cancels is twice as large (36 px instead of 18).
  - The dotted settings rim sits 30 px beyond the farthest caption instead of
    at the edge of the window, so a short move past the captions reaches it.
  - Dial keys stopped working after some work in panels and menus until the
    viewport was clicked: 3ds Max's menu bar had taken the keyboard after a
    lone Alt. MarkingForge now disarms that while a dial is open and hands
    the keyboard back when the menu bar takes it right after a dial key.
    Diagnostics > Event log shows such moves as FOCUS lines.
  - More submenus in the built-in dials: Create (Alt+3) has Shapes, More
    primitives, Helpers and Cameras and lights; Modifiers (Ctrl+Alt+2) has
    Deform and Geometry; Modelling with nothing selected has Shapes and More
    primitives. Dials you already have are not changed - "Load default
    dials..." brings the new ones in.
  - The editor opens larger (most of the screen) instead of at its minimum.
  - A 3ds Max command put on a direction without a caption of its own showed
    its keyboard-underline mark - "Select &None". The dial, the search, the
    recent-commands dial and the editor's catalogue now show "Select None".

1.0.8 - a script library and an easier editor
-------------------------------------------------------------------------------
  - Script library: "Script library..." under the directions and under the
    list offers 25 ready-made scripts - pivot to bottom, drop to the ground,
    reset XForm, select n-gons, select holes, weld close vertices, auto smooth,
    smoothing on/off, grey clay material, see-through, copy and paste
    transform and more. Each one was run in 3ds Max on a test scene before it
    went into the list; pick one and it goes on the dial with its caption.
  - The editor's panes have their own colours - the dials, the dial's
    contents, the list under it and the catalogue no longer run into one.
  - The button under the directions says "Edit script..." when the direction
    already runs a script, as the list's bar does.
  - The list's buttons sit in two rows, as the directions' do: what is in the
    list above, editing the selected row below.
  - New document: the Editor Guide - your first dial from an empty slot, and
    every part of the editor step by step.

1.0.7 - the centre always cancels
-------------------------------------------------------------------------------
  - Releasing at the very centre of the dial (the small dot) always cancels,
    also when several picks wait in a queue. Before, going a little past the
    ring and back to the centre to give up queued that command, the centre
    turned green and the release ran it.
  - "Multiple picks in one gesture" is off by default. Switch it on in
    MarkingForge > Experimental features; the queue then runs from the dashed
    circle round the centre, and the dot in the middle still cancels.
  - Settings... on a script item takes a second version "with parameters" -
    the command with its caddy, say. An ordinary release runs one of the two
    and releasing past the ring runs the other, as for 3ds Max's commands.
    Scripts that have one are marked "[+ with parameters]" in the editor.

1.0.6 - the list under the dial can be edited
-------------------------------------------------------------------------------
  - A row of the list under the dial is edited like a direction: select it and
    use "Change label...", "Edit script...", "Settings..." or "Colour..." in
    the list's own bar. Before, a row could only be added, removed and moved.
  - "Add a script..." adds a row that runs your own MAXScript, and asks for its
    caption at once - rows are read, so a caption says what a row does.
  - A row's colour dialog offers only the caption colour: a row has no tile.

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
