# AI ANALYST LAB

![](../_img/Ghost_TheSyntheticBanner.png)

### A Hands-on Course on AI for Data Analysts
## Setting up your Claude Project tutors

Feedback should be sent to [goran.milovanovic@datakolektiv.com](mailto:goran.milovanovic@datakolektiv.com).

Throughout this course you will have **three kinds of tutors** working alongside you — each one a separately configured Claude assistant ready to answer a different kind of question. This guide walks you through setting them up.

If you have never created a Claude Project before, follow every step in order. If you get stuck, ask your instructor — do not improvise.

---

## The three kinds of tutors

| Tutor | When to set it up | What it helps with |
|---|---|---|
| **`python_stack_tutor`** | **Once**, before Session 01 starts. | Any Python question across the whole course: pandas, NumPy, matplotlib, seaborn. *"What does `df.groupby()` actually return?"* *"How do I draw a boxplot?"* |
| **`windows_powershell_tutor`** | **Once**, before Session 01 starts. | Any Windows PowerShell / terminal question. *"What does the `.\` mean?"* *"How do I check whether my API key is set?"* *"What does this error message mean?"* |
| **`sessionXX_tutor`** (one per session) | At the start of **each** session — Session 01, then Session 02, and so on. **Eight in total** over the course. | The statistics covered in *that specific session*. *"Could you explain mean vs median with a small example?"* *"What does standard error really mean?"* |

The first two are set up **once and reused** across all eight sessions. The third kind is **per session** — you create a new one at the start of each new session, scoped to the statistics topics of that session.

By the end of the course you will have **ten Claude Projects** in your Claude account: two cross-session tutors and eight per-session tutors.

Each tutor's instructions live in the `_tutors/` folder of this repository as an `.xml` file:

```
_tutors/
├── python_stack_tutor.xml          ← set up once
├── windows_powershell_tutor.xml    ← set up once
├── session01_tutor.xml             ← set up at the start of Session 01
├── session02_tutor.xml             ← set up at the start of Session 02 (when published)
├── ...                              (one XML per session)
├── WindowsPowerShellBasics.md      ← gentle PowerShell primer (read first)
└── TutorProjectCreation.md         ← this file
```

---

## What is a "Claude Project"?

