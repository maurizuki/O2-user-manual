---
title: Masks
parent: Rules
nav_order: 2
---

# Masks
{: .no_toc }

The **Field name mask** and **Field value mask** of a rule decide which fields it applies to. A rule applies to a field only when the field name matches the name mask *and* the field value matches the value mask.

1. TOC
{:toc}

---

## Mask syntax

A mask is made of literal characters, wildcards and sets. All comparisons ignore case.

### Literal characters

Each literal character matches the same single character. `phone` matches *Phone* and *PHONE*, but not *Phone 2* or *Mobile phone*.

### Wildcards

| Wildcard | Matches | Example | Matches | Doesn't match |
|:---------|:--------|:--------|:--------|:--------------|
| `*` | Any number of characters, including none. | `*phone*` | *Phone*, *Mobile phone*, *Phone 2* | *Tel.* |
| `?` | Exactly one character. | `pin?` | *PIN1*, *PIN2* | *PIN*, *PIN12* |

### Sets

A set, written between square brackets, matches **one** character from a list:

- List the characters: `[abc]` matches *a*, *b* or *c*.
- Give a range with a dash: `[0-9]` matches any digit, `[a-f]` any letter from *a* to *f*.
- Combine them, without spaces or commas: `[0-9a-f]`.
- Start with `!` to match any character *not* in the set: `[!0-9]` matches anything but a digit.

## Examples

| Purpose | Name mask | Value mask |
|:--------|:----------|:-----------|
| Any field | `*` | `*` |
| Fields named *Password* | `password` | `*` |
| Web addresses | `*` | `http*://*` |
| E-mail addresses | `*` | `*@*` |
| Fields named *Phone*, *Phone 2*, *Mobile phone* | `*phone*` | `*` |
| *Date of birth*, *Birthday*, *Birth date* | `*birth*` | `*` |
| Addresses in Canada | `address` | `*canada*` |
| Dates written as `mm/dd/yyyy` | `*date*` | `[0-1][0-9]/[0-3][0-9]/[1-2][0-9][0-9][0-9]` |
| Italian mobile numbers | `*phone*` | `+39 3*` |
| Values that don't start with a digit | `*` | `[!0-9]*` |

{: .tip }
Masks match field names, so they work best when you name fields consistently across objects. A rule for `phone` won't catch a field you called `Tel.`.
