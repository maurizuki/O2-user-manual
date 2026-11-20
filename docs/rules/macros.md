---
title: Macros
parent: Rules
nav_order: 3
---

# Macros
{: .no_toc }

Macros are placeholders, written between braces, that O2 replaces with real values. They're used in the link mask of *Internet link* rules and in the display mask of *Expiration date* and *Recurrence* rules. Click the **Macros** button next to a mask to insert one.

1. TOC
{:toc}

---

## Link macros

Used in the **Mask** on the *Internet link* page of the **Rule properties** dialog, to build the address that opens when you **Ctrl+click** a field.

| Macro | Replaced by |
|:------|:------------|
| `{fv}` | The field value, URL-encoded. |
| `{fn}` | The field name, URL-encoded. |

When the mask is empty, the field value is used as the address unchanged.

The older forms `<fieldvalue>` and `<fieldname>` still work, for compatibility with files created by earlier versions of O2.

**Examples**

| Link mask | Field | Opens |
|:----------|:------|:------|
| `tel:{fv}` | Phone = `922-555-0165` | `tel:922-555-0165` |
| `https://maps.google.com/?q={fv}` | Address = `636 Vine Hill Way, Portland` | A map of the address. |
| `https://www.google.com/search?q={fn}+{fv}` | Model = `XR-200` | A search for *Model XR-200*. |

## Display macros

Used in the **Mask** on the *Display* page of *Expiration date* and *Recurrence* rules, to set how the date appears in the **Fields** tab. Time spans are counted between today and the date in the field.

| Macro | Replaced by |
|:------|:------------|
| `{fv}` | The field value. |
| `{fn}` | The field name. |
| `{years}` | Whole years. |
| `{monthsof}` | Months left over after the whole years (0–11). |
| `{daysof}` | Days left over after the whole months (0–30). |
| `{months}` | Total whole months. |
| `{days}` | Total days. |

When the mask is empty, O2 uses `{fv} ({days})` for *Expiration date* rules and `{fv} ({years})` for *Recurrence* rules.

The results below assume today is November 20, 2026.

**Examples** for a birth date field, using a *Recurrence* rule:

| Display mask | Result |
|:-------------|:-------|
| *(empty, the default)* | `02/28/1987 (39)` |
| `{fv} ({years} years)` | `02/28/1987 (39 years)` |
| `{years} years, {monthsof} months` | `39 years, 8 months` |

**Examples** for an expiry date field, using an *Expiration date* rule:

| Display mask | Result |
|:-------------|:-------|
| *(empty, the default)* | `03/15/2027 (115)` |
| `{fv}, {days} days left` | `03/15/2027, 115 days left` |
| `{fv} (in {months} months)` | `03/15/2027 (in 3 months)` |

{: .note }
The display mask applies only while the date is upcoming (*Expiration date*) or already passed (*Recurrence*). Otherwise the value is shown unchanged.
