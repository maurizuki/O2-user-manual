---
title: Objects, fields and tags
nav_order: 6
has_children: true
---

# Objects, fields and tags
{: .no_toc }

1. TOC
{:toc}

---

## Create an object

1. Choose **New object** from the **New** menu or the object menu, or press **Ctrl+Shift+N**.
2. Fill in the **Object properties** dialog, described below.
3. Click **OK**. The new object is added to the list and selected.

## The Object properties dialog

Open it to create an object, or to edit one by double-clicking it, pressing **Enter**, or choosing **Properties** from the object menu. When you edit an object, the dialog opens on the page that matches the tab you were viewing: **Fields** or **Notes**.

The **Help** button, at the bottom left of the dialog, opens this page of the online manual.

### General page

- **Name**: the object's name. It must be unique in the file. If another object already has the name, O2 reports *An object named "…" already exists.*
- **Tags**: the list shows every tag used in the file. Click tags to select the ones that apply to this object; hold **Ctrl** to select more than one. To create a tag, type it in the *New tag* box and click **Add**.

### Fields page

The list shows the object's fields in order. Below the list are two boxes, *Field name* and *Field value*, which suggest names and values already used in the file.

| Button | Action |
|:-------|:-------|
| **Add** | Add a field with the name and value typed in the boxes. |
| **Replace** | Replace the selected field with the name and value in the boxes. |
| **Delete** | Delete the selected field. |
| **▲** / **▼** | Move the selected field up or down. |

Each field name can appear only once per object.

When a field matches a *Password* rule, a password strength indicator appears under the value box. See [Password]({% link docs/rules/rule-types.md %}#password).

{: .tip }
Keep field names consistent across objects, for example always `Phone` and never `Tel.` in some objects. A rule written for `phone` then works everywhere.

### Notes page

Type free-form notes about the object.

- Check **Markdown syntax** to format the notes with Markdown: headings, **bold**, *italic*, lists, links, tables and horizontal rules. See [Markdown in notes]({% link docs/markdown.md %}) for everything O2 supports.
- Leave it unchecked for plain text.

The **Notes** tab in the main window shows the notes, formatted when Markdown is on.

## Duplicate an object

Select an object and choose **Duplicate** from the object menu. The **Object properties** dialog opens with a copy of the object's tags, fields and notes. Give it a new name and click **OK**.

## Rename an object

Select an object and press **F2**, or choose **Rename** from the object menu. Type the new name in place and press **Enter**. If the name is already in use, the old name is restored.

## Delete objects

Select one or more objects and choose **Delete** from the object menu. O2 asks *Delete selected objects?*. Deleting an object also deletes all its relations.

## Select objects

- Click to select one object; **Ctrl+click** to add or remove objects; **Shift+click** to select a range.
- **Select all** (**Ctrl+A**), **Deselect** and **Invert selection** are in the object menu.

## Tags

### Tag one object

Choose **Edit tags** from the object menu. The **Object properties** dialog opens on the **Tags** box.

### Tag many objects at once

1. Select the objects.
2. Right-click and open **Add tag**, then pick a tag. The tag is added to every selected object.

To remove a tag, open **Delete tag** and pick it. The list shows the tags used by the selected objects.

## Bulk changes

The *Replace* commands in the object menu change many objects at once. They act on the selected objects or, when nothing is selected, on all objects shown in the list.

| Command | Fields in the dialog | Effect |
|:--------|:---------------------|:-------|
| **Replace tag** | *Tag*, *New tag* | Renames a tag. |
| **Replace field name** | *Field name*, *New field name* | Renames a field. |
| **Replace field value** | *Field name*, *New field value* | Sets the value of a field. |
| **Replace role** | *Role*, *New role* | Renames a role in the objects' relations. |

{: .tip }
Combine bulk changes with the [search pane]({% link docs/search.md %}). For example, filter by the tag `Old bank`, leave nothing selected, then use **Replace field value** to update the `Branch` field of every matching account.

## Use field values

### Copy field values

Double-click a field, or select it and press **Enter**, to copy its value. Right-click the **Fields** tab for more copy formats, grouped in submenus.

**Copy field value** copies the selected field's value.

The **Copy field name and value**, **Copy field values** and **Copy fields** submenus use tabs and line breaks, so the result pastes cleanly into a spreadsheet:

| Submenu | Command | Copies |
|:--------|:--------|:-------|
| **Copy field name and value** | **One row** | The selected field's name and value on one line, separated by a tab. |
| | **One column** | The selected field's name, then its value on the next line. |
| **Copy field values** | **One value per row** | All values, one per line. |
| | **One value per column** | All values on one line, separated by tabs. |
| **Copy fields** | **One field per row** | All fields, one per line, name and value separated by a tab. |
| | **One field per column** | All names on one line and all values on the next. |

The **Copy as table** submenu copies all fields as a table, ready to paste into a document, an e-mail or a Markdown file:

| Command | Table layout |
|:--------|:-------------|
| **One field per row** | Two columns, headed *Field* and *Value*, with one row per field. |
| **One field per column** | One column per field, headed by the field name, with the values in a single row. |

The table is copied in two formats at once, and the program you paste into picks the one it supports:

- **HTML**, for programs that accept formatted text, such as Word, Outlook or OneNote. The table keeps its rows, columns and header.
- **Markdown**, for plain-text editors. The table is written with pipes (`|`); pipe characters inside values are written as `&#124;` so they don't break the table.

Copy commands always copy the real value, including passwords hidden behind dots.

### Open links and send e-mail

- **Open link** opens the field in your browser or in the program associated with the link type, such as `tel:` or `mailto:`. It appears for fields that match an *Internet link* rule.
- **Send e-mail** starts a new message in your e-mail program, addressed to the field value. It appears for fields that match an *E-mail address* rule.

**Ctrl+click** a field to do the same thing.

### Show passwords

Fields that match a *Password* rule are shown as dots. Right-click the **Fields** tab and choose **Show passwords** to show the real values. Choose it again to hide them.
