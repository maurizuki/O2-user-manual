---
title: Finding objects
nav_order: 10
---

# Finding objects
{: .no_toc }

1. TOC
{:toc}

---

## Open the search pane

Click **Find** on the toolbar, or press **Ctrl+F**. The search pane opens on the right of the window. Click **Find** again to hide it.

The pane has four filters. The objects list updates as you change them, and shows only the objects that pass **all** active filters.

## Find by name

Type part of a name. The list shows objects whose name contains the text anywhere, ignoring case. For example, `van` finds both *Vanessa* and *Ivanov*.

## Find by event

Pick a time period to show only objects with an event in it, such as *Today*, *This week* or *Next 30 days*. Pick **All** to turn the filter off. See [Find by event]({% link docs/events.md %}#find-by-event) for the full list of options.

## Find by tag

Select one or more tags. The list shows objects that have **at least one** of the selected tags.

- Select **(none)** to include objects without tags.
- Select nothing to turn the filter off.
- Hold **Ctrl** to select several tags. Right-click the list for **Select all**, **Deselect** and **Invert selection**.

## Find by rule

Select one or more rules. The list shows objects that have at least one field matching a selected rule. Use it, for example, to list every object with a password, or every contact highlighted as living in a given country.

- For *Expiration date* and *Recurrence* rules, an object is shown only when its event is within the rule's custom interval.
- Disabled rules match nothing.
- Select nothing to turn the filter off. Right-click the list for **Select all**, **Deselect** and **Invert selection**.

## Clear the search

Open the **Find** menu and choose **Clear search** to reset all four filters and show every object again.

## Search and other commands

Many commands act on the selected objects or, when none are selected, on every object shown in the list. Because the list reflects the search, you can use filters to choose which objects to:

- [print or export to HTML]({% link docs/import-export.md %});
- [export]({% link docs/import-export.md %}#export) to another O2 file, XML or iCalendar;
- change with the [Replace commands]({% link docs/objects.md %}#bulk-changes).

{: .tip }
To export only your work contacts: filter by the tag `Co-workers`, make sure no object is selected, then export.
