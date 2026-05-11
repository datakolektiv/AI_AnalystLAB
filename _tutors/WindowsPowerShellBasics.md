# AI ANALYST LAB

![](../_img/Ghost_TheSyntheticBanner.png)

### A Hands-on Course on AI for Data Analysts
## Windows PowerShell — a gentle crash course

Feedback should be sent to [goran.milovanovic@datakolektiv.com](mailto:goran.milovanovic@datakolektiv.com).

Welcome. If the word "terminal" makes you a little tense, this primer is exactly for you.

The good news: **you will not become a programmer of the terminal during this course.** You will only ever *type the commands that the course gives you*, almost always copy-pasted. That is it. No scripts. No loops. No mysterious incantations. But because typing into a black-and-blue window is unfamiliar at first, we are going to spend a few minutes building up your comfort with it.

By the end of this primer you will know:

- What PowerShell is and why we use it.
- How to open it and what the prompt is telling you.
- How to find your way around your computer with two or three commands.
- How to copy, paste, and recall previous commands without retyping.
- How Windows handles file paths inside the terminal — including the `\` backslash, the `.\` prefix, and what to do when a folder name has spaces in it.
- How to set and read environment variables (we use one of these for your Claude API key).
- How to read the most common error messages.

You can read this whole primer in about 15 minutes. Keep it open in a tab while you work through Session 00 and Session 01 — you will refer back to it a few times.

---

## 1. What is PowerShell, exactly?

**PowerShell is a window where you type commands instead of clicking.** Windows has had this kind of window since the very beginning, under different names — "MS-DOS Prompt", "Command Prompt", and now "PowerShell". PowerShell is the modern one, and it is the one we use throughout this course.

A few things to know up front so the terminology never bites you:

- PowerShell is **built into Windows.** You do not need to install anything. It is already on your machine.
- There are technically two PowerShells — "Windows PowerShell" (the older one, version 5.1, blue background, always present) and "PowerShell" (the newer one, version 7+, black background, you have to install it separately). **For this course, the built-in Windows PowerShell is all we need.** Open whatever you find when you search for "PowerShell" in the Start menu.
- PowerShell is similar in spirit to the **Terminal** on macOS or **bash** on Linux. The commands are different in detail, but the idea — *"type, press Enter, see output"* — is the same.

**Why do we use it at all?** Because some of the things we need to do — creating a Python virtual environment, activating it, installing packages, running git, setting environment variables — are easiest and most reliable in PowerShell. The point-and-click alternatives are either missing or much more confusing. The terminal is shorter, faster, and more consistent across machines.

---

## 2. How to open PowerShell

There are several ways. Use whichever one feels easiest.

**Method A — the Start menu (most beginners use this).**
1. Click the **Start** menu (Windows logo, bottom-left).
2. Start typing **"PowerShell"**.
3. Click **Windows PowerShell** from the search results.

A blue-ish window opens with some text in it. You are in.

**Method B — Win + R shortcut.**
1. Press **Windows key + R** to open the "Run" dialog.
2. Type **`powershell`** and press ENTER.

**Method C — right-click in a folder (handy for jumping straight to a location).**
- In File Explorer, hold **Shift** and right-click in an empty area inside a folder. You will see an option like **"Open in Terminal"** or **"Open PowerShell window here"**. Click it. PowerShell opens *already inside that folder* — saving you a `cd` command.

You can have **multiple PowerShell windows open at the same time** with no problem. We will sometimes ask you to *"close this one and open a new one"* — when we do, we mean exactly that: close the entire window, then open a brand-new one.

> **Administrator vs regular.** Some commands need *administrator privileges* (the equivalent of granting elevated permissions). You open an admin PowerShell by right-clicking **Windows PowerShell** in the Start menu and choosing **"Run as administrator"**. **In this course, we almost never need this.** We tell you explicitly when we do (Session 00 mentions one or two cases). The vast majority of what you do is in a regular, non-admin PowerShell.

---

## 3. What does the prompt mean?

When PowerShell opens, you see something like this, with a blinking cursor at the end:

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

PS C:\Users\jane>
```

That last line is called the **prompt**. Read it like this:

