# Release notes

```
MarkingForge - Release notes
===============================================================================

1.5.48 - Script items undo; final review (2026-10-09)
-------------------------------------------------------------------------------
  - A dial item that runs a script (Add TurboSmooth, Convert to Editable
    Poly and some two hundred more) could not be undone: Ctrl+Z left the
    change. Each one is now an undo entry named after the item.
  - Updating MarkingForge no longer gives a key back to a dial whose key you
    cleared on purpose: "Set up the standard shortcuts" is ticked for a first
    install only.
  - The editor's Save keeps the previous menus.json (the last 5, in a
    "backups" folder beside it).
  - Several commands in one gesture: Select, Move, Rotate or Scale ends a
    waiting tool like a right-click (now said in the documents); a new scene
    drops a waiting queue; a creation tool no longer drops it; a queue that
    waited for a tool is not saved as one item.
  - A condition the plugin does not know (a typo such as "subObject") is
    reported, and a variant with no known condition is skipped instead of
    matching everywhere.
  - Smaller: a dial bound to Alt + a mouse button no longer wakes the menu
    bar; a click in the hotbox works in the place it was opened; old backup
    files are pruned; the documents give the short QuickStart's real size.

1.5.47 - A pinned dial gives the keyboard back (2026-10-09)
-------------------------------------------------------------------------------
  - With a dial pinned by typing, a click into a text field of 3ds Max (the
    object name, a spinner) left the dial open, and what you typed went into
    the dial's search instead of the field. The dial now closes, running
    nothing, as soon as the field takes the keyboard.

1.5.46 - A value direction undoes with Ctrl+Z (2026-10-09)
-------------------------------------------------------------------------------
  - A value set by dragging (an experimental "value" direction) could not be
    undone: Ctrl+Z took back only the selection of the object under the
    cursor and left the value. Now one Ctrl+Z takes back both.
  - Moving through a value direction - even in passing, then giving up in
    the centre - selected the object under the cursor and left it selected.
    It now reads the starting value without changing the selection.

1.5.45 - The waiting queue: its status line and lesson (2026-10-09)
-------------------------------------------------------------------------------
  - While a queue waited for a tool, 3ds Max's status line said "... Menu N
    - Overriding" instead of naming the next command. It now says, for
    example: "right-click when Inset is done - next: Extrude".
  - Documentation: QuickStart Easy v3 has a lesson of its own on a queue
    that waits for you (lesson 14) - what a right-click, Esc, a pan, another
    tool or a new gesture does, and how Ctrl+Z goes back. The QuickStarts,
    the Reference and the Editor Guide describe it too.

1.5.44 - A queue waits for Inset, Bevel... (2026-10-09)
-------------------------------------------------------------------------------
  - Several commands in one gesture: Inset, Extrude, Bevel, Chamfer and any
    other command that switches on a tool waiting for a drag used to work
    only as the LAST command of a queue - the next one switched the tool off
    again. Now the queue stops at such a command: drag in the viewport, then
    right-click, and the next queued command starts by itself. 3ds Max's
    status line says which one is next.
  - Each such step is its own undo entry (commands that finish at once
    still share one). Picking another tool, selecting another object or a
    new gesture drops the rest of the queue.

1.5.43 - A readable narrow catalogue; review fixes (2026-10-08)
-------------------------------------------------------------------------------
  - Editor: with the action catalogue dragged narrow, the "Category / table"
    column took the space and the command names all but vanished. The
    category now gives way - the names keep at least half of the pane - and
    gets its width back when the pane is widened. A width dragged by hand is
    kept, also through a search.
  - A tap or flick of another dial key while a dial was PINNED (typing in
    it) ran that key's command under the open dial. It runs nothing now.
  - A dial held over a floating editor (Slate) and released outside it ran
    the editor's commands with the editor not active, so they did nothing.
    The release now works where the dial was opened, as a flick already did.
  - Editor: Apply shortcuts writes only the keys that were changed - it no
    longer puts back, for the selected dial, a key changed meanwhile in
    3ds Max's Hotkey Editor. The guard against writing shortcuts while Max's
    shortcut file is missing works again. Looking at a context variant that
    has no menu of its own no longer saves an empty one. A dial written by
    hand with "Hotbox" in capitals, a null list or rules, or an unsigned
    table number loads as 3ds Max reads it.
  - The event log no longer says "chain: ..." about a queue that a release
    in the centre dropped.

1.5.42 - The 3D view under the dial (2026-10-08)
-------------------------------------------------------------------------------
  - 1.5.38 taught the plugin to look through its own dial at the window
    beneath; over the 3D view it stopped one window short, so with the dial
    on screen the view was not recognised - a page turned with the wheel
    there lost the object under the cursor. It now reaches the view.

1.5.41 - A queue runs in order; Connect on edges works (2026-10-08)
-------------------------------------------------------------------------------
  - Several commands in one gesture: 3ds Max ran the dial's macros LATER
    than the script items of the same queue (its action system delays them),
    so a queue could run out of order and outside its single undo entry.
    1.5.39 did not fix that - re-measured. Queued macros now run at once,
    one after another, as one Ctrl+Z.
  - "Connect" on the Editable Poly edge dial did nothing: it ran Max's
    vertex connect. It now connects the selected edges. Dials saved before
    are updated when the plugin or the editor reads them.
  - "Connect" on the border dial did nothing either; Loop is there now.

1.5.40 - The short QuickStart: chains and the keys (2026-10-08)
-------------------------------------------------------------------------------
  - QuickStart_Easy_v3 has a lesson on several commands in one gesture: how
    to queue, where to let go, a working example (Ring + Connect), which
    commands chain well and why Inset, Extrude, Bevel or Chamfer go last.
  - Its first pages explain the standard keys: chosen to stay out of the way
    of 3ds Max's own shortcuts, and meant to be changed - with the steps.

1.5.39 - Several commands in one gesture run in order (2026-10-08)
-------------------------------------------------------------------------------
  - With "Multiple picks in one gesture" on, 3ds Max commands in a queue ran
    only after the script items of the same queue, whatever their place in
    it - and outside the single undo entry. A queue now runs strictly in
    order, as one Ctrl+Z.
  - The QuickStart example (Inset, then Extrude) changed nothing: those dial
    items only start Max's interactive tool, which waits for a drag. The
    documents now say which commands chain well (selections, Flip, Connect,
    Weld, modifiers...), that a command waiting for a drag goes last, and
    give a working example: Ring, then Connect.

1.5.38 - The window under the dial (2026-10-08)
-------------------------------------------------------------------------------
  - With a dial on screen, the plugin asked "which window is under the
    cursor?" and got the dial itself. Turning a page with the mouse wheel
    over the Slate material editor, Track View or another window could
    therefore miss that window's variant; the footer lost "under cursor:
    <object>" after a page turn; and the event log named no window. The
    plugin now looks through its own dial at the window beneath it.

1.5.37 - More examples in the short QuickStart (2026-10-08)
-------------------------------------------------------------------------------
  - The short QuickStart (QuickStart_Easy_v3) grows to 14 lessons: the
    variants already in the built-in dials and why their order matters; a
    variant for a window (Track View, from a template); object class, kind
    and modifier names - what each looks at and how to write them; the
    dotted settings ring and how to change its size; and the right-click
    menu of a dial - saving and loading one dial, or every dial.

1.5.36 - Updating while a document is open (2026-10-08)
-------------------------------------------------------------------------------
  - With a PDF of the installed version open (in Acrobat, say), an update
    stopped halfway, said the previous version could NOT be restored - it
    was in fact still in place - and left a backup in the temp folder. The
    installer and the studio script now look for files another program holds
    open BEFORE they change anything, name them and stop: close them and
    install again. Uninstall does the same. The studio script ends with the
    new exit code 8.

1.5.35 - Variants in the short QuickStart (2026-10-08)
-------------------------------------------------------------------------------
  - The short QuickStart (QuickStart_Easy_v3) has a lesson on variants: what
    they are, one made step by step (Export for the whole scene when nothing
    is selected, on the File dial), and what a variant's condition can ask.
  - Every document names its 3ds Max version where you see it when it is
    open: in the window title of the PDF viewer and at the foot of every
    page (the covers already did).

1.5.34 - The mouse wheel always changes the dial (2026-10-08)
-------------------------------------------------------------------------------
  - With an object selected whose modifier has a variant (Unwrap UVW, say),
    turning the wheel on a dial with pages could bring back the same
    commands: a page copied from another dial brings that dial's variants
    along, so two pages showed the very same variant. The wheel now always
    changes what you see - such a page shows its own contents instead.

1.5.33 - No warning at every opening of the editor (2026-10-08)
-------------------------------------------------------------------------------
  - Opening the editor on dials saved before 1.5.30 showed a warning box,
    "Some of the file could not be read", about the updated "Open UV Editor"
    item - and showed it again at every opening. Nothing was lost: the item
    was updated. The editor now says so in its status bar and marks the file
    changed, so Save (or saving when you close) keeps the update and the note
    does not come back.

1.5.32 - The UV editor as a window; object name and layer in the editor (2026-10-07)
-------------------------------------------------------------------------------
  - A variant can ask for the cursor over the UV editor (Edit UVWs): pick
    "UV editor (Edit UVWs)" under "Cursor over the window" (in menus.json:
    "window": "uvEditor"). It covers the UV canvas, the side panels and the
    toolbars of that window. Until now a UV variant could only ask for the
    Unwrap UVW modifier to be open, which holds over every window.
  - "What is open?" in the condition window lists the UV editor too, and
    MarkingForge.windowInfo() names it.
  - The condition window has fields for the object name (with * as a
    wildcard) and the layer, each with a Take button that fills it from the
    selected object. Both conditions worked before but could only be typed
    into menus.json. The MATCHES preview now decides them as well.

1.5.31 - Open UV Editor in configurations saved earlier (2026-10-07)
-------------------------------------------------------------------------------
  - "Open UV Editor" opens the UV editor also in dials saved before 1.5.30.
    1.5.30 fixed the shipped dials only; a menus.json saved earlier kept the
    old item, which opens nothing. The plugin now runs the working command
    in its place, and the menu editor rewrites the item when it opens the
    file (Save keeps it).
  - The event log (MarkingForge > Diagnostics > Event log) names the window
    each gesture began over, next to the dial variant it showed.

1.5.30 - Slate and the UV editor (2026-10-07)
-------------------------------------------------------------------------------
  - The commands of the dials over the Slate Material Editor now run. They
    did nothing whenever Slate was not the active window - after a click in
    a viewport, say - because 3ds Max runs an editor's own commands only
    while that editor is active. A dial command now first makes the window
    the gesture pointed at the active one (over a viewport nothing
    changes). The same holds for every editor with commands of its own,
    Track View among them.
  - Slate's two ways to an object's material say what they do: "Material
    of selected" takes the selected object's material at once,
    "Eyedropper: click an object" waits for a click on an object.
  - "Open UV Editor" (the UV dial with an Unwrap UVW selected) opens the UV
    editor. It ran a command that opened nothing.
  - The QuickStart now also comes in a short version (QuickStart_Easy_v3,
    11 pages) in the Documentation folder.

1.5.29 - fixes from a function-by-function review (2026-10-07)
-------------------------------------------------------------------------------
  - Menus from the scene file (experimental): "sceneMenuUse false" in the
    Always mode no longer comes undone the next time the configuration is
    saved, and switching from Always to Ask stops using the scene's menus
    until you consent again.
  - The menu editor:
    - Load default dials... that has nothing to bring in no longer marks
      the editor as unsaved; neither does emptying an empty direction.
    - Assign on a hotbox or on a dial that fills itself does nothing and
      says why (those dials do not use their eight directions).
    - A group in the catalogue picked instead of an action: the Assign
      buttons say so instead of doing nothing silently.
    - Replacing what a dial with pages shows (a library dial, a dial file,
      the wizard) gives the page on the key the new dial's name.
    - Fill the free slots... and the first start no longer give a dial a
      key that another MarkingForge dial already holds as its second key.
    - The Save preset... and Load preset... tooltips say what a preset
      holds since 1.5.28.
  - The installer: a first installation that fails half-way removes the
    incomplete copy, so 3ds Max does not load it at the next start.
  - A hand-edited menus.json whose dial pages lack their list no longer
    makes "Menu N - next set" fail with an error in the Listener.
  - Holding Escape or Enter over an open dial no longer passes the key's
    repeats on to 3ds Max; the error for a damaged menus.json names slots
    1 to 24; the Studio Deployment guide lists exit code 1.

1.5.28 - presets keep pages and colours; Assign under each table (2026-10-07)
-------------------------------------------------------------------------------
  - Save preset... now keeps each dial's pages and the colours of the dials
    (Colours...), and Load preset... replaces the slots' pages with the ones
    in the file. A set added after saving the preset no longer stays behind
    after loading it. A preset of the whole layout sets the dial colours as
    saved (the default ones when it saved none, presets from before 1.5.28
    included); a pack of a few dials leaves your colours alone. The editor's
    own colours (Editor colours...) stay in their own file and are never
    part of a preset.
  - Load default dials... with "Replace the slots that already have a menu
    as well" ticked is the state MarkingForge came with: every dial also
    gets its default pages back (pages you added are removed) and the
    default dial colours. Filling only the empty slots changes neither.
  - Assign sits under the table it fills: "Assign to selected direction"
    under the directions, and a new "Assign to selected row" under the list,
    which puts the catalogue's action in place of the selected row. The two
    Assign buttons at the bottom of the window (under the catalogue and in
    the bottom bar) are gone; a double-click or a drag still works.

1.5.27 - the licence names its licensor (2026-10-07)
-------------------------------------------------------------------------------
  - LICENSE.txt names the licensor - ForgePlugins, Poland - and the address
    for bug reports and feature requests next to the e-mail. The terms are
    unchanged.

1.5.26 - release notes in order (2026-10-07)
-------------------------------------------------------------------------------
  - The notes of 1.5.25 below are written out in full and stand under this
    title with the others. Nothing else changed.

1.5.25 - fixes from a full code review (2026-10-07)
-------------------------------------------------------------------------------
  - Hotbox: the entry under the cursor at the moment you release the key is
    the one that runs. A move onto another entry, or off the list, right
    before the release ran the entry lit a moment earlier.
  - Installer and studio script: when the copied files cannot even be read
    back for the check after an update, the previous version is restored,
    as it is when a file differs.
  - Menus from the scene file (an experimental feature): changing the
    editor's setting for scene menus from Never to Ask or Always now finds
    the menus of the scene that is already open; until now it took reopening
    the scene. Ask still waits for your consent.
  - A damaged menus.json, dial file or preset is refused with a message that
    names the broken place, before a single dial is changed. A preset that
    failed half-way could leave some slots replaced and some not.
  - A menus.json without its own fallback dial shows, in the editor, the
    eight commands 3ds Max really falls back to (Undo, Redo, Zoom Extents...)
    instead of an empty dial that saving would have written over them.
  - Save every dial... twice in the same minute makes a second folder ("(2)")
    instead of writing over the first. Load every dial... puts back a dial
    that followed the fallback dial as it was saved, and the colours as
    saved, also after the fallback dial or the colours changed since.
  - The cheat sheet made with 3ds Max closed lists every key of a dial that
    has more than one.
  - Conditions on the mode and on the selection ("Selected", "selected ")
    are read the same way by the editor's preview and by 3ds Max.

1.5.24 - the features roadmap in the menu (2026-10-07)
-------------------------------------------------------------------------------
  - MarkingForge > Roadmap (Trello) opens the public board of planned and
    in-progress features in your browser; the Suggest a feature... window
    links to it as well, and so do the README and the Installation Guide.

1.5.23 - the cheat sheet shows every page of a dial; review fixes (2026-10-07)
-------------------------------------------------------------------------------
  - The cheat sheet drew only the page a dial's key opens; the dial's other
    pages (the ones the mouse wheel turns to) were missing - the Alt+5
    viewport dial printed one page of five. Every page is now drawn, headed
    "Page 2 of 5: ...", in the order the wheel reaches them, and its checks
    (a source whose toggle is off, an action with no name) cover the other
    pages too. The heading of the sheet counts them.
  - Studio script (Deploy-MarkingForge.ps1): started as "powershell -File ..."
    from PowerShell 7 (the default in Windows Terminal), it stopped with exit
    code 1 right after copying - Windows PowerShell could not load its own
    Get-FileHash there - so the copy was neither verified nor rolled back.
    The check no longer needs that command.
  - Load default dials... with "Replace the slots that already have a menu
    as well" ticked could lose a dial on a configuration from before 1.5.21:
    an empty slot whose dial sat on another key stayed empty while that
    other key was replaced too. Every slot is now filled when you replace
    them all. A page of the Alt+5 viewport dial no longer counts as the
    Shift+Alt+1 dial of the same name, which left that slot empty.
  - Load preset... (and the four preset packs) keeps each slot's own mouse
    button, as the dial library does, and the page on the key takes the
    preset dial's name.
  - The dial footer and MarkingForge.version() show the version and its
    release date, without the internal note that used to follow.
  - Documents: the 2025 and 2026 Installation Guide and Studio Deployment
    guide name their own package (MarkingForge_Max2025_..., the
    MarkingForge_2025 folder); the Reference counts the dial library as it
    ships (12 extra dials, not 8).

1.5.22 - fixes from the review of 1.5.14-1.5.21 (2026-10-07)
-------------------------------------------------------------------------------
  - A key another program holds for the whole of Windows is named. PowerToys
    ZoomIt, for one, records a window with Ctrl+Alt+5 and takes the key, so
    3ds Max never receives it and the dial on it cannot open. The menu
    editor now says so in red under the dial's shortcut, the Set shortcut...
    window warns before you take such a key, and Fill the free slots... and
    the first start leave it out. (Programs that read the keyboard by other
    means, AutoHotkey for one, cannot be seen this way.)
  - Load default dials... no longer puts a dial on a second key: an empty
    slot whose default dial you already have elsewhere (on a configuration
    from before 1.5.21, say) stays empty and the window says where the dial
    is. Replacing every slot no longer leaves the old viewport pages behind
    the Modifiers dial on Alt+2.
  - Load preset... says, slot by slot, which of your dials it replaces.
  - Installer and studio script: the backup made before an update does not
    follow a link either (1.5.15 made removing safe; copying could still
    copy a whole share into the temporary folder); a failed update under a
    path with "[" in it restores the previous version; a backup that cannot
    be cleaned up no longer ends the script with the wrong exit code.
  - Texts: the README's quick gesture and hotbox sections, the dial
    library's list of extras, the beta checklist (new keys, the settings
    default, the Report a bug window), the Report a bug tooltip; the
    Installation Guide's uninstall steps are numbered 1-3 again. The editor
    video and the colour presets video show the editor with the new dial
    list, and the Installation Guide's installer pictures were taken again.

1.5.21 - the dials laid out for modelling first (2026-10-07)
-------------------------------------------------------------------------------
  - A fresh installation puts the dials in a new order: the first keys
    model, the rarely used ones sit furthest away.
      Alt+1..8        Modelling, Modifiers, Selection, Create, the viewport
                      with the hotbox (its last page), Modifier stack, Undo,
                      Recent commands
      Ctrl+Alt+1..8   Transform, Align and pivot, Lights and cameras, UV
                      mapping, Snaps and grid, Show and hide, View, Viewports
      Shift+Alt+1..8  Viewport display, Selection sets, Materials, Render,
                      Animation, Scene, Tools and setup, File
    Every dial is the same as before - only its key moved. Modifiers, once
    Ctrl+Alt+2, is now Alt+2; Selection Alt+3; Create Alt+4; the viewport
    and the hotbox Alt+5. Modifier stack, Undo and Recent keep Alt+6..8.
  - Your own configuration keeps its layout. To take the new one: Load
    default dials... in the editor with "Replace the slots that already have
    a menu as well" ticked (it fills only empty slots otherwise). The dial
    library and the four preset packs follow the new layout (each pack still
    replaces the same dials as before).
  - Every document, the README and the store texts name the new keys; the
    pictures of the dials were taken again.

1.5.20 - clickable links in every MarkingForge window (2026-10-07)
-------------------------------------------------------------------------------
  - MarkingForge > Report a bug... and Suggest a feature... open a window
    whose GitHub address and e-mail are links: one click opens the issue
    forms or your e-mail program (the bug report's e-mail carries the
    version in its subject). Until 1.5.19 they were a question box with the
    addresses as plain text to retype.
  - MarkingForge > Documentation, when the guides are not next to the
    plugin, says where they are online - as links, too.
  - Every link in these windows and in About is drawn in link blue.

1.5.19 - the project's new home on GitHub (2026-10-07)
-------------------------------------------------------------------------------
  - Bug reports, feature requests and the documentation now live at
    https://github.com/Forge-Plugins/MarkingForge - in the README, every
    document, the MarkingForge menu's report windows and the store texts.
  - The plugin itself is unchanged apart from its version.

1.5.18 - ForgePlugins in the package manifest (2026-10-07)
-------------------------------------------------------------------------------
  - PackageContents.xml names ForgePlugins as the author and the company -
    what 3ds Max's plugin manager and the Autodesk App Store show.
  - The plugin itself is unchanged apart from its version.

1.5.17 - commands run without their settings by default (2026-10-07)
-------------------------------------------------------------------------------
  - An ordinary release over Chamfer, Extrude, Inset, Bevel... now runs the
    command at once, as its Modify-panel button does - for Inset, Extrude or
    Bevel you drag in the viewport. Releasing PAST the dotted ring (or a
    long flick) opens its settings first. Until 1.5.16 it was the other way
    round. The tick box "An ordinary release shows the action's SETTINGS"
    in Experimental features brings the old way back, and Settings... in
    the editor still chooses per command.
  - A configuration that set this itself keeps its choice. One that never
    touched it ("showItemSettings" missing from menus.json) gets the new
    default.
  - QuickStarts, Installation Guide, Editor Guide, Reference, the Maya guide,
    README and the store text describe the new default; the pictures of a
    dial aimed inside and past the ring were taken again.

1.5.16 - documentation brought up to the last versions (2026-10-07)
-------------------------------------------------------------------------------
  - Both QuickStarts: moving the settings ring has its own part - the steps
    and the real Settings ring... window - instead of a one-line tip; the
    hotbox says that Esc or a right click closes it.
  - Reference, chapter 8: MF_ORIGIN_SCREEN, MF_ORIGIN_VIEW and
    MF_ORIGIN_WORLD - where the gesture began, for your own scripts: what
    each holds, when it is set (also for the hotbox and the search since
    1.5.14) and a script that creates an object there.
  - Installation Guide: what Uninstall removes - only the MarkingForge
    folder and two flag files; a link is removed as a link (1.5.15).
  - The plugin itself is unchanged apart from its version.

1.5.15 - Uninstall and updates never follow a link (2026-10-07)
-------------------------------------------------------------------------------
  - The installer's Uninstall, and every Update / Repair, could delete files
    OUTSIDE MarkingForge's folder when that folder held a link. A junction or
    symbolic link inside it (a studio's shared dials, say) had the files it
    pointed to deleted, and a MarkingForge folder that was itself a link to
    a studio share emptied the share. Both happened in a test: 3 of 3 and 80
    of 80 files. Links are now removed as links; what they point to is never
    touched. A normal installation, with no links, was not affected.
  - The studio script (Deploy-MarkingForge.ps1) takes every path literally:
    a "[" in a profile or share path no longer breaks an install or makes a
    removal match another folder. It also never follows a link.
  - Uninstall also removes the "skip shortcuts" flag file, so a later
    install sets the standard shortcuts up as the tick box says.
  - Checked in a sandbox for 3ds Max 2025, 2026 and 2027, with both the
    installer's Uninstall and the studio script: another vendor's plugin,
    look-alike folder names, another year's MarkingForge, loose files and
    your own settings (menus.json, the shortcut file) all survive unchanged.

1.5.14 - fixes from the second final review (2026-10-07)
-------------------------------------------------------------------------------
  - Scripts started from the hotbox or from Type-to-search read MF_ORIGIN_*
    of THIS gesture. These two paths never published it, so a macroscript
    picked there read the point of the previous dial or flick.
  - Escape closes the hotbox, as it closes every dial since 1.5.12 (the
    right mouse button still does too). Ctrl+Shift+Esc during a dial held
    with Ctrl now opens the Task Manager instead of cancelling the dial.
  - Saving menus.json while a dial is open no longer moves that dial's
    settings ring under your hand; the new distance applies from the next
    gesture.
  - Editor, Settings ring...: a slot that turns into a hotbox in some
    context (a rule) is skipped like a plain hotbox; "Hotbox" in capitals
    counts too, as it does for the plugin; with no plugin loaded the window
    says so instead of calling the plugin old.
  - Editor, Value...: the number of decimals is read as the plugin reads
    it. A value such as 2.7 or 1e100, which the plugin runs as 0 decimals,
    showed as 2 or 4, and OK then silently changed the slider.
  - Texts: the Autodesk submission notes, the store descriptions and the
    licence texts in the listing kits name 3ds Max 2025, 2026 and 2027.

1.5.13 - fixes from the final review of 1.5.10-1.5.12 (2026-10-06)
-------------------------------------------------------------------------------
  - Scripts read MF_ORIGIN_* (where the gesture began) published at the
    release again, as up to 1.5.10. 1.5.11 put it off until a script ran:
    a macroscript reached through the Recent dial then read an older
    gesture's point, and in a queue of several picks the
    point was worked out after earlier picks had already changed the view.
  - The settings ring keeps the distance you set on every dial. On a dial
    with a caption of the full width east or west, the window's edge held
    the ring on that caption for any distance up to 20 px and took 20 px off
    larger ones. The dial window now always has room for the ring (about
    22 px more on each side than before - also at the default distance, so
    the 1.5.10 note that it then keeps its 1.5.9 size no longer holds).
  - The window is sized for your ring distance already when 3ds Max starts,
    and the editor's ring preview no longer leaves its distance on the dial
    until the next gesture - so no resize on the way to the first pixel.
  - Settings ring... in the editor: a slot that is a hotbox (which has no
    ring) previews another dial and says so; with a plugin older than 1.5.10
    the window says the setting is ignored there; the preview can no longer
    show the previous picture.
  - Texts: the 2025 and 2026 packages no longer name one year twice in the
    1.5.7 list of builds, or say Smart Bevel exists only in their version; the
    store GIFs are all under 2 MB as the listing says; README, Reference and
    the beta checklist corrected.

1.5.12 - numeric input and macro origin fixes (2026-10-06)
-------------------------------------------------------------------------------
  - Escape cancels a held dial even with Type-to-search disabled, including
    Ctrl-based shortcuts. Other typing passes through when search is off.
  - Settings ring: very large numeric values are clamped consistently in the
    editor and plugin; nonfinite editor inputs use the default distance.
  - Value item editor: malformed numeric fields no longer raise Python/Qt
    overflow errors. Decimal places are limited before conversion to Qt's int.
  - Macros stored as action-table references receive the current gesture
    origin, just like macros stored by name and category.

1.5.11 - performance over a long session (2026-10-05)
-------------------------------------------------------------------------------
  Asked: "the dials feel slower after many gestures, and the longer I move
  over an open dial". Measured first, in 3ds Max with real key and mouse
  input on a copy of a working configuration: 400 held gestures, 300 more
  that ran commands, and three 40 s holds with the cursor circling. Nothing
  grew - opening about 5 ms, the first pixel about 2.2 ms, a release 4-6 ms,
  a cursor tick about 1 ms while moving, the same in the last block as in
  the first; memory, handles and GDI objects flat. What was removed is work
  that could make a single gesture stall:
  - usage.json (the Usage column) is no longer written inside the key
    release every tenth gesture - it is written 1.5 s later, when no dial is
    open;
  - the event log keeps its last 512 entries without moving all of them on
    every new one;
  - a pick of a plain 3ds Max action no longer compiles and runs MAXScript to
    publish MF_ORIGIN_* - only scripts, sliders and macroscripts, which can
    read it, get it (less MAXScript garbage, fewer collection pauses);
  - the start-up menu log (menu_log.txt) is kept under 512 KB.
  New diagnostics: MarkingForge.perfSeries() reports every held gesture in
  blocks of 25 (opening, first pixel, release, cursor ticks, paints) and
  every HITCH - a held tick over 25 ms with its parts, an opening over 40 ms,
  a release over 60 ms - with the time of day; perfReset() clears them. When
  a dial feels slow, perfSeries() says where the time went.

1.5.10 - the settings ring's size is yours to set (2026-10-05)
-------------------------------------------------------------------------------
  - New in the menu editor: Settings ring... sets how far the dotted ring
    lies past the farthest caption, from 0 to 200 px (20 px by default, as
    before). The window shows the real dial with the ring where you put it.
    The ring is the settings boundary: releasing inside it runs Inset,
    Chamfer and the like WITH their settings, past it WITHOUT them (or the
    other way round when that is your default). A quick flick without the
    dial uses the same ring, so both always agree. Saved in menus.json as
    "rimDistance"; a value out of range is clamped and reported.
  - The dial window grows with a ring set farther out, so the ring is never
    cut off by the window's edge; at the default it keeps its 1.5.9 size.
  - MAXScript: MarkingForge.rimInfo() reports the distance in use;
    snapshotMenuEx takes "rim=N" to draw a dial with another distance.
  - Store pictures and animations taken again from the current dial; the
    beta-test checklist lists the nine PDFs and the quick-gesture rule.

1.5.9 - fixes from the final review (2026-10-05)
-------------------------------------------------------------------------------
  Quick gestures and taps now do exactly what the held dial does:
  - A flick or tap on a dial that fills itself works: Alt+7 up undoes,
    Alt+8 up repeats the last command, Alt+6 opens a modifier. They read
    only the file's (empty) directions before and did nothing.
  - A flick acts on the page the held key would open (the page used last),
    also right after 3ds Max starts.
  - The flick's length is measured in the dial's own units, so the settings
    rim and the dead zone sit where the dial draws them at 125-200 % display
    scaling too.
  - The object under the cursor and the command now share ONE undo step on a
    flick, a tap and a list row, as on a held release.
  - The context is judged once per flick (it was judged three times, which
    could switch "menu under the cursor" off on a single flick in a heavy
    scene); a tap while another dial is open is ignored; scripts read the
    flick's own starting point (MF_ORIGIN_*).
  The dial:
  - Returning to the centre from a submenu two levels deep goes up ONE level.
  - A variant asking for a sub-object level no longer wins over an object the
    pick will select (that object is at object level).
  - Rules for docked panels (command panel, time slider, Scene Explorer)
    match while docked, not only while floating.
  - A list row lights and repaints the moment the cursor moves onto it; rows
    the window cannot show are not picked; a submenu waiting for the hand to
    come back does not pick a row either; the queue row no longer covers the
    north caption; the dead zone includes its edge; a hotbox entry reached in
    the last 8 ms before release is the one that runs.
  - A release on a list row runs a waiting multi-pick queue too; undo-dial
    entries cannot be queued.
  Reliability:
  - The remembered page is written after the command runs, and a moment with
    one page (a scene's own menu) no longer erases it.
  - Queued work is cancelled when the plugin stops; the type-to-search index
    is rebuilt right after 3ds Max rebuilds its menus, not on the first key.
  - A save landing while the configuration reloads is no longer skipped; a
    toggle in Experimental features no longer blocks the editor's save; a
    duplicated direction or slot key in the file is reported.
  - The mouse hook leaves clicks on other programs' windows alone and
    recovers from a release lost to the lock screen.
  - A dial with an action of an uninstalled plugin no longer re-reads every
    action table on every key press.
  The editor:
  - Enter in a text field (the catalogue search, the menu name) no longer
    saves menus.json.
  - Apply shortcuts writes only the dials changed in this session.
  - Variants, the menu name and Load default dials respect inheriting slots
    and mouse buttons; Condition... keeps values it does not list; deleting
    a set, a cancelled script row and Colours... with no change behave.
  - Direction keys written in lower case are read the plugin's way.
  - Library: Smoothing on/off and Renderable on/off switch shared
    (instanced) modifiers and shapes once; + UVW Map (box) skips lights.
  Installers: the .mzp installer refuses a second copy in the other folder
  (the studio script already did); the studio script finds non-English
  3ds Max settings folders and takes paths with brackets literally.

1.5.8 - two fixes after the 1.5.7 review (2026-10-04)
-------------------------------------------------------------------------------
  - Save last chain as an item works again for a chain released over a
    submenu tile (or a broken entry): 1.5.7 wrote the chain down before
    leaving that tile out, so nothing could be saved.
  - Recent commands (Alt+8) are no longer cleared when 3ds Max rebuilds its
    menus (a workspace change, loading a menu file). They hold action
    identities that are looked up again before every use.

1.5.7 - stability and safer concurrent editing (2026-10-03)
-------------------------------------------------------------------------------
  - Scene menu storage uses the 3ds Max allocator and preserves the previous
    data if allocating its replacement fails.
  - Commands are resolved again before use after an action table changes;
    queued gesture callbacks cannot act on a closed or replaced gesture.
  - Value directions handle re-entrant getters, cancellation, reloads and
    invalid numeric results. Releasing a gesture samples its final position.
  - Executing commands and chains keeps stable copies across callbacks;
    saved chains preserve quotes and backslashes in action identifiers.
  - Usage statistics distinguish temporary access failures from damaged
    files and avoid waiting for another writer during normal gestures.
  - Preset writes are serialized, dial switching checks for changed files,
    and a failed chain save retains the text entered in its dialog.
  - Failed shortcut restores recover the current shortcut set. Damaged drag
    data and non-object library files no longer raise editor exceptions.
  - Adding Next set to all pages checks their capacity before changing any.
  - Editor layouts release their native Qt items when their window closes.
  - Clearing usage statistics reports a retained counter or an unreadable
    response instead of displaying an unverified success message.
  - Gesture origins use physical screen coordinates at Windows display
    scaling above 100%; pinned dial gaps no longer pass clicks to the viewport.
  - Tap commands resolve their context once; rule benchmarks no longer
    disable hover targeting through its performance protection.
  - Saving a scene menu retains the choice to use it in the current scene;
    existing damaged scene menu data is protected from accidental overwrite.
  - File watching retries failed reads without accepting a failed read as
    the latest configuration. Developer reloads report missing startup paths.
  - Updated builds for all three versions (2025, 2026 and 2027); editor version 0.19.3.

1.5.6 - every document up to date with 1.5.2-1.5.5
-------------------------------------------------------------------------------
  - The README, the Shortcut Card and the guide for Maya users now say that
    a flick follows the settings rim too (1.5.2): a short flick opens the
    settings window, a long one runs without it.
  - The Reference: two new rows in the troubleshooting table - a flick that
    always (or never) opens the settings, and Inset that "does nothing" past
    the rim (it waits for a drag in the viewport, as its own button does).
  - The Reference, the Editor Guide, the guide for Maya users, the Shortcut
    Card and the store texts name the easy QuickStart; the store texts said
    "QuickStart (20 tutorials)" - it has 22.
  - No change to how MarkingForge works.

1.5.5 - the easy QuickStart covers everything
-------------------------------------------------------------------------------
  - MarkingForge_QuickStart_Easy.pdf now teaches everything the full
    QuickStart does - the same 22 lessons with the same numbers, the five
    tricks, the key map, the learning plan and every problem - in plainer
    words: shorter sentences (10.9 words on average instead of 13.5, half as
    many over 20 words), one action per step, and each term (submenu,
    variant, hotbox, content source, page...) explained where it first
    appears. 1.5.4 had made it twelve lessons that left things out.
  - No change to how MarkingForge works.

1.5.4 - a second, easy QuickStart
-------------------------------------------------------------------------------
  - New document: MarkingForge_QuickStart_Easy.pdf - the QuickStart said
    simply, in twelve short lessons (16 pages instead of 41): six on using
    the dials, six on changing them in the editor, then a page of things
    good to know and the common problems. The full QuickStart stays as it
    was and now points to the easy one.
  - The README lists every document again (the Editor Guide was missing).
  - No change to how MarkingForge works.

1.5.3 - the dial 25 px bigger
-------------------------------------------------------------------------------
  - 1.5.2 made the dial too small. The wedges are 25 px longer again
    (radius 115 instead of 90; 130 up to 1.5.1). The names stay right at
    the wedges' edge and the dotted settings rim stays 20 px past the
    farthest name, so the rim moves out with the names.
  - The return zone of multiple picks follows the dial: out to 92 px.
  - The menu editor's dial drawing follows the new proportions.

1.5.2 - a smaller dial; a quick gesture past the rim skips the settings
-------------------------------------------------------------------------------
  - The dial is smaller: the wedges are 40 px shorter (radius 90 instead of
    130), the names sit right at the wedges' outer edge (4 px instead of
    14), and the dotted settings rim lies 20 px past the farthest name
    instead of 30. On a typical dial the rim is about a third smaller.
  - A quick gesture (a flick with no dial shown) now measures how far the
    hand went. Past the place where the dial would draw its dotted rim it
    counts as a release past the rim - so a long flick at Extrude or Bevel
    runs it WITHOUT the settings window, a short one with it, exactly as
    the same movement does on the shown dial. Up to 1.5.1 every flick
    counted as a short one and always opened the settings.
  - The menu editor's dial drawing follows the new proportions.
  - QuickStart, tutorial 4, corrected: past the rim Inset, Extrude and Bevel
    start WITHOUT the window as their Modify-panel button does - drag in the
    viewport to set the amount. It said they run at once with the last
    values; 3ds Max's own Inset macro (EPoly_Inset) toggles the drag mode.

1.5.1 - a QuickStart in plain words
-------------------------------------------------------------------------------
  - The QuickStart is rewritten in plain words: fewer technical terms, the
    same steps. It now also covers what changed since 1.4.5 - the viewport
    pages of Alt+2 with a picture (tutorial 5), submenus that open in place
    with their path under the dial (tutorials 1 and 13), the dial opening on
    the page you used last (tutorial 20), 51 dials in the dial library
    (tutorial 21), and new hints and troubleshooting rows.
  - Small corrections in the Reference and the README to match.
  - No change to how MarkingForge works.

1.5.0 - five ready-made values; a QuickStart tutorial on them
-------------------------------------------------------------------------------
  - Value... in the menu editor offers six ready-made examples instead of
    three: viewport field of view, time slider frame, TurboSmooth
    iterations of the selection, uniform scale of the selection, thickness
    of the selected splines, height of the selected object. The new ones
    act on every selected object; each was run in 3ds Max - read, written,
    read back - and with nothing selected (the dial shows ?, nothing is
    written).
  - QuickStart: tutorial 15, "Values - five gesture sliders", walks through
    switching values on, the Value... window and five examples, each with
    every field to type and something to try.
  - The same release for 3ds Max 2025, 2026 and 2027 - checked file by file
    and in each 3ds Max.

1.4.9 - a submenu says where you are
-------------------------------------------------------------------------------
  - Inside a submenu the footer under the dial shows the path - the dial's
    name and the tiles you went through, e.g. "Nothing selected  >  More
    primitives". Until now a submenu had no name of its own there and the
    footer showed MarkingForge's version number instead.

1.4.8 - submenus open in place; a dial opens the page you turned to last
-------------------------------------------------------------------------------
  - A submenu (a direction marked >, such as Shapes or More primitives on
    Alt+1 with nothing selected) now opens IN PLACE: the dial stays where it
    is and its tiles become the submenu's. Until 1.4.7 it opened as a new
    dial further out in that direction, and coming back moved it back - the
    dial seemed to jump one way or the other depending on the tile.
    Move back inside the dial to pick; nothing is picked by a release made
    while the cursor is still out where it entered. The centre of the dial
    goes back up a level, as before.
  - A dial with several sets opens on the page you turned to last with the
    mouse wheel, not on the first one - also after 3ds Max restarts. The
    page is remembered by its name (last_pages.json beside menus.json); a
    set renamed or removed in the editor opens the first page again.

1.4.7 - your shortcuts stay where 3ds Max keeps them
-------------------------------------------------------------------------------
  - The shortcut file (hotkeys\MarkingForge_Hotkeys.hsx) now always stays in
    3ds Max's own plugcfg\MarkingForge folder, also when the dials are moved
    to another folder with MARKINGFORGE_CONFIG_DIR. Until 1.4.6 it followed
    the dials there - but 3ds Max remembers ONE active hotkey set per 3ds Max
    version, for all its sessions, so a second 3ds Max started on a test or
    studio folder switched the shortcuts of your own 3ds Max to that folder,
    and once the folder was gone 3ds Max started with no shortcuts at all.
  - Nothing to do for most users: without MARKINGFORGE_CONFIG_DIR the file was
    always in plugcfg\MarkingForge. With the variable set, the next shortcut
    change in the editor writes the file back to plugcfg\MarkingForge.

1.4.6 - the lighting page of Alt+2 works; commands from more tables
-------------------------------------------------------------------------------
  - Shadows, Highlights, Ambient occlusion and hard or soft shadows on the
    Viewport lighting page (Alt+2, one wheel notch towards you) were drawn
    broken in 1.4.5 and did nothing. Their commands sit in a table whose
    number 3ds Max reports as negative, and MarkingForge refused negative
    table numbers. Found by testing the page with real mouse and keyboard
    input.
  - The same fix applies to any command you put on a dial from such a table
    in the menu editor - those were broken the same way. Nothing to do: the
    dials you already have work as they are.

1.4.5 - the viewport on Alt+2; the hotbox as a page; 102 scripts
-------------------------------------------------------------------------------
  - Alt+2 drives the viewport, on four pages turned with the mouse wheel:
      Viewport shading (on the key): default shading, clay, facets, flat
        colour, hidden line, bounding box, wireframe override, edged faces;
        the seven stylized looks in the list.
      Viewport lighting: shadows, ambient occlusion, highlights, scene or
        default lights, shaded or realistic materials with or without
        maps; hard or soft shadows, the selected-lights switches, textures
        and progressive refinement in the list.
      Viewport display: grid, safe frames, statistics, ViewCube, selection
        brackets, shade selected faces, selected with edged faces, isolate;
        see-through, backface cull, expert mode and hiding lights,
        cameras, helpers, shapes or particles in the list.
      Viewport views: top, front, left, right, perspective, orthographic,
        camera, maximize; bottom, back, zooms, one or four viewports, the
        field of view, undo and redo of a view change in the list.
    Every switch 3ds Max has a command for is that command, so the dial
    shows it checked while it is on. Each item was run in 3ds Max twice.
  - The hotbox is the fifth page of Alt+2 - one wheel notch AWAY from you
    when the key opens. Any hotbox can now be one of a dial's sets: the
    wheel turns into it and back out of it. A fresh installation gets this
    layout; an existing one keeps its own Alt+2 until "Load default dials"
    (which now brings a dial's pages too) or the dial library. The hotbox
    is in the dial library as a dial of its own (Extra > Menus), and the
    three other viewport pages are under Extra > Viewport.
  - The script library has 102 scripts - 45 new, in four new groups:
      Modelling (advanced): select hard edges, edge loop, edge ring, a
        random 20 % of polygons, extrude, bevel, detach, make planar, bake
        TurboSmooth, symmetrize across the pivot, greeble, chamfer edges,
        connect edges, delete the -X half, bridge two borders.
      UV mapping: a 100-unit UVW box map, a capped cylindrical UVW map,
        unwrap and flatten, copy UVs to channel 2, a 2x finer checker.
      Layout and placement: snap to grid, arrange in a grid, stack up,
        align bottoms, drop onto a surface, spread along a line, jitter,
        scatter onto a surface.
      Cameras, lights and render: camera from the view, three-point
        lights, render size 1920 x 1080, lights on/off.
    And more in the old groups: random colour materials, merge same-named
    materials, the first one's material to all, wire colour from the
    material, rename in sequence, layers by object type, select a whole
    layer, delete empty layers, a scene report, a spline from edges,
    lighter splines, + Lathe, renderable 2 units thick. Each was run in
    3ds Max on a test scene and with nothing selected.

1.4.4 - a dial always closes; 57 scripts; load every dial
-------------------------------------------------------------------------------
  - A dial closes when you let go, even when 3ds Max does not report it.
    In some states 3ds Max switches its shortcuts off - measured after
    starting a Text object, when its own shortcuts stop too - and a dial
    opened just before could stay on screen after the key came up, with
    every other dial key doing nothing. MarkingForge now watches the key
    itself: up for a quarter of a second without word from 3ds Max, and the
    dial closes exactly as a release would have closed it.
    MarkingForge.eventLog() shows RELEASE_LOST when that happens.
  - The script library has 57 scripts - 32 new, in two new groups:
      Objects and pivots: pivot aligned to world, pivot to world origin,
        centre on the origin, attach to the first, split into elements.
      Topology: select faces facing up / down, cap holes, flip normals,
        clear smoothing.
      Modifiers: + Shell, + Symmetry, + Chamfer, + Edit Poly, + FFD 3x3x3.
      Materials and display: UV checker material, material = wire colour,
        backface cull on/off.
      Selection and transforms: select same type, select children, select
        without material, random rotation, random scale, spread evenly
        along X.
      Shapes and splines: renderable on/off, close all splines, + Extrude.
      Scene and layers: selection to a new layer, freeze selection, unfreeze
        all, zoom to selection, size to the status bar.
    Each was run in 3ds Max on a test scene and with nothing selected.
  - Load every dial... puts back a whole folder made by Save every dial... -
    what each dial showed, its sets in their order, the dials that showed
    the default menu and the colours of every dial. Scripts from the files
    are removed unless you keep them; a damaged file stops the whole load;
    nothing is written until Save.
  - Right-click a dial - in the list of dials or on its drawing - to save
    it, load a file into it, put a library dial on it, or save or load
    every dial.

1.4.3 - a brighter "Broken", and review fixes
-------------------------------------------------------------------------------
  The caption of a broken entry ("Broken")
  - It is BRIGHTER on dark tiles - the plugin's own look and all 25 dark
    ready-made looks. It was a dim salmon at 80 % opacity, the faintest
    caption on the dial (5:1 against its tile in Slate); it is now a light
    red at 96 %, at least 7:1 in every dark look, and still red.
  - On the light-tile looks it stays dark red - a light caption would vanish
    on a light tile. The 1.4.2 change that made it light there is undone: it
    was readable only on the red "aimed" tile, and an entry not aimed at
    sits on the light one.
  - The colour editor's preview put every broken entry on the red "aimed"
    tile. It now draws it as the plugin does - red only when aimed.
  - Every ready-made look is now checked on the pairs the plugin really
    draws, including the pointed list row and the hotbox.

  And a careful review of everything since 1.2.0 - the wheel that turns
  pages, the colours of each page and the presets. What it found, and what
  was done about it:

  The dials (the plugin)
  - Turning to a page with a WIDER caption left the dial invisible for the
    rest of the gesture, while releasing still ran the direction aimed at.
    The dial now stays on screen.
  - The wheel was held back from 3ds Max even when it could not turn a page
    (in a submenu, while a dial waited pinned, in search): the viewport's
    zoom did nothing. It is now taken only when it turns a page.
  - A fine wheel or a touchpad turned a page for every small step; it now
    turns one page per notch.
  - A page turn chose the dial's context variant at the moved cursor instead
    of where the gesture began - it could jump to another variant.
  - A quick second gesture could lose its page to the reset of the one
    before; a dial built live from 3ds Max now wears its dial's colours.
  - MARKINGFORGE_CONFIG_DIR: quotes are taken off, a relative path or a
    folder that does not exist is refused, and Diagnostics > Configuration
    status says which folder is in use and why.

  The editor
  - Colours... wrote back EVERY page that had been only looked at: choosing
    "every page" to look and then changing a global colour gave all pages
    the same colours, and a page painted before looking at another lost its
    paint. Only what was edited is written now.
  - Renaming the set whose tab was open sent the next edits to the set on
    the key; deleting it, or "Back to the default menu", left a stale tab.
    "Back to the default menu" also did not count as a change - closing
    without Save asked nothing and the deletion was lost.
  - The sets list shows the open tab's set, so Save dial, Rename and Delete
    act on the set you are looking at.
  - A colour preset file that cannot be read is left as it is and said so -
    the next Save used to replace every preset in it. Importing a preset
    with a name you already have keeps both ("Mine (2)"). A failed export is
    said, not only written to the Listener. An opaque colour in a preset of
    your own stays opaque.
  - A page the file names but does not hold no longer breaks Colours...;
    "Save every dial" writes "UV" and "uv" to two files.

  - The Reference Manual lists all the editor's ready-made looks (it said
    "two starting points"); the package check looks for every editor module.

1.4.2 - thirty dial looks, twenty-two editor looks
-------------------------------------------------------------------------------
  - Twelve more ready-made looks for the dials - Sapphire, Amethyst, Magenta,
    Coral, Sunset, Amber, Ruby, Storm, Carbon, Neon, and two with light
    tiles, Snow and Peach - thirty in all.
  - Eight more for the editor's own colours - Sapphire, Amethyst, Carbon,
    Storm, Burgundy, Slate grey, Dusk and Espresso - twenty-two in all.
  - The looks with light tiles keep two things readable that were not: the
    caption of a broken entry (now light on its red tile, as in the plugin's
    own look) and a toggle that is on (a darker shade of the tile instead of
    dark green under dark text).
  - A catalogue of every dial look on one picture - in the Editor Guide and
    in the store kit (images/09_dial_looks.png).

1.4.1 - more colour presets
-------------------------------------------------------------------------------
  - Eight more ready-made looks for the dials - Indigo, Twilight, Steel,
    Crimson, Copper, Gold, and two with light tiles and dark text, Ice and
    Lavender - eighteen in all.
  - Six more starting points for the editor's own colours - Charcoal, Steel
    blue, Indigo night, Mocha, Rose dust and Nord - fourteen in all.
  - Every ready-made look is checked for readable text: a caption against its
    tile, list text against its row, table text against its ground.
  - A short video of the colours - every page of a dial in its own preset,
    the colour editor and the editor's own looks - is in the store kit.

1.4.0 - colour presets, and colours for each page of a dial
-------------------------------------------------------------------------------
  - Colours... (the dials' palette) has PRESETS: ten ready-made looks -
    Graphite, Slate, Ocean, Violet, Rose, Ember, Mono, Sand with light tiles,
    High contrast and the default - and your own: "Presets > Save these
    colours as a preset...", Delete, and Export / Import of one preset as a
    .mfcolors file to take it to another computer.
  - A preset goes where you choose: every dial, one dial, or - for a dial with
    sets - every page of it or each page on its own (the sets the mouse wheel
    turns). A page's colours travel with it when it goes on the key.
  - A dial's own colours now reach its context variants and its submenus.
    Until now they stopped at the dial's base menu: "Poly: polygon" or a
    submenu came back in the colours of every dial.
  - Editor colours... has five more starting points (Graphite, Midnight blue,
    Warm sepia, Plum, Ocean) and your own presets, the same way.
  - MARKINGFORGE_CONFIG_DIR: when this environment variable names a folder
    that exists, 3ds Max reads and writes the dials there instead of in its
    plug-in configuration folder - for a test copy or a prepared studio set.

1.3.0 - the editor's own colours
-------------------------------------------------------------------------------
  - "Editor colours..." in the menu editor's bottom bar colours the editor's
    window itself - not the dials: the window's ground, its text and hints,
    each pane's colour and ground, the tables and lists (ground, every other
    row, text, the selected row, the column headers) and every column of
    every table on its own, text and ground. The editor changes as you pick;
    Cancel puts back what was there. Two starting points: High contrast and
    Calm grey.
  - Nothing is set until you choose it: an editor with no colours of its own
    looks exactly as before. The colours are kept in editor_colors.json
    beside menus.json - they are not part of your dials and need no Save.
  - Buttons, text fields, drop-down lists and check boxes keep 3ds Max's own
    look: a colour of ours on them takes their whole style away.

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
    on the Modifiers dial and in the Modelling pack: that modifier exists only
    in the 2027 release of 3ds Max. It is replaced by Quadify Mesh (Modifiers > Geometry)
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
  - Bug reports and feature requests: https://github.com/Forge-Plugins/MarkingForge/issues
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
