---
title: Troubleshooting
nav_order: 14
---

# Troubleshooting
{: .no_toc }

1. TOC
{:toc}

---

## Notes or the HTML export preview are blank

O2 needs **Microsoft Edge WebView2 Runtime** to display notes and the HTML export preview. Install it from the [WebView2 page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/), choosing the *Evergreen* version, then restart O2.

## "Wrong password."

The password you typed doesn't open the file. Passwords are case-sensitive, so check **Caps Lock**. O2 has no way to recover a forgotten password.

## Save opens the Save as dialog

This happens when the file has never been saved, or when it's encrypted with a cipher or hash algorithm that is now deprecated. In the second case, choose a supported algorithm, such as *Rijndael (AES)* with *SHA-256*, in the **Encryption** dialog. You can overwrite the same file. See [Files that use a deprecated algorithm]({% link docs/files.md %}#files-that-use-a-deprecated-algorithm).

## OK is disabled in the Encryption dialog

Check that:

- the password is at least 5 characters long;
- **Password** and **Password confirmation** are identical;
- neither the cipher nor the hash algorithm is marked *[deprecated]*.

## "File version not supported" or "Cipher not supported"

The file was created by a newer version of O2. [Update O2]({% link docs/preferences.md %}#updates) and try again.

## "File type not supported."

The file isn't an O2 file, or it's damaged. To bring data in from XML, use [Import]({% link docs/import-export.md %}#import) instead of Open.

## "An object named … already exists."

Object names must be unique in a file. Choose a different name, or rename the existing object first.

## A date field has no countdown, no event and no highlight

- Check that a rule of type *Expiration date* or *Recurrence* matches the field: its name mask and value mask must both match.
- Check that the rule is enabled on the **Rules** tab.
- Check the rule's **Date format** page: the order (day, month, year) and separator must match how the date is typed in the field. A value such as `28.02.1987` won't be read with separator `/`.
- If another rule higher in the list also matches the field and changes its display, move the date rule up.

## A link doesn't open on Ctrl+click

- The field must match an enabled *Internet link* or *E-mail address* rule.
- If the rule has a link **Mask**, check that it produces a valid address, for example `https://…` or `tel:…`.
- For e-mail, a default e-mail program must be set up in Windows.

## Objects are missing from the list

A search filter may be active. Open the **Find** menu and choose **Clear search**.

## A recent file can't be opened

If the file was moved or deleted, O2 offers to remove it from the recent files list. Use **Open** to browse to its new location.

## Still stuck?

Ask in [Support requests](https://github.com/maurizuki/O2/discussions/categories/q-a), or report a problem in [Bug reports](https://github.com/maurizuki/O2/labels/bug). Include your O2 version, shown in **Help > About O2**, but never share your O2 files or passwords.
