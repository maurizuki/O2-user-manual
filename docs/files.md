---
title: Files and encryption
nav_order: 5
---

# Files and encryption
{: .no_toc }

1. TOC
{:toc}

---

## Create a file

Click **New** on the toolbar, or press **Ctrl+N**. O2 clears the window and starts an empty, untitled file. If the open file has unsaved changes, O2 first asks **Save changes?**: choose **Yes** to save, **No** to discard them, or **Cancel** to stay on the current file.

To work on two files at once, open the **New** menu and choose **New window**. This starts another copy of O2.

## Open a file

Use any of these:

- Click **Open** on the toolbar, or press **Ctrl+O**, and pick the file.
- Open the **Open** menu and pick one of the recently used files listed there.
- Double-click an `.o2` file in File Explorer.
- Drag an `.o2` file onto the O2 window.

If the file is encrypted, O2 asks for its **Password**. A wrong password shows the message *Wrong password.*

### Recent files

The **Open** menu lists up to nine recently used files. If a listed file no longer exists, O2 offers to remove it from the list. **Clear recent file list** empties the list.

### Reopen and open folder

- **Reopen** (**Ctrl+Shift+O**) reloads the current file from disk. If you have unsaved changes, O2 asks whether to save them first; choosing **No** discards them.
- **Open folder** opens the folder that contains the current file in File Explorer.

## Save a file

| Command | Shortcut | What it does |
|:--------|:---------|:-------------|
| **Save** | **Ctrl+S** | Saves the file under its current name. For a file that has never been saved, it works like *Save as*. |
| **Save as** | **Ctrl+Shift+S** | Saves the file under a new name and makes the new file the current one. |
| **Save as copy** | — | Saves a copy under a new name. The current file stays open, and its unsaved changes stay unsaved. |

*Save as* and *Save as copy* ask for confirmation before overwriting an existing file, then open the **Encryption** dialog.

## Encryption

The **Encryption** dialog appears every time you save under a new name. It sets how the file is protected.

| Setting | Description |
|:--------|:------------|
| **Encryption** | The cipher. Choose *(none)* to save without encryption. |
| **Hash algorithm** | The hash algorithm used together with the cipher. |
| **Password** | The password needed to open the file. Minimum 5 characters. |
| **Password confirmation** | The same password again. |
| **Password strength** | An estimate of how hard the password is to guess, with suggestions to improve it. |

**OK** stays disabled until the settings are valid: the two passwords match, the password has at least 5 characters, and neither algorithm is deprecated.

{: .important }
For a new file the **Encryption** box starts at *(none)*. Pick a cipher, such as *Rijndael (AES)*, or the file will be saved in a readable, unprotected form.

### Recommended algorithms

*Rijndael (AES)* with *SHA-256* is a sound choice. The available options are:

| | Supported | Deprecated (open only) |
|:--|:--|:--|
| **Ciphers** | Cast-256, Ice 2, IDEA, MARS, RC5, RC6, Rijndael (AES), Serpent, Twofish | Blowfish, Cast-128, DES, 3DES, Ice, Thin Ice, Misty1, RC2, RC4, TEA |
| **Hash algorithms** | SHA-256, SHA-384, SHA-512 | Haval, MD4, MD5, RipeMD-128, RipeMD-160, SHA-1, Tiger |

Deprecated algorithms are marked *[deprecated]* in the lists. O2 can still open files that use them but won't save with them.

### Files that use a deprecated algorithm

When you click **Save** on a file encrypted with a deprecated cipher or hash, O2 runs *Save as* instead, so you can choose a supported algorithm. You can save to the same file name to replace it.

### Change the password

1. Choose **Save as**.
2. Select the current file and confirm the overwrite.
3. Enter the new password in the **Encryption** dialog.

{: .warning }
O2 cannot recover a forgotten password. Keep a copy of it somewhere safe.

## File properties

Choose **Tools > File properties** to view or edit:

| Property | Editable | Description |
|:---------|:---------|:------------|
| **Title** | Yes | A title for the file. Used as the title of exports and printouts. |
| **Description** | Yes | A short description. |
| **Author** | Yes | The author's name. |
| **Encryption** | No | The cipher in use. |
| **Hash algorithm** | No | The hash algorithm in use. |

## Unsaved changes

O2 tracks changes and asks **Save changes?** before closing the window, starting a new file, opening another file or reopening.
