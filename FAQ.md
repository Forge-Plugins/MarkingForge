# MarkingForge - frequently asked questions

Questions people ask before buying. Something missing? Ask on [Discord](https://discord.gg/HsakZWQZAw) or [open an issue](https://github.com/Forge-Plugins/MarkingForge/issues).

## Which versions of 3ds Max does it support - and with so many updates, is it safe for my work?

3ds Max 2025, 2026 or 2027 on Windows 64-bit - each version has its own download, and its installer checks the version and will not install into another one. 3ds Max 2024 and earlier may follow if enough users ask for them. Your scenes stay yours: by default MarkingForge writes nothing into your .max files - a scene saved with it opens normally without it - and it runs 3ds Max's own commands, so undo works as usual. The frequent updates come from users' reports and code reviews; every release is tested with real keyboard and mouse input in all three versions, and the full changelog is public. No crash has been traced to MarkingForge so far; if 3ds Max ever crashes or freezes, MarkingForge keeps a short log of its last actions on your computer (event_log.txt beside menus.json), which helps find the cause. Nothing is ever sent anywhere.

## How is it different from 3ds Max's quad menu or a free pie-menu script?

A quad menu has to be read and clicked; a marking menu is aimed by direction, so after a few days you flick without looking - and a quick flick runs the command without the dial being drawn at all. The dials change with what you edit (each sub-object level, splines, the editors), four live dials show your modifier stack, undo history, recent commands and selection sets, and it is native C++, not a script.

## Does it work with several monitors, Windows scaling and high-refresh screens?

Yes. The dial opens on the screen the cursor is on and follows Windows scaling (tested at 100 and 150 %). Since 1.5.92 it draws at the refresh rate of its screen - about every 5 ms on a 180 Hz monitor, every 16 ms on a 60 Hz one.

## What are the Experimental features - do I need them?

No. They are optional extras, each switched on with one tick in MarkingForge > Experimental features - Maya's marking menu look, type-to-search, a tap that repeats the last modelling command, several picks in one gesture and more. The defaults are what most people want; try one at a time.

## How do I uninstall it?

Run the installer again and choose Uninstall: it removes MarkingForge's files from 3ds Max (for the current user and for all users). Your dials and settings are kept apart, so a later install brings them back, and your own shortcuts and quad menus are never touched. The Installation Guide shows every step.

## Will it change or remove my keyboard shortcuts?

No. It only offers the standard keys (Alt, Ctrl+Alt and Shift+Alt with 1-8) to dials that have no key yet, skips any key you already use, and backs up your shortcuts before every change.

## Does it work with V-Ray, Corona, Arnold and other plugins?

Yes. MarkingForge does not depend on the renderer. Any command 3ds Max lists - including commands other plugins add - can go on a dial, and the hotbox shows other plugins' menus too.

## Do I need to know MAXScript?

No. The 24 built-in dials work out of the box, and the menu editor assigns any command by clicking or dragging. Scripts are optional - and the script library has 102 ready-made ones, each tested in 3ds Max, to put on a dial with one click.

## I come from Maya. Will it feel familiar?

Yes - hold, aim, release, flick without looking, eight directions with extra rows, a hotbox you can put on Space. One tick (Experimental features > Maya marking menu look) draws every dial as Maya's marking menu - grey boxes round a centre dot, Maya's option boxes, no disc. A dedicated guide maps Maya habits to MarkingForge.

## Is it fast?

The dial is drawn by native C++ code with Qt; its first pixel appears in about 3 ms (median, measured on the 2027 release of 3ds Max). A held key with the mouse still opens it after 100 ms - 3ds Max alone would wait 250 ms - and you can set 0 to 250 ms. With a flick it is not drawn at all.

## Does it connect to the internet or collect data?

No. There is no licence server and no telemetry. Usage counters stay on your computer.

## How many computers can I use it on?

One licence is for one person, who may use it on up to two of their computers (for example a workstation and a laptop). Studios need one licence per person.

## Are updates included?

All 1.x updates are included. Install a new version over the old one - your dials and shortcuts are kept.

## Can a studio deploy it to many workstations?

Yes. A deployment script installs silently for all users, can give everybody the same dial layout and the standard shortcuts, and uninstalls cleanly. See the Studio Deployment Guide.

## What if it does not work on my system?

Write to forgeplugins@gmail.com. If it cannot be solved, you get a refund within 14 days of purchase.

## Where do I report a bug or ask for a new feature?

Open an issue at https://github.com/Forge-Plugins/MarkingForge/issues (bug report and feature request forms), or write to forgeplugins@gmail.com. In 3ds Max, MarkingForge > Report a bug... puts your version details on the clipboard, ready to paste. Every message is read.

## Can I undo what a gesture did?

Yes - every command undoes with Ctrl+Z as usual, and a chain of several picks undoes as one step. A chain that waits for your drag (Inset, then Extrude) undoes one tool at a time.
