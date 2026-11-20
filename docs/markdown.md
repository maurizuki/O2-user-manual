---
title: Markdown in notes
parent: Objects, fields and tags
nav_order: 1
---

# Markdown in notes
{: .no_toc }

Object notes can be written in Markdown, a simple way to format text with ordinary characters. O2 follows the [CommonMark](https://commonmark.org/) standard, plus the GitHub-style extensions for tables, strikethrough and automatic links.

1. TOC
{:toc}

---

## Turn on Markdown

1. Open the object's **Properties** and go to the **Notes** page.
2. Check **Markdown syntax**.
3. Write your notes and click **OK**.

The setting is per object. With the box unchecked, notes are plain text: shown in a fixed-width font, exactly as typed, with spaces and line breaks preserved.

The **Markdown syntax help** link on the **Notes** page opens a short CommonMark reference.

## Where Markdown is rendered

| Place | Result |
|:------|:-------|
| **Notes** tab of the main window | Formatted. |
| [Export to HTML]({% link docs/import-export.md %}#export-to-html) | Formatted, using the chosen style. |
| [Print]({% link docs/import-export.md %}#print) | Not formatted: the text is printed as typed, Markdown symbols included. |

## Text

### Paragraphs and line breaks

Separate paragraphs with a blank line. Lines with no blank line between them are joined into one paragraph.

To break a line without starting a new paragraph, end it with two spaces or a backslash (`\`).

~~~
First line\
Second line, same paragraph.

A new paragraph.
~~~

### Emphasis

| You type | You get |
|:---------|:--------|
| `*italic*` or `_italic_` | *italic* |
| `**bold**` or `__bold__` | **bold** |
| `***bold italic***` | ***bold italic*** |
| `~~strikethrough~~` | ~~strikethrough~~ |
| `` `code` `` | `code` |

### Headings

Start a line with one to six `#` characters, followed by a space:

~~~
# Heading 1
## Heading 2
### Heading 3
~~~

You can also underline a line with `===` for a level 1 heading, or `---` for a level 2 heading.

### Special characters

To show a character that Markdown would otherwise interpret, such as `*`, `_`, `#` or `|`, put a backslash in front of it: `\*not italic\*`.

HTML entities such as `&copy;`, `&euro;` and `&nbsp;` are converted to the corresponding character.

## Lists

### Bulleted lists

Start each item with `-`, `*` or `+` and a space. Indent items to nest them:

~~~
- Passport
- Driving license
  - Category B
  - Category A
~~~

### Numbered lists

Start each item with a number, a period and a space. The list starts from the first number you write:

~~~
3. Third step
4. Fourth step
~~~

## Block quotes

Start lines with `>`:

~~~
> The PIN was changed at the branch on 3 March.
~~~

## Code

Indent lines by four spaces, or wrap them in a fence of three backticks (```` ``` ````) or three tildes (`~~~`). The text is shown in a fixed-width font, exactly as typed.

````
```
ssid: HomeNetwork
security: WPA3
```
````

## Horizontal rules

A line containing only `---`, `***` or `___` draws a horizontal rule.

## Links

| You type | Result |
|:---------|:-------|
| `[O2 home page](https://maurizuki.github.io/O2)` | A link with your own text. |
| `[O2](https://maurizuki.github.io/O2 "Visit O2")` | The same, with a tooltip. |
| `<https://maurizuki.github.io/O2>` | The address itself, as a link. |
| `<jane.doe@example.com>` | An e-mail link. |
| `https://maurizuki.github.io/O2` | Plain addresses starting with `http://`, `https://`, `ftp://` or `www.` become links automatically. |
| `jane.doe@example.com` | Plain e-mail addresses become links automatically too. |

Links open in a separate window.

## Images

`![Router label](https://example.com/router-label.png)` displays the image at that address. Images are loaded from the internet, so they appear only when you're online.

## Tables

Separate cells with `|`, and put a line of dashes under the header row:

~~~
| Card    | Expires | Limit  |
|:--------|:-------:|-------:|
| Visa    | 05/29   | 5,000  |
| Amex    | 11/27   | 10,000 |
~~~

Colons in the dash line set the alignment of each column:

| Dash line | Alignment |
|:----------|:----------|
| `:---` | Left |
| `:---:` | Center |
| `---:` | Right |
| `---` | Default |

The pipes at the start and end of each row are optional. To put a `|` inside a cell, write `\|`.

## Not supported

These Markdown features are not available in O2 notes:

| Feature | What happens |
|:--------|:-------------|
| HTML tags, such as `<b>` or `<div>` | Shown as text, not interpreted. |
| Reference-style links, such as `[text][1]` with `[1]: https://…` on another line | Not turned into links. Use inline links instead. |
| Task lists, such as `- [ ] item` | Shown as an ordinary list item with literal brackets. |
| Footnotes | Not supported. |

## Example

This note, from the *AddressBook.o2* example file:

~~~
She and her husband __Frank__ have two children:
- __Vanessa__, the _eldest daughter_.
- __Frank Jr.__, the younger one.
~~~

is displayed as:

> She and her husband **Frank** have two children:
> - **Vanessa**, the *eldest daughter*.
> - **Frank Jr.**, the younger one.
