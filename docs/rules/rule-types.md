---
title: Rule types
parent: Rules
nav_order: 1
---

# Rule types
{: .no_toc }

1. TOC
{:toc}

---

## Internet link

Turns matching field values into links. **Ctrl+click** the field, or choose **Open link** from its menu, to open the link in the associated program: your browser for `https://` addresses, your phone app for `tel:` and so on.

**Internet link page**

- **Mask**: a template for the address. Leave it empty to use the field value as it is. Otherwise, use the macros `{fv}` (field value) and `{fn}` (field name); click **Macros** to insert them. Macro values are URL-encoded, so spaces and special characters are safe. See [Link macros]({% link docs/rules/macros.md %}#link-macros).

**Examples**

| Rule | Field name mask | Field value mask | Link mask |
|:-----|:----------------|:-----------------|:----------|
| Web address | `*` | `https://*` | *(empty)* |
| Phone | `phone` | `*` | `tel:{fv}` |
| Map | `address` | `*` | `https://maps.google.com/?q={fv}` |
| Wikipedia | `wiki` | `*` | `https://en.wikipedia.org/wiki/{fv}` |

With the *Map* rule, a field `Address` = `10203 Acorn Avenue, Calgary` opens a map of that address.

## E-mail address

Marks matching fields as e-mail addresses. **Ctrl+click** the field, or choose **Send e-mail** from its menu, to write a message to that address in your default e-mail program.

This type has no extra settings. A typical rule uses field name mask `*` and field value mask `*@*`.

## Password

Hides matching values behind dots (`●●●●●●●●`) in the **Fields** tab. To see them, choose **Show passwords** from the **Fields** menu. Copy commands still copy the real value.

**Password page**

- **Display password strength**: when checked, the field is colored by the password's strength. The object is colored in the objects list too.

  | Color | Strength |
  |:------|:---------|
  | Red | Very weak |
  | Orange | Weak |
  | Yellow | Fair |
  | Blue | Strong |
  | Green | Very strong |

  The strength estimate takes into account common passwords, names, dictionary words, dates, keyboard patterns and repetitions.

When you edit an object, any field that matches a *Password* rule shows a strength indicator in the **Object properties** dialog.

**Example**: field name mask `*password*`, field value mask `*`. This also covers *Wi-Fi password* and *Password (old)*.

{: .note }
A *Password* rule only hides the value on screen. Real protection comes from [encrypting the file]({% link docs/files.md %}#encryption). Also note that printing and HTML export include passwords unless you turn that option off.

## Expiration date

Treats matching values as one-time dates, such as a passport expiry, a warranty end or a contract renewal, and tracks them as [events]({% link docs/events.md %}).

- **Display**: while the date is today or later, the **Fields** tab shows it with a countdown. With the default display mask, `12/31/2027` shows as something like `12/31/2027 (406)`, meaning 406 days left. After the date passes, the value is shown unchanged.
- **Highlight**: the field and its object are highlighted while the date is within the [custom interval](#custom-interval-page).

Uses the **Display**, **Date format**, **Custom interval** and **Highlight** pages.

**Example**: field name mask `*expir*`, field value mask `*`.

## Recurrence

Treats matching values as yearly dates, such as birthdays and anniversaries, and tracks the next occurrence as an [event]({% link docs/events.md %}).

- **Display**: once the date is today or in the past, the **Fields** tab shows it with the time elapsed. With the default display mask, a birth date `02/28/1987` shows as `02/28/1987 (39)`, the person's age. A display mask such as `{fv} ({years} years)` gives `02/28/1987 (39 years)`.
- **Highlight**: the field and its object are highlighted while this year's (or next year's) anniversary is within the [custom interval](#custom-interval-page).
- **iCalendar export**: exported as a yearly repeating event.

Uses the **Display**, **Date format**, **Custom interval** and **Highlight** pages.

**Examples**: `*birth*` / `*` for birthdays; `*wedding*` / `*` for wedding anniversaries.

## Highlight

Colors matching fields, and the objects that contain them, with the colors on the **Highlight** page. Use it to make values stand out, such as contacts in a given country, or accounts at a given bank.

**Example**: field name mask `address`, field value mask `*australia*`, light blue highlight.

---

## Settings pages for date rules

The *Expiration date* and *Recurrence* types share these pages.

### Display page

- **Mask**: how the value is shown in the **Fields** tab. Click **Macros** to insert a macro. Leave it empty to use the default: `{fv} ({days})` for *Expiration date*, `{fv} ({years})` for *Recurrence*. See [Display macros]({% link docs/rules/macros.md %}#display-macros).

### Date format page

Tells O2 how to read the dates typed in field values.

- **Date format**: *Year, month, day*, *Month, day, year* or *Day, month, year*.
- **Date separator**: the character between the parts, such as `/`, `-` or `.`.

Both default to your Windows regional settings. For example, to read `28.02.1987`, choose *Day, month, year* and separator `.`.

{: .important }
A value that can't be read as a date with these settings is ignored by the rule: it has no countdown, no event and no highlight. If a date doesn't show up as an event, check this page first.

### Custom interval page

Sets the window around today in which the event counts as "close":

- **Days before today**: default 15.
- **Days after today**: default 60.

This window controls:

- when the field and object are **highlighted**;
- what the **Custom** option of *Find by event* shows;
- what *Find by rule* shows for this rule.

With the defaults, a birthday is highlighted from 60 days before it until 15 days after it.

### Highlight page

- **Highlight color**: the background color. Default yellow.
- **Text color**: the text color. Default black.

This page also appears for *Highlight* rules.
