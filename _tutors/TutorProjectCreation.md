# How to set up your Session Tutor as a Claude Project

Every session of **AI Analyst LAB** comes with a **Session Tutor** — a dedicated Claude assistant configured to teach you exactly the statistics and machine-learning concepts that the session covers. You set up the tutor **once per session**, then keep all your conversations with it inside that one Project. Over the course of the eight weeks you will end up with eight tutors: `session01_tutor`, `session02_tutor`, …, `session08_tutor`.

This guide walks you through creating a Claude Project for **Session 01**. The same steps apply, with different filenames, for every later session — just swap `session01_tutor.xml` for `session02_tutor.xml`, and so on.

If you have never used Claude before, or never created a "Project" in Claude, follow every step in order. If you get stuck, ask your instructor — do not improvise.

---

## What is a "Claude Project"?

A **Claude Project** is a saved workspace inside Claude (the chat app at [https://claude.ai](https://claude.ai)) that has its own custom instructions and its own conversation history. By saving instructions once, you don't have to paste them at the start of every chat. The tutor "remembers" how to teach you each time you start a new chat inside the Project.

For us, the custom instructions live in an `.xml` file in the [`_tutors/`](.) folder of this repository (where you are reading right now). You will copy the contents of that file into your Project once, and you are done.

---

## Before you start, make sure you have

- **A Claude account.** Sign up at [https://claude.ai](https://claude.ai) if you do not have one. Use the same email you use for the course.
- **The XML file for the session you are starting.** For Session 01 that is `session01_tutor.xml`, in the same folder as this README. (You already have it on your computer because you cloned the course repository — see the main course README if you haven't.)
- **A subscription that includes Projects.** As of 2026, Claude Projects is part of **Claude Pro** and above. If you do not see "Projects" in your Claude sidebar, ask your instructor about access.

---

## Step 1 — Sign in to Claude

1. Open [https://claude.ai](https://claude.ai) in your browser.
2. Click **Sign in** and enter your Claude account credentials.
3. After signing in, you should see a chat-style interface with a left-hand sidebar.

## Step 2 — Find the Projects section

1. Look at the **left sidebar** of the Claude interface.
2. Find an item labeled **"Projects"** (it may have a folder-like icon next to it).
3. Click **Projects**. A list of your projects appears (it will be empty if this is your first project).

> If you cannot find **Projects** anywhere in the sidebar, you are most likely on a plan that does not include it. Stop here and contact your instructor.

## Step 3 — Create a new Project

1. Click the button labeled **"Create project"** (or **"+ New project"**, depending on the exact wording Claude uses in your version).
2. A small dialog appears asking for a project name and (optionally) a description.

## Step 4 — Name the Project exactly

In the **Name** field, type exactly:

```
session01_tutor
```

(All lowercase, with an underscore between `session01` and `tutor`. Match this format for every later session: `session02_tutor`, `session03_tutor`, and so on. Consistent names make it easy to find the right tutor later.)

In the **Description** field, you can type anything you like — for example:

```
Statistics tutor for AI Analyst LAB Session 01 (bike-sharing demand & operations).
```

Click **Create** (or **Save**, depending on the wording).

## Step 5 — Open the project's instructions

After the project is created, Claude takes you to the project's main page. On that page, find the section labeled **"Set custom instructions"**, **"Project instructions"**, **"System prompt"**, or similar — the exact label varies slightly across Claude versions. It is usually a button or panel near the top of the project page.

Click it. A large empty text box appears. This is where the tutor's instructions go.

## Step 6 — Copy the XML file contents

1. In Visual Studio Code (which you already installed in Session 00), open the file:

   ```
   _tutors/session01_tutor.xml
   ```

2. Press **Ctrl + A** (Windows / Linux) or **Cmd + A** (macOS) to select the entire contents of the file.

3. Press **Ctrl + C** / **Cmd + C** to copy.

> If you would rather not use VS Code, you can also open the file in any text editor (Notepad, TextEdit) or directly on the GitHub page for this repository. The point is to copy the *exact contents* of the `.xml` file. Do not retype it.

## Step 7 — Paste into the Project instructions

1. Go back to your Claude project's instructions text box (from Step 5).
2. Click inside the empty text box.
3. Press **Ctrl + V** / **Cmd + V** to paste.
4. The full XML should now appear in the box.

You do **not** need to "wrap" the XML in any extra text. The XML *is* the instructions — Claude reads it directly.

## Step 8 — Save

Click the **Save**, **Update instructions**, or **Done** button (the exact wording varies). The dialog closes and you return to the project page.

You have now configured your Session 01 tutor.

## Step 9 — Start your first chat with the tutor

1. On the project page, find the chat input box (usually at the bottom of the page).
2. Type your first question. Some good first questions:
   - *"Can you explain in plain English the difference between a mean and a median?"*
   - *"What does the standard deviation in my describe() output actually mean for my business?"*
   - *"I don't really understand why my sample average wouldn't equal the population average. Can you walk me through it?"*
   - *"Can you give me a tiny example of the Central Limit Theorem so I get the intuition?"*

3. Send the message. The tutor responds, scoped to Session 01 topics, in beginner-friendly language.

Every time you start a new chat inside this project, the tutor will already be "in character" as your Session 01 statistics tutor. You do not need to re-paste the XML.

---

## How to use the tutor effectively

- **Compute first in Python, then ask the tutor to interpret.** The tutor is configured to *not* invent numbers. If you ask "what does my histogram look like?", paste the actual `describe()` output or a description of the chart shape. The tutor will help you read it, not pretend to see it.
- **Ask "stupid" questions on purpose.** The tutor's whole job is to assume you know nothing and to slow down. If a single sentence in your course notebook confuses you, paste that sentence and ask "what does this mean?" — that is exactly what the tutor is for.
- **Start a fresh chat when you change topic.** A clean chat is easier to come back to later. Within one project you can have many chats — name each by the topic ("CLT intuition", "Reading boxplots", etc.).
- **Don't push the tutor outside the session scope.** It is intentionally focused on Session 01. If you ask it about A/B testing or regression, it will gently tell you those topics come later. That is not a bug.

---

## When the next session starts

The instructor will add a new XML file to the `_tutors/` folder — for example, `session02_tutor.xml`.

1. Pull the latest changes from the course repository:
   ```
   cd ~/ai_analyst_lab/AI_AnalystLAB
   git pull
   ```
2. Repeat Steps 3 through 8 above, this time using the new XML file and naming the new project `session02_tutor`.

By the end of the course you will have eight projects, each one a different "expert tutor".

---

## Troubleshooting

- **"I don't see 'Projects' in my Claude sidebar."** Your plan probably does not include Projects yet. Contact your instructor.
- **"The tutor's first response feels generic, not like a tutor."** Something went wrong in Steps 5–8. Open the project's instructions, confirm the full XML is in there (it should start with `<project>` and end with `</project>`), and try a new chat.
- **"The tutor keeps trying to teach me Python."** Re-check the XML — the instructions explicitly tell the tutor to stay focused on statistics and refer Python questions back to the course. If you missed a section when pasting, the behavior changes.
- **"I want to start over."** Open the project, replace the instructions text with a fresh paste of the XML, and save again. Old chats remain unaffected.
- **"Can I share my tutor with my classmate?"** Each participant should create their own project. That way each person has their own private chat history with their tutor.

---

That is everything. Once you have done this once, it takes about two minutes per session for the rest of the course.
