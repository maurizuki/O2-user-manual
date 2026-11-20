---
title: Getting started
nav_order: 2
---

# Getting started
{: .no_toc }

1. TOC
{:toc}

---

## System requirements

- Windows.
- **Microsoft Edge WebView2 Runtime.** O2 uses it to display notes and the HTML export preview. Most up-to-date Windows installations already have it. If not, download it from the [WebView2 page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/); the *Evergreen* version is recommended.

## Install O2

### With the installer

1. Download the latest setup program from the [O2 releases page](https://github.com/maurizuki/O2/releases/latest).
2. Run it and choose an installation type:

   | Type | Installs |
   |:-----|:---------|
   | **Full** | The program, the example files and the HTML export style sheets. |
   | **Compact** | The program only. |
   | **Custom** | The program, plus the components you pick. |

3. Optionally, create a desktop icon.

The installer registers the `.o2` file extension, so you can open O2 files by double-clicking them in File Explorer.

### With Windows Package Manager

Open a terminal and run:

```powershell
winget install --id=maurizuki.O2 -e
```

### On a USB stick

Once O2 is installed, you can copy a portable version of it to a removable drive. See [Install on removable media]({% link docs/preferences.md %}#install-on-removable-media).

## Explore the examples

A full installation adds an **Examples** folder inside the O2 installation folder (by default `C:\Program Files\O2\Examples`). It contains two files that show how O2 is meant to be used:

| File | Shows how to… | Password |
|:-----|:--------------|:---------|
| **AddressBook.o2** | Organize contacts with *E-mail address*, *Highlight*, *Internet link* and *Recurrence* rules, and connect people with relations (husbands and wives, brothers and sisters, companies and employees). | none |
| **PasswordWallet.o2** | Store account credentials safely with a *Password* rule. | `password` |

To open one, click **Open** on the toolbar (or press **Ctrl+O**), browse to the Examples folder and pick the file.

{: .tip }
Open *AddressBook.o2*, then click a contact. Notice how phone numbers and addresses become links, and how birthdays show the person's age. All of this comes from the rules on the **Rules** tab.

## Create your first file

This walkthrough builds a small password wallet.

### 1. Start a new file

Click **New** on the toolbar (or press **Ctrl+N**). If the current file has unsaved changes, O2 asks whether to save them first.

### 2. Add an object

1. Click the arrow next to **New** and choose **New object** (or press **Ctrl+Shift+N**).
2. On the **General** page, type a **Name**, for example `Email account`.
3. Under **Tags**, type `Accounts` in the *New tag* box and click **Add**.
4. Open the **Fields** page and add these fields. For each one, type the name and value in the two boxes under the list and click **Add**:

   | Field | Value |
   |:------|:------|
   | `User name` | `jane.doe` |
   | `Password` | `S3cret-Phrase!` |
   | `Web site` | `https://mail.example.com` |

5. Click **OK**.

### 3. Add rules

Rules tell O2 how to treat certain fields. Here you add one that hides passwords and one that makes web addresses clickable.

1. Click the arrow next to **New** and choose **New rule**.
2. Set **Name** to `Passwords`, **Type** to *Password*, **Field name mask** to `password`, and **Field value mask** to `*`.
3. On the **Password** page, check **Display password strength**, then click **OK**.
4. Create a second rule: **Name** `Web sites`, **Type** *Internet link*, **Field name mask** `*`, **Field value mask** `https://*`. Click **OK**.

Select your object again. The password now shows as dots, colored by strength, and **Ctrl+click** on the web site opens it in your browser.

### 4. Save and encrypt

1. Click **Save** (or press **Ctrl+S**), choose a folder and a file name, and click **Save**.
2. In the **Encryption** dialog, set **Encryption** to *Rijndael (AES)*. For a new file it starts at *(none)*, which would save the file unencrypted.
3. Keep **Hash algorithm** at *SHA-256*.
4. Type a **Password** of at least 5 characters and repeat it in **Password confirmation**. The *Password strength* box tells you how strong it is.
5. Click **OK**.

{: .warning }
O2 cannot recover a forgotten password. If you lose it, the data in the file is lost too. Store the password somewhere safe.

## Next steps

- Learn the vocabulary in [Core concepts]({% link docs/concepts.md %}).
- Take a [tour of the main window]({% link docs/main-window.md %}).
- See everything rules can do in [Rule types]({% link docs/rules/rule-types.md %}).
