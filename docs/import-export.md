---
title: Import, export and print
nav_order: 11
---

# Import, export and print
{: .no_toc }

1. TOC
{:toc}

---

## Which objects are included

Export, Export to HTML and Print all work on the **selected objects**. If no object is selected, they include **every object shown in the list**, which respects the current [search filter]({% link docs/search.md %}).

## Import

Import merges another file into the one you have open. Your current file is not replaced.

1. Open the **Open** menu and choose **Import**.
2. Pick the file type, **O2 file** or **XML file**, and select the file. If the O2 file is encrypted, enter its password.

What gets merged:

| Item | Behavior |
|:-----|:---------|
| **Objects** | An object that already exists in your file, because it was originally exported from it, is updated with the imported version. Other objects are added. |
| **Relations** | Same as objects: existing relations are updated, new ones are added. |
| **Rules** | A rule with the same name as one of yours replaces it. Other rules are added. |
| **Title, description, author** | Imported only if they're empty in your file. |

{: .note }
Object names must stay unique. If a new object being imported has the same name as a different object in your file, O2 reports that the name already exists. Rename one of the two objects and import again.

{: .tip }
Import is an easy way to reuse rules: keep a small O2 file that contains only your favorite rules, and import it into new files.

## Export

1. Optionally, select the objects to export or set a search filter.
2. Open the **Save** menu and choose **Export**.
3. Pick a file type, choose a name and click **Save**.

| File type | Contents |
|:----------|:---------|
| **O2 file** | The objects, the relations between them, all rules, and the file's title, description and author. Open it in O2 or import it into another file. |
| **XML file** | The same contents in XML format, readable by other programs. The format is described by the [O2 file XML schema](https://maurizuki.github.io/O2/xml/O2File/30.xsd). |
| **iCalendar file** | The events of the objects, for calendar programs. See [Send events to your calendar]({% link docs/events.md %}#send-events-to-your-calendar). |

{: .warning }
Exported files are **not encrypted**, including O2 files. Anyone who gets them can read everything in them, passwords included. To protect an exported O2 file, open it in O2 and use **Save as** to save it with a password. Delete exported XML and iCalendar files when you no longer need them.

## Export to HTML

Creates a web page with the details of your objects, ready to view in a browser, share or print.

1. Open the **Save** menu and choose **Export to HTML**.
2. A preview window opens. Adjust it with the toolbar:
   - **Options**: choose what to include. Every option is on by default.

     | Option | Includes |
     |:-------|:---------|
     | **Include index** | A list of object names at the top, linking to each object. |
     | **Include tags** | Each object's tags. |
     | **Include notes** | Each object's notes, formatted when they use Markdown. |
     | **Include relations** | Each object's related objects and their roles. |
     | **Include passwords** | Fields that match a *Password* rule, in clear text. When off, those fields are left out. |

     Fields that match an *Internet link* or *E-mail address* rule become clickable links in the page.

   - **Style**: pick a look for the page. Built-in styles are *Blue Water*, *Matcha*, *Sakura* and *Call of the Night* (dark). A full installation adds *Blocks*, *Mono* and *Sticky Notes*.
3. Click **Export** and choose where to save the `.html` file.

O2 remembers your options and style for next time. The page title comes from the file's **Title** in [File properties]({% link docs/files.md %}#file-properties), or from the file name when the title is empty.

{: .warning }
**Include passwords** is on by default. Turn it off before exporting a page you plan to share.

### Custom styles

Every `.css` file in the **Styles** folder of the O2 installation (by default `C:\Program Files\O2\Styles`) appears in the **Style** menu, named after the file. To make your own style, copy one of the included files, rename it and edit it.

## Print

1. Click **Print** on the toolbar, or press **Ctrl+P**. A preview window opens.
2. Adjust the preview with the toolbar:
   - **Zoom**: *Whole page*, *Page width*, or 25% to 400%.
   - **Options**: **Include tags**, **Include notes**, **Include relations**, **Include passwords**. Every option is on by default.
3. The status bar shows the number of pages. Click **Print** to choose a printer and print.

O2 remembers your print options.

{: .warning }
**Include passwords** is on by default for printing too. Turn it off if the printout might be seen by others.
