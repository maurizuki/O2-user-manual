---
title: Rules
nav_order: 8
has_children: true
---

# Rules
{: .no_toc }

Rules give fields behavior: hiding passwords, turning values into links, tracking dates, highlighting values. A rule belongs to the file and applies to every object, so you write it once and it covers all matching fields.

1. TOC
{:toc}

---

## How a rule works

Every rule has two masks:

- the **field name mask**, tested against the field's name;
- the **field value mask**, tested against the field's value.

A rule applies to a field only when **both** masks match. Matching ignores upper and lower case. Masks support wildcards: `*` matches any run of characters and `?` matches one character. See [Masks]({% link docs/rules/masks.md %}).

| Name mask | Value mask | Matches |
|:----------|:-----------|:--------|
| `password` | `*` | Every field named *Password*, whatever its value. |
| `*` | `https://*` | Every field whose value starts with `https://`. |
| `*` | `*@*` | Every value containing `@`, such as an e-mail address. |
| `*birth*` | `*` | *Date of birth*, *Birthday*, *Birth date*. |
| `address` | `*canada*` | *Address* fields that mention Canada. |

## Create a rule

1. Choose **New rule** from the **New** menu, or right-click the **Rules** tab and choose **New rule**.
2. In the **Rule properties** dialog, fill in the **General** page:
   - **Name**: a unique name for the rule.
   - **Type**: what the rule does. See [Rule types]({% link docs/rules/rule-types.md %}).
   - **Field name mask** and **Field value mask**. The help text on the page summarizes the mask syntax.
3. Fill in the extra pages for the chosen type (see below).
4. Click **OK**. New rules are enabled.

### Pages of the Rule properties dialog

Which pages appear depends on the rule type:

| Page | Shown for | Contents |
|:-----|:----------|:---------|
| **General** | All types | Name, type and masks. |
| **Internet link** | Internet link | The link **Mask**: a template that builds the address. See [Link macros]({% link docs/rules/macros.md %}#link-macros). |
| **Display** | Expiration date, Recurrence | The display **Mask**: how the value is shown in the **Fields** tab. See [Display macros]({% link docs/rules/macros.md %}#display-macros). |
| **Date format** | Expiration date, Recurrence | How to read dates in field values. |
| **Custom interval** | Expiration date, Recurrence | **Days before today** and **Days after today** for highlighting and the *Custom* event filter. |
| **Highlight** | Expiration date, Recurrence, Highlight | **Highlight color** and **Text color**. |
| **Password** | Password | **Display password strength**. |

## Manage rules

All rules are listed on the **Rules** tab. Right-click it for these commands:

| Command | Description |
|:--------|:------------|
| **New rule** | Create a rule. |
| **Duplicate** | Create a copy of the selected rule, to use as a starting point. |
| **Delete** | Delete the selected rules after confirmation. |
| **Move up** / **Move down** | Change the rule's position (**Ctrl+Shift+Up** / **Ctrl+Shift+Down**). |
| **Enable** / **Disable** | Turn the selected rules on or off. |
| **Select all**, **Deselect**, **Invert selection** | Change the selection. |
| **Properties** | Edit the selected rule. You can also double-click it. |

The check box next to each rule also turns it on or off. A disabled rule has no effect anywhere: no links, no hidden passwords, no events, no colors. Disabling is handy for trying out a rule without deleting it.

## Rule order

Rules are evaluated from top to bottom, so when several rules match the same field, order matters:

- **Display**: the first rule that changes how a value looks wins. For example, it hides a password or adds a countdown to a date.
- **Links**: the first matching *Internet link* rule builds the address.
- **Field colors**: the first rule that supplies a color wins.
- **Object colors**: in the objects list, an object takes the color of the highest rule that colors any of its fields.
- **iCalendar export**: the first matching event rule is used.

Put specific rules above general ones. For example, put a *Highlight* rule for `address` = `*canada*` above a catch-all *Highlight* rule for `address` = `*`.

{: .tip }
Rules aren't attached to objects, so changing a rule instantly changes how every matching field looks. To reuse a set of rules in another file, see [Import]({% link docs/import-export.md %}#import): rules are imported along with objects.
