---
title: Tools and preferences
nav_order: 12
---

# Tools and preferences
{: .no_toc }

The **Tools** button on the toolbar opens a menu with file properties, window options, settings and updates.

1. TOC
{:toc}

---

## File properties

Edit the title, description and author of the open file, and see its encryption settings. See [File properties]({% link docs/files.md %}#file-properties).

## Window options

### Transparency

**Tools > Transparency** makes the O2 window see-through, from **0%** (opaque) to **90%**.

Check **Only if deactivated** to apply transparency only while you're working in another window. O2 becomes opaque again as soon as you switch back to it.

### Always on top

**Tools > Always on top** keeps the O2 window above other windows. Handy when you're copying values from O2 into another program.

## Settings

O2 remembers your preferences between sessions: window options, view style and sorting, recent files, update checks, and HTML export and print options. They're saved in `O2.xml` in the `%APPDATA%\O2` folder.

To move your preferences to another computer or back them up:

- **Tools > Export settings** saves them to an XML file of your choice.
- **Tools > Import settings** loads them from such a file.

Settings don't contain your O2 data or passwords, but they do list the paths of your recently used files.

## Updates

- **Tools > Check for updates now** checks whether a newer version of O2 is available. If one is, O2 offers to open its download page.
- **Tools > Check for updates periodically**, on by default, makes O2 check silently once a day, telling you only when an update is available.

Checking for updates requires an internet connection.

## Install on removable media

O2 can copy itself to a USB stick, external disk or memory card, so you can carry it, and your files, to other computers without installing anything there.

1. Plug in the removable drive.
2. Choose **Tools > Install on removable media**. The dialog shows how much free space is needed.
3. Select or create the destination folder and click **OK**.

The portable copy is started with `O2Portable.exe` in the destination folder. It keeps its settings on the removable drive, in the `Data\Settings` folder, instead of on the computer. Custom HTML export styles go in its `App\O2\Styles` folder.

{: .note }
The portable copy still needs Microsoft Edge WebView2 Runtime on the computer where it runs.

## About O2

**Help > About O2** shows the version number, license and credits.