- **`PS`** stands for *"PowerShell"*. It is reminding you which kind of terminal you are inside.
- **`C:\Users\jane`** is your **current working directory** — the folder PowerShell is "standing in" right now. Whatever you do (`cd`, `ls`, run a script) happens relative to this folder unless you say otherwise.
- **`>`** is the cursor marker. After this you type your command.

When this primer (or the course) shows code like:

```powershell
ls
```

it means: type `ls` after the prompt, then press ENTER.

When the course shows code like:

```powershell
cd C:\Users\jane\ai_analyst_lab
```

it means: type the **whole line** after the prompt, then press ENTER. You do **not** type the `PS C:\Users\jane>` part — PowerShell shows that itself.

---

## 4. Your first three commands

Three commands you can try right now to get comfortable.

### `Get-Date` — what time is it?

```powershell
Get-Date
```

Output (yours will differ):

```
Friday, May 15, 2026 3:47:21 PM
```

This does nothing useful for your work, but it shows you that the prompt accepts a command and shows a result. Try it once for the warm-up.

### `whoami` — who am I logged in as?

```powershell
whoami
```

Output:

```
laptop-2025\jane
```

The bit before the `\` is your computer's name; the bit after is your Windows username. This is the username you might need to substitute into file paths.

### `pwd` — where am I right now?

```powershell
pwd
```

Output:

```
Path
----
C:\Users\jane
```

This is the same information that the prompt was already showing you, just spelled out as a one-line table. *"Print Working Directory"* is the old Unix name, and PowerShell keeps it as an alias because it is muscle memory for many people.

---

## 5. The single most important time-saver: **tab completion**

PowerShell can finish your typing for you. Start typing a command or a path, then press the **Tab** key. PowerShell guesses what you meant. If there is more than one possibility, press **Tab** again to cycle through them.

Try it. Start typing:

```
cd C:\Us
```

…then press **Tab**. PowerShell completes it to `C:\Users\`. Press **Tab** again and again to cycle through the folders inside `Users`.

**Use tab completion for every long path.** It saves time and — more importantly — it **prevents typos**. If Tab will not complete your path, that is PowerShell telling you the path does not exist where you said it would.

---

## 6. Moving around: `cd`

`cd` stands for *"change directory"*. It moves PowerShell's current working directory.

```powershell
cd C:\Users\jane\Downloads
```

After running this, your prompt updates to show the new location:

```
PS C:\Users\jane\Downloads>
```

A few small but useful tricks:

- **`cd ..`** — go up one level (to the folder containing the current one).
- **`cd \`** — go to the very top of the current drive (`C:\`).
- **`cd ~`** — go to your home folder (`C:\Users\<your-name>`).
- **`cd -`** — toggle back to the previous location.

If you try to `cd` somewhere that does not exist, PowerShell tells you:

```
cd : Cannot find path 'C:\Users\jane\Downloads2' because it does not exist.
```

Read the error literally: it says "the folder I tried to go to does not exist". Almost always this is a typo. Use **tab completion** to avoid it.

---

## 7. Listing what is in a folder: `ls`

`ls` lists the files and folders in your current location:

```powershell
ls
```

Output:

```
    Directory: C:\Users\jane\Downloads

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         5/10/2026   1:18 AM                ai_analyst_lab
-a----         5/12/2026   9:30 AM         275000 python-3.14.4-amd64.exe
```

Reading the table:

- The **`Mode`** column has a `d` for *directories* (folders) and `a` for *archive* (regular files).
- The **`Length`** column is the file size in bytes (empty for folders).
- The **`Name`** column is what you would `cd` into or open.

> **Note.** `ls` in PowerShell is an alias for the actual command name, **`Get-ChildItem`**. Both work identically — `ls` is shorter and is what we use throughout the course. You can ignore the long name.

---

## 8. Windows paths — three things that catch beginners

### a. Backslashes, not slashes

On Windows, the folder separator is the **backslash** (`\`), not the forward slash (`/`) used by macOS and Linux. So:

```
C:\Users\jane\ai_analyst_lab\Session01
```

Not:

```
C:/Users/jane/ai_analyst_lab/Session01     ← not the Windows convention
```

Forward slashes happen to work in most PowerShell commands too, but stick to backslashes — every guide and every error message you read will use them.

### b. Quoting paths that contain spaces

If a folder name contains a space, PowerShell needs you to wrap the whole path in **single quotes**:

```powershell
cd 'C:\Users\John Smith\ai_analyst_lab'
```

Without the quotes, PowerShell would see `John` and `Smith` as two separate arguments and complain. The single quotes glue them together as one path. Use them whenever a path has a space in it.

### c. The `.\` prefix when running something in the current folder

To run a script or executable that lives in your **current** folder, you must put `.\` (dot-backslash) in front of its name:

```powershell
.\ailab\Scripts\activate
```

The `.\` means *"in the current folder"*. Without it, PowerShell will refuse to run the script — for security reasons it does not want to execute random files just because they happen to be next to where you are.

You will see this prefix most often when activating the course's Python virtual environment.

---

## 9. Copy and paste

This is a little different from the rest of Windows.

- **Paste into PowerShell:** **right-click** anywhere in the window. Whatever is on your clipboard is pasted at the cursor. (You can also press **Ctrl + V** in modern Windows 10 / 11 PowerShells.)
- **Copy from PowerShell:** select text with the mouse (click-drag), then press **ENTER** or **Ctrl + C** to copy.

> **When pasting a long password or API key.** PowerShell will not echo the characters (you will see nothing happen), but the paste *did* work. Just press ENTER. This is a security feature.

---

## 10. Pressing **Up Arrow** to recall previous commands

PowerShell remembers every command you ran in the current window. Press the **Up Arrow** key (and **Down Arrow**) to step through your history. This is enormously useful when:

- You typed a long command and need to fix one typo. Up arrow → edit → ENTER.
- You want to re-run the same command after small changes.
- You forgot what you ran ten minutes ago.

---

## 11. Environment variables

An **environment variable** is a setting that Windows remembers and shares with programs you run from PowerShell. We use one of these — `ANTHROPIC_API_KEY` — to give your Python notebooks access to Claude.

### Reading an environment variable

```powershell
echo $env:ANTHROPIC_API_KEY
```

Output (if it is set):

```
sk-ant-api03-xxxxxxxxxxxxx...
```

The `$env:` prefix is how PowerShell looks up environment variables. **No space** between `$env:` and the variable name.

### Setting an environment variable temporarily (just for this PowerShell window)

```powershell
$env:ANTHROPIC_API_KEY = "sk-ant-..."
```

This works *only* in the current window and only until you close it. We almost never use this form in this course.

### Setting an environment variable permanently (for all future windows)

```powershell
setx ANTHROPIC_API_KEY "sk-ant-..."
```

The **`setx`** command writes the variable into your user profile, so it survives reboots and is visible to every PowerShell window you open from now on. **Two important quirks:**

1. **`setx` does NOT update the current window.** Only *future* windows see the new value. So after running `setx`, close that PowerShell window and open a new one.
2. **VS Code reads environment variables at launch.** If you want VS Code's Python kernel to see a new env var you just set, **close VS Code completely and reopen it**.

You will run `setx` exactly once per machine in this course, for `ANTHROPIC_API_KEY`. The notebook README walks you through it.

---

## 12. Running scripts and the execution policy

By default, Windows PowerShell is conservative about running scripts (`.ps1` files). You will hit this once in Session 00 when you try to activate the Python virtual environment for the first time. The fix is one line:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

Type **`Y`** when it asks you to confirm. This relaxes the policy for *your user account only*, not the whole machine. After this you will never have to think about execution policies again.

You can check the current setting at any time with:

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

You want it to say `RemoteSigned` (or anything more permissive). If it says `Restricted` or `Undefined`, run the `Set-ExecutionPolicy` line.

---

## 13. The course's PowerShell cheat-sheet

Every PowerShell command you will need across the entire eight sessions, in one place. Print it if you want.

### Navigation and inspection

| Command | What it does |
|---|---|
| `pwd` | Show the current folder. |
| `ls` | List files and folders here. |
| `cd <path>` | Move into the folder at `<path>`. |
| `cd ..` | Move up one folder. |
| `cd ~` | Jump to your home folder. |
| `Get-Date` | Show today's date and time. |

### Python and the virtual environment

| Command | What it does |
|---|---|
| `python --version` | Confirm Python is installed and which version. |
| `python -m venv ailab` | Create the `ailab` virtual environment in the current folder. |
| `.\ailab\Scripts\activate` | Activate the `ailab` venv (prompt gets `(ailab)` prefix). |
| `deactivate` | Leave the active venv. |
| `python -m pip install --upgrade pip` | Update pip itself. |
| `python -m pip install numpy pandas …` | Install one or more packages. |
| `python -m pip list` | List installed packages in the active venv. |

### Git

| Command | What it does |
|---|---|
| `git --version` | Confirm Git is installed. |
| `git clone <url>` | Download a repository to your current folder. |
| `git status` | See which files have changed. |
| `git pull` | Download new changes from the remote (GitHub) into your local copy. |
| `git add <file>` | Mark a file as ready to commit. |
| `git commit -m "message"` | Save your staged changes locally. |
| `git push` | Send your local commits to GitHub. |

### Environment variables (for Claude API key)

| Command | What it does |
|---|---|
| `echo $env:ANTHROPIC_API_KEY` | Show the current value of the variable. |
| `setx ANTHROPIC_API_KEY "sk-ant-…"` | Save it permanently for your user. (Close + reopen PowerShell and VS Code afterwards.) |

### PowerShell policy

| Command | What it does |
|---|---|
| `Get-ExecutionPolicy -Scope CurrentUser` | Show the script policy. |
| `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` | Allow venv activation scripts to run. |

That is everything. There is no command in this course that is not on this list.

---

## 14. The most common error messages (and what to do)

You **will** see error messages. They are not your fault. Here is how to read the most common ones.

### **"`X` is not recognized as the name of a cmdlet, function, script file, or operable program."**

Translation: *"You typed `X`, but I have never heard of `X`."*

Most common causes:
- You just installed something (Python, Git, …) but your PowerShell window predates the install. **Close the window, open a new one**, and the new install becomes visible.
- A typo. Check the spelling.
- You forgot the `.\` prefix for a script in the current folder.

### **"Cannot find path 'X' because it does not exist."**

Translation: *"You told me to look at a folder or file at `X`, but there is nothing there."*

Most common causes:
- A typo in the path. Use **tab completion** to verify the path piece by piece.
- The wrong working directory (you are in `Downloads` but the path you typed is relative to `Documents`).
- Backslash vs forward slash mix-ups.

### **"Access is denied."**

Translation: *"You are trying to do something this PowerShell window is not allowed to do."*

Most common cause: the operation needs administrator privileges. Open a *new* PowerShell as administrator (right-click → Run as administrator) and retry.

### **"…the execution of scripts is disabled on this system."**

Translation: *"PowerShell will not run `.ps1` script files until you allow it."*

Fix: run the `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` line from §12.

### **A command that worked yesterday no longer works.**

Translation: usually *"a setting changed (often an environment variable) and PowerShell needs a fresh window to see it."*

Fix: close the PowerShell window, open a new one, try again.

---

## 15. What is next

You now know everything about PowerShell you need for AI Analyst LAB. **You do not need to memorize any of this.** Keep this primer as a reference, and use the cheat-sheet in §13 when you forget a specific command.

If you get stuck at any point, you have two safety nets:

- The **`windows_powershell_tutor`** Claude Project, set up the same way as the Session Tutors (see `TutorProjectCreation.md`). Paste any PowerShell question, error message, or *"what does this line do?"* into it, and you will get a patient beginner-level explanation.
- Your **instructor.** When in doubt, ask. PowerShell is the kind of skill where ten minutes of help is worth two hours of frustration.

Welcome to the terminal.

---

![](../_img/DK_Logo_White_150.png)

DataKolektiv, 2026.

[hello@datakolektiv.com](mailto:hello@datakolektiv.com)

<font size=1>License: [GPLv3](../LICENSE). This document is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This document is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.</font>