A **Claude Project** is a saved workspace inside Claude (the chat app at [https://claude.ai](https://claude.ai)) that has its own custom instructions and its own conversation history. By saving the instructions once, you do not have to paste them at the start of every chat. The tutor "remembers" how to teach you each time you start a new chat inside that Project.

For us, those custom instructions live in the `.xml` files listed above. You will copy the contents of an XML file into a Claude Project's instructions box **once per tutor**, and the tutor is then ready for you.

---

## Before you start, make sure you have

- **A Claude account.** Sign up at [https://claude.ai](https://claude.ai) if you do not have one. Use the same email you use for the course.
- **The XML files for the tutors you are setting up.** They live in the `_tutors/` folder of this repository, which you cloned to your computer per the main course README.
- **A subscription that includes Projects.** As of 2026, Claude Projects is part of **Claude Pro** and above. If you do not see "Projects" in your Claude sidebar, ask your instructor about access.

---

## What to set up *before* Session 01 starts (one-time)

Before you begin Session 01, set up **two** Claude Projects — the two cross-session tutors. You will use these from Session 01 right through Session 08.

### A. `python_stack_tutor`

Follow the **generic Claude Project setup steps** in the next section, using:

- **Project name:** `python_stack_tutor`
- **Description (optional):** `Python tutor for pandas, NumPy, matplotlib, and seaborn — used across all eight AI Analyst LAB sessions.`
- **Instructions to paste:** the entire contents of `_tutors/python_stack_tutor.xml`

### B. `windows_powershell_tutor`

Same steps, using:

- **Project name:** `windows_powershell_tutor`
- **Description (optional):** `Windows PowerShell tutor for AI Analyst LAB — terminal, venv, git, env-var, and path questions.`
- **Instructions to paste:** the entire contents of `_tutors/windows_powershell_tutor.xml`

> If you have never used Windows PowerShell before, *also* read the short companion primer `_tutors/WindowsPowerShellBasics.md` — it covers every PowerShell command the course actually uses, with examples and expected output.

---

## The generic step-by-step (works for any tutor XML)

Use the steps below whenever you create a new Claude Project from any tutor XML — the two cross-session tutors above, or the per-session tutors below. The walkthrough is intentionally idiot-proof.

### Step 1 — Sign in to Claude

1. Open [https://claude.ai](https://claude.ai) in your browser.
2. Click **Sign in** and enter your Claude account credentials.
3. After signing in, you should see a chat-style interface with a left-hand sidebar.

### Step 2 — Find the Projects section

1. Look at the **left sidebar** of the Claude interface.
2. Find an item labeled **"Projects"** (it may have a folder-like icon next to it).
3. Click **Projects**. A list of your projects appears (it will be empty if this is your first project).

> If you cannot find **Projects** anywhere in the sidebar, you are most likely on a plan that does not include it. Stop here and contact your instructor.

### Step 3 — Create a new Project

1. Click the button labeled **"Create project"** (or **"+ New project"**, depending on the exact wording Claude uses in your version).
2. A small dialog appears asking for a project name and (optionally) a description.

### Step 4 — Name the Project exactly

In the **Name** field, type the **exact** project name for the tutor you are setting up. The course's naming convention is:

| Tutor | Project name to type |
|---|---|
| Cross-session Python tutor | `python_stack_tutor` |
| Cross-session PowerShell tutor | `windows_powershell_tutor` |
| Session-1 statistics tutor | `session01_tutor` |
| Session-2 statistics tutor | `session02_tutor` |
| … and so on | `sessionXX_tutor` |

(All lowercase, with underscores. Consistent names make tutors easy to find later.)

In the **Description** field, you can type a short reminder of what the tutor is for — see the "Description (optional)" examples in the previous section.

Click **Create** (or **Save**, depending on wording).

### Step 5 — Open the project's instructions

After the project is created, Claude takes you to the project's main page. On that page, find the section labeled **"Set custom instructions"**, **"Project instructions"**, **"System prompt"**, or similar — the exact label varies slightly across Claude versions. It is usually a button or panel near the top of the project page.

Click it. A large empty text box appears. This is where the tutor's instructions go.

### Step 6 — Copy the XML file contents

1. In Visual Studio Code, open the appropriate `.xml` file from the `_tutors/` folder:

   - `_tutors/python_stack_tutor.xml`
   - `_tutors/windows_powershell_tutor.xml`
   - `_tutors/session01_tutor.xml`
   - …and so on for each new session.

2. Press **Ctrl + A** (Windows / Linux) or **Cmd + A** (macOS) to select the entire contents of the file.

3. Press **Ctrl + C** / **Cmd + C** to copy.

> If you would rather not use VS Code, you can also open the file in any text editor (Notepad, TextEdit) or directly on the GitHub page for this repository. The point is to copy the *exact contents* of the `.xml` file. Do not retype it.

### Step 7 — Paste into the Project instructions

1. Go back to your Claude project's instructions text box (from Step 5).
2. Click inside the empty text box.
3. Press **Ctrl + V** / **Cmd + V** to paste.
4. The full XML should now appear in the box.

You do **not** need to "wrap" the XML in any extra text. The XML *is* the instructions — Claude reads it directly.

### Step 8 — Save

Click the **Save**, **Update instructions**, or **Done** button (the exact wording varies). The dialog closes and you return to the project page. Your tutor is configured.

### Step 9 — Start your first chat with the tutor

1. On the project page, find the chat input box (usually at the bottom of the page).
2. Type a first question to test it. Some good first questions depending on the tutor:

   **`python_stack_tutor`:**
   - *"Could you explain what a pandas DataFrame is, with a tiny example?"*
   - *"What does `df.groupby('hr')['cnt'].mean()` actually do, step by step?"*

   **`windows_powershell_tutor`:**
   - *"What does the `.\` prefix mean before a script name in PowerShell?"*
   - *"My PowerShell says `'python' is not recognized`. What is going on?"*

   **`sessionXX_tutor`:**
   - *"What is the difference between mean and median in plain English?"*
   - *"Could you walk me through what a histogram is showing?"*

3. Send the message. The tutor responds, scoped to its specialty, in beginner-friendly language.

Every time you start a new chat inside this project, the tutor will already be "in character". You do not need to re-paste the XML.

---

## At the start of each new session

Each session of the course comes with its own statistics tutor scoped to that session's topics. **Set it up at the beginning of the session, before you start working through the session's notebook.**

1. Pull the latest changes from the course repository:

   ```powershell
   cd C:\Users\<your-name>\AI_AnalystLAB
   git pull
   ```

   Confirm a new `sessionXX_tutor.xml` file has appeared inside `_tutors/`.

2. Follow Steps 1 through 9 above, using:
   - **Project name:** `sessionXX_tutor` (e.g., `session02_tutor`, `session03_tutor`, …)
   - **Instructions to paste:** the contents of `_tutors/sessionXX_tutor.xml`

The cross-session tutors (`python_stack_tutor`, `windows_powershell_tutor`) keep working as-is — you set them up once and use them throughout the entire course.

---

## How to use the tutors effectively

- **Compute first in Python, then ask the tutor to interpret.** The `python_stack_tutor` and the per-session statistics tutors are configured to *not* invent numbers. If you ask *"what does my histogram look like?"*, paste the actual `describe()` output or a description of the chart shape. The tutor will help you read it, not pretend to see it.
- **Ask each tutor only what it specializes in.** If you ask the `windows_powershell_tutor` about regression coefficients, or the `python_stack_tutor` about hypothesis tests, or `session01_tutor` about decision trees — each one is configured to politely redirect you to the right tutor. That redirect is a feature, not a bug.
- **Ask "stupid" questions on purpose.** The tutors' whole job is to assume you know nothing and to slow down. If a single sentence in your course notebook confuses you, paste that sentence and ask *"what does this mean?"* — that is exactly what the tutors are for.
- **Start a fresh chat when you change topic.** A clean chat is easier to come back to later. Within one project you can have many chats — name each by its topic ("CLT intuition", "Reading boxplots", "PowerShell venv activation", etc.).
- **Don't push a tutor outside its session scope.** The per-session statistics tutors are intentionally focused on the *current* session. If you ask `session01_tutor` about A/B testing, it will gently tell you that topic comes later. That is by design.

---

## Troubleshooting

- **"I don't see 'Projects' in my Claude sidebar."** Your plan probably does not include Projects yet. Contact your instructor.
- **"The tutor's first response feels generic, not like a tutor."** Something went wrong in Steps 5–8. Open the project's instructions, confirm the full XML is in there (it should start with `<project>` and end with `</project>`), and try a new chat.
- **"The tutor keeps trying to teach me Python / statistics / PowerShell — but I asked the wrong tutor."** Each tutor is configured to redirect off-topic questions to the right tutor. If `python_stack_tutor` answers a stats question with *"that belongs to your session tutor — try `session01_tutor`"*, take its advice. The redirects are deliberate.
- **"I want to start over."** Open the project, replace the instructions text with a fresh paste of the XML, and save again. Old chats remain unaffected.
- **"Can I share my tutors with my classmate?"** Each participant should create their own tutors. That way each person has their own private chat history with their tutor, scoped to their own learning pace.
- **"How do I clean up old per-session tutors after the course?"** You can leave them — they cost nothing and the conversation history is useful as a study record. Or you can delete the projects from the Projects sidebar one by one.

---

That is everything. Setting up `python_stack_tutor` and `windows_powershell_tutor` takes about ten minutes the first time. Setting up each new `sessionXX_tutor` afterwards takes about two minutes.

---

![](../_img/DK_Logo_White_150.png)

DataKolektiv, 2026.

[hello@datakolektiv.com](mailto:hello@datakolektiv.com)

<font size=1>License: [GPLv3](../LICENSE). This document is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This document is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.</font>
