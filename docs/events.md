---
title: Events and reminders
nav_order: 9
---

# Events and reminders
{: .no_toc }

O2 can track dates stored in your fields, such as document expiries, renewals, birthdays and anniversaries, and show you what's coming up.

1. TOC
{:toc}

---

## How events are created

Events come from rules. A field becomes an event when it matches an enabled rule of type:

- **Expiration date**: a single date, such as `Passport expiry` = `05/31/2029`;
- **Recurrence**: a date that repeats every year, such as `Date of birth` = `02/28/1987`.

The field value must be a date that the rule can read with its [date format]({% link docs/rules/rule-types.md %}#date-format-page). Set up a rule once, and every matching field in every object becomes an event.

### Example: birthdays

1. Choose **New rule**.
2. **Name** `Birthday`, **Type** *Recurrence*, **Field name mask** `*birth*`, **Field value mask** `*`.
3. On **Date format**, choose the order you use to type dates, such as *Month, day, year*, and the separator, such as `/`.
4. Optionally, on **Display**, set the mask to `{fv} ({years} years)`.
5. Click **OK**.

Every object with a field like *Date of birth* or *Birthday* now has an event.

## Next event column

In the **Report** view, the **Next event** column shows each object's nearest event date:

- for an *Expiration date* field: the date itself;
- for a *Recurrence* field: the next anniversary.

When an object has several events, the earliest one is shown.

## Upcoming events first

Choose **View > Sort by next event**, or click the **Next event** column header, to put the nearest events at the top. Choose it again to reverse the order.

{: .tip }
Combine **Sort by next event** with the *Find by event* filter set to *Next 30 days* for a quick agenda of the coming month.

## Highlighting

A field with an event is highlighted, together with its object, while the event falls within the rule's **custom interval**: by default, from 60 days before the date until 15 days after it. Change the interval on the rule's **Custom interval** page, and the colors on its **Highlight** page.

## Countdown and age

In the **Fields** tab, the rule's display mask adds information to the date:

- *Expiration date*: days left, while the date is still ahead. For example `05/31/2029 (923)`.
- *Recurrence*: years elapsed, once the date is in the past. For a birth date, that's the person's age, for example `02/28/1987 (39)`.

See [Display macros]({% link docs/rules/macros.md %}#display-macros) to customize the text.

## Find by event

The **Find by event** box in the [search pane]({% link docs/search.md %}) shows only objects with an event in a given period:

| Option | Shows objects with an event… |
|:-------|:-----------------------------|
| **All** | No filter: all objects are shown, with or without events. |
| **All events** | At any date. Objects without events are hidden. |
| **Custom** | Within each rule's own custom interval: the same events that are highlighted. |
| **Today**, **Tomorrow** | On that day. |
| **This week**, **This month**, **This year** | In the current calendar week, month or year. |
| **Next 7 / 15 / 30 / 60 / 90 / 180 / 365 days** | Between today and that many days from now. |

For *Recurrence* rules, the anniversary of the date is used, so a birthday in 1987 counts as an event this year.

## Send events to your calendar

Export events to an iCalendar (`.ics`) file to import them into Outlook, Google Calendar, Apple Calendar and other calendar programs:

1. Select the objects whose events you want, or select none to export every object shown in the list.
2. Open the **Save** menu and choose **Export**.
3. Set the file type to **iCalendar file**, choose a name and click **Save**.

Each event becomes an all-day calendar entry titled *object name – field name*. *Recurrence* events repeat every year. Entries are marked private and don't block time in your calendar.
