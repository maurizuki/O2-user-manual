---
title: Core concepts
nav_order: 3
---

# Core concepts
{: .no_toc }

O2 has a small vocabulary. Once you know these terms, the rest of the program follows from them.

1. TOC
{:toc}

---

## File

Everything lives in a single **O2 file** (extension `.o2`). A file contains your objects, relations and rules, plus a few descriptive properties (title, description, author). The file is normally encrypted with a password. See [Files and encryption]({% link docs/files.md %}).

## Object

An **object** is one item in your archive: a person, an account, a credit card, a Wi-Fi network, a car. Each object has:

| Part | What it is |
|:-----|:-----------|
| **Name** | A unique name, shown in the objects list. Two objects in the same file can't share a name. |
| **Tags** | Zero or more labels that group objects, such as `Friends`, `Bank`, `Work`. |
| **Fields** | An ordered list of name–value pairs, such as `Phone` = `555-0165`. Field names must be unique within an object. |
| **Notes** | Free text, either plain text or [Markdown]({% link docs/markdown.md %}). |

O2 does not impose a structure. Two objects can have completely different fields. Use whatever field names make sense to you, but keep them consistent across similar objects: rules match fields by name, so consistent names let one rule cover many objects.

## Tag

A **tag** is a label attached to an object. An object can have many tags; O2 stores them as a comma-separated list. Tags let you [filter the objects list]({% link docs/search.md %}#find-by-tag) and sort it.

## Relation

A **relation** connects two objects, and gives each object a **role** in it. For example, a relation between *Frank* and *Pamela* could give Frank the role `husband` and Pamela the role `wife`. When you select either object, the relation appears on its **Relations** tab, showing the other object and its role. See [Relations]({% link docs/relations.md %}).

## Rule

A **rule** adds behavior to fields. Each rule has:

- a **type**, which decides what the rule does;
- a **field name mask** and a **field value mask**, which decide which fields the rule applies to.

A rule applies to a field when the field name matches the name mask *and* the field value matches the value mask. Masks use wildcards, so `*birth*` matches *Date of birth* and *Birthday*.

Rules belong to the file, not to individual objects, so a single rule applies across every object. The six rule types are:

| Type | Effect |
|:-----|:-------|
| **Internet link** | Makes the value a clickable link, optionally built from a template such as `tel:{fv}`. |
| **E-mail address** | Lets you send an e-mail to the value. |
| **Password** | Hides the value behind dots and can display its strength. |
| **Expiration date** | Treats the value as a one-time date and tracks it as an event. |
| **Recurrence** | Treats the value as a yearly date (birthday, anniversary) and tracks it as an event. |
| **Highlight** | Colors matching fields and objects. |

See [Rules]({% link docs/rules/index.md %}) and [Rule types]({% link docs/rules/rule-types.md %}).

## Event

An **event** is a date that O2 found in a field through an *Expiration date* or *Recurrence* rule. Events drive the **Next event** column, sorting by next event, the *Find by event* filter, and iCalendar export. See [Events and reminders]({% link docs/events.md %}).

## Selection

Many commands act on the **selected objects**. When no object is selected, commands such as print, export and the *Replace* commands act on **all objects currently shown** in the list, which respects any active search filter.
