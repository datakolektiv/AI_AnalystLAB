# AI Analyst LAB

![](_img/Ghost_TheSyntheticBanner.png)

Welcome! This repository contains the course material for **AI Analyst LAB**, a hands-on course on using AI as a data analyst, by [DataKolektiv](https://datakolektiv.com).

**Lecturer:** [Goran S. Milovanović, PhD](https://www.linkedin.com/in/gmilovanovic/), Chief Scientist & Owner, DataKolektiv

---

## What this README is for

This README walks you through the **one-time setup** of getting the course code onto your computer. After this, every week your instructor will add new sessions, and you will just run a single command (`git pull`) to update your local copy.

If you have never used GitHub, Git, or a terminal before, **do not worry** — every step is explained, and you cannot break anything by following the instructions. Plan to spend about **5 minutes** on this.

If you get stuck for more than a few minutes on any step, contact your instructor — do not try to improvise.

---

## A two-minute glossary (for absolute beginners)

If any of these words feel unfamiliar, read them once and move on. They will start to make sense as you do each step.

- **GitHub** — a website that stores code and files. Think of it as Google Drive for code, plus a complete history of every change ever made.
- **Repository** (or "repo") — a project folder on GitHub. The page you are reading right now is the README of the AI Analyst LAB repository.
- **Git** — a free program that runs on your computer. Git is what talks to GitHub and downloads or uploads files for you. *GitHub is the website; Git is the program — different things.*
- **Clone** — the act of making a copy of a GitHub repository onto your computer. You do this once, at the start.
- **Pull** — the act of checking GitHub for new changes and downloading them. You will do this every time the instructor announces new course material.
- **Terminal / PowerShell** — a window where you type commands instead of clicking. On Windows it is called **PowerShell**. On macOS and Linux it is called **Terminal**. Do not be intimidated — every command in this guide can be copied and pasted.

---

## What you will do (overview)

You will go through three numbered steps to get the course code onto your computer:

1. Install **Git** on your computer (skip if you already have it).
2. **Clone** the AI Analyst LAB repository onto your computer.
3. Learn how to **pull updates** later in the course.

Because this repository is **public**, you do not need a GitHub account, an invitation, or a password to clone it.

After those steps, a separate **Set up your Claude API access** section walks you through getting an API key so the Python code in your course notebooks can talk to Claude.

---

## Step 1 — Install Git (skip if you already have it)

### Open your terminal

- **Windows:** type "PowerShell" in the Start menu and click **Windows PowerShell**.
- **macOS:** press **CMD + SPACE**, type "Terminal", and press ENTER.
- **Linux:** press **CTRL + ALT + T** (or open Terminal from your application launcher).

### Check whether Git is installed

In your terminal, type:

```
git --version
```

and press ENTER.

- If you see something like `git version 2.50.x`, you already have Git — **skip to Step 2**.
- If you see `command not found` or `'git' is not recognized`, continue below.

### Install Git

#### Windows
1. Open [https://git-scm.com/downloads/win](https://git-scm.com/downloads/win) in your browser.
2. Click **64-bit Git for Windows Setup** (under "Standalone Installer") to download the installer.
3. Run the downloaded `.exe` file. Click **Next** through every screen with the **default options**, then **Install**, then **Finish**.

#### macOS
The easiest way is via Homebrew. If you do not have Homebrew yet, install it by pasting this command into Terminal and pressing ENTER:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Follow the on-screen instructions (you will be asked for your macOS password). Once Homebrew is installed, run:

```
brew install git
```

#### Linux (Ubuntu / Debian)

```
sudo apt update
sudo apt install -y git
```

### After installing

**Close your terminal and open a new one** — this is important, because the new terminal needs to pick up the updated environment. Then run `git --version` again to verify.

---

## Step 2 — Clone the repository

This is the step where the course code lands on your computer.

1. Open a new terminal.
2. Navigate to the folder where you want the course code to live. We recommend your **home folder**.
   - **Windows:**
     ```
     cd C:\Users\<your-name>
     ```
     Replace `<your-name>` with your Windows username.

     > **How to find your Windows username:** open **File Explorer** → click **This PC** → **Users**. The folder names you see inside `Users` are usernames; one of them is yours (the folder that contains your `Documents`, `Downloads`, etc.).

   - **macOS / Linux:**
     ```
     cd ~
     ```
     The `~` symbol means "my home folder".

3. Run the clone command:

   ```
   git clone https://github.com/datakolektiv/AI_AnalystLAB.git
   ```

4. After a few seconds, you should see output similar to:

   ```
   Cloning into 'AI_AnalystLAB'...
   remote: Enumerating objects: ...
   Receiving objects: 100% ...
   ```

   When your terminal prompt comes back, the clone is complete.

5. Verify a new folder named **`AI_AnalystLAB`** appeared:
   - **Windows:** type `dir` and press ENTER.
   - **macOS / Linux:** type `ls` and press ENTER.

---

## Step 3 — Pulling future updates

Whenever your instructor adds new course material, you do **not** clone the repository again. Instead, you "pull" the new changes into your existing folder.

Open your terminal and run:

```
cd AI_AnalystLAB
git pull
```

If you opened a new terminal session and `cd AI_AnalystLAB` does not work, use the full path:

- **Windows:** `cd C:\Users\<your-name>\AI_AnalystLAB`
- **macOS / Linux:** `cd ~/AI_AnalystLAB`

That is all. No password, no token — `git pull` just downloads the latest changes.

---

## Set up your Claude API access

Throughout this course you will write Python in your notebooks that **calls the Claude API** — meaning your code will send a question to Claude over the internet and get back an answer, with no chat window open. The API is **separate from the Claude chat app** at [https://claude.ai](https://claude.ai), and it needs its own setup. This section walks you through it, step by step.

This section is conceptual and practical only. The Python code that actually makes the API calls is taught hands-on starting in **Session 01** — you do not need to write any code right now.

### Two different "Claudes" you will use

The same Claude models are reachable through **two completely separate products**, and you will use both during this course.

|  | The chat app | The developer platform |
|---|---|---|
| **Address** | [https://claude.ai](https://claude.ai) | [https://platform.claude.com](https://platform.claude.com) |
| **What it is** | A website / app where you type messages and read replies. | A developer service that your Python code can talk to. |
| **Pricing** | Monthly subscription (Pro, Team, …). | Pay-as-you-go for what you use ("tokens"). |
| **You use it for** | The **Session Tutors** (see [`_tutors/TutorProjectCreation.md`](_tutors/TutorProjectCreation.md)). | The **API calls in your course notebooks**. |
| **Account / billing** | Separate. | Separate. |

You may already have a `claude.ai` account from setting up your Session Tutor. **The developer platform is a separate sign-up**, even though both are run by the same company (Anthropic).

### What is "calling the API"? (non-technical)

The **API** ("Application Programming Interface") is a way for your Python code to send messages to Claude directly, without anyone typing in a chat box.

The whole workflow, in plain English:

1. Your Python code prepares a message — for example: *"Here is a small table of bike-rental statistics; please summarize it for an operations manager."*
2. The code sends that message to a Claude server on the internet, along with your **API key** (a long secret string that proves the request belongs to your account).
3. The server runs Claude on your message and sends a text reply back to your code.
4. Your code receives the reply and can do whatever it likes with it — print it, save it to a file, parse it as JSON, paste it into a report.

That is it. The instructor will show you the exact Python code in Session 01. You will not write any of the network plumbing yourself — the `anthropic` Python package (already installed in Session 00) handles that for you in one or two lines of code.

### What is a "token"? How does pricing work?

The developer platform charges per **token**, not per call.

- A token is a small chunk of text — roughly **four characters** of English, or about **three-quarters of a word**.
- You pay for **input tokens** (the text your code sends to Claude) **and** for **output tokens** (the text Claude sends back).
- Different Claude models cost different amounts per token. Newer or larger models cost more per token; smaller, faster models cost less.

In practice, the kind of question-and-answer you will make in this course costs **a small fraction of one US cent per call**. Topping up your account with a modest balance is enough to cover all eight sessions comfortably.

You add money to your account as a balance. Each API call your code makes deducts a tiny amount from that balance. When the balance gets low, you top it up — there is no fixed monthly fee.

### Step 1 — Create your developer account at platform.claude.com

1. Open [https://platform.claude.com](https://platform.claude.com) in your browser.
2. Click **Sign up**. We recommend using the **same email** you used for your `claude.ai` account — it is not strictly required, but it keeps things simple.
3. Set a password and follow any verification prompts (you may receive a verification code by email).
4. After signing in, you land on the developer console — the home screen of `platform.claude.com`.

### Step 2 — Add a payment method and a small balance

1. In the left-hand sidebar, click **Billing** (the label may also read **Plans & Billing**).
2. Click **Add payment method**, enter your credit or debit card, and save.
3. Click **Add credit** (or **Buy credits**, depending on the exact wording).
4. Enter the amount you wish to deposit. **$10–$25 is more than enough to start.** You can always add more later. Confirm.

Your balance is now shown on the Billing page. From now on, each API call your code makes will deduct a small amount from it.

### Step 3 — Create an API key

After signing in and adding a balance, you land on the developer dashboard at [https://platform.claude.com/dashboard](https://platform.claude.com/dashboard). This is where you create your API key.

An **API key** is a long secret string that lets your code authenticate as you. **Treat it like a credit-card number** — anyone who has it can spend your balance.

1. From the dashboard, look at the **left-hand sidebar**. Find and click **API Keys**.
   > The exact label and location vary slightly between Anthropic console versions. If you do not see "API Keys" directly in the sidebar, click **Settings** and look inside; on some accounts it lives under an "Organization" or "Workspace" section.
2. You land on the API Keys management page. Click the button labeled **Create Key** (or **+ Create Key**).
3. A small form opens. Fill it in as follows:
   - **Name:** type something descriptive, e.g., `AI_AnalystLAB-laptop`. The name is purely for your own organization — it does not affect how the key works.
   - **Workspace** (if asked): leave the default.
   - **Permissions / scope** (if asked): leave the default ("full access" / "all permissions" — fine for a beginner course).
4. Click **Create** (or **Generate Key**).
5. A new screen shows your key — a long string starting with `sk-ant-…`. **Copy it right now** using the small "copy" button next to the key.

   > ⚠️ **The developer console will NOT show this full key again.** After you close this screen, only the first few and the last few characters remain visible. If you lose the key, do not panic — come back to this same page, **Revoke** the lost key, and **Create** a new one. But it is much easier to copy and store it now.

6. **Temporarily** paste the key into a private text file on your desktop. You will delete this file after Step 4 below. Do **not** paste it into a chat, an email, or anywhere on the internet.

### Step 4 — Store the API key on your Windows machine

We need your computer to remember your API key so that your course notebooks can use it automatically — without you having to paste it into every notebook (which would be both insecure and tedious).

The cleanest way on Windows is to save the key as a **user environment variable**. This is a setting Windows stores permanently for your user account, and Python — and therefore your notebooks — can read it automatically.

1. Open **PowerShell** (Start menu → type "PowerShell" → click **Windows PowerShell**).

2. Type the following command, but **replace** `sk-ant-your-key-here` with the actual key you copied in Step 3 (keep the double quotes):
   ```powershell
   setx ANTHROPIC_API_KEY "sk-ant-your-key-here"
   ```
   Press ENTER. PowerShell prints:
   ```
   SUCCESS: Specified value was saved.
   ```
   Your key is now permanently stored as a user environment variable on this machine.

3. **Close this PowerShell window completely**, then open a brand-new PowerShell window.
   > The `setx` command does not update the *current* shell — only future ones. This is normal Windows behavior, not a bug.

4. **Verify** the key was saved. In the new PowerShell window, type:
   ```powershell
   echo $env:ANTHROPIC_API_KEY
   ```
   It should print your key. If it does, the storage step is complete.

5. **Restart VS Code completely.** Close every VS Code window, then re-open VS Code.
   > This is important. VS Code (and the Python kernel that runs your notebooks) only sees environment variables that existed at the moment VS Code launched. If you opened a notebook before this step, the kernel will not see your key until VS Code is restarted.

6. **Delete the temporary text file** containing the key that you saved in Step 3 — you no longer need it on disk. If you use a password manager, that is the appropriate long-term home for a backup copy.

Once Steps 1–6 are done, the Python code in any notebook can use Claude **without ever mentioning the key in code**. In Session 01 your instructor will show you the exact one-line Python pattern that picks up `ANTHROPIC_API_KEY` automatically.

> **On macOS or Linux** (for completeness, since the rest of the course is multi-platform): add the line `export ANTHROPIC_API_KEY="sk-ant-..."` to your `~/.zshrc` (macOS) or `~/.bashrc` (Linux), then open a fresh Terminal so it picks up the change. The Python side of the workflow is identical on every platform.

### Step 5 — Keep your API key safe

This is non-negotiable. If a stranger gets your API key, they can spend your balance.

- **NEVER commit your API key to git, paste it into chat, post it on a forum, or email it.** Not even to your instructor — your instructor never needs it.
- **NEVER hard-code the key inside a notebook cell.** Do not type `client = anthropic.Anthropic(api_key="sk-ant-...")`. Always rely on the environment variable you set in Step 4 — that is exactly what your instructor will teach you to do.
- If you ever suspect your key has leaked: open [https://platform.claude.com/dashboard](https://platform.claude.com/dashboard) → **API Keys** → click the affected key → **Revoke** (or **Delete**). Then create a fresh key and re-run the `setx` command from Step 4 with the new value (followed by closing and reopening VS Code).

### Where to learn more

- **Official docs:** [https://docs.claude.com](https://docs.claude.com). The **Quickstart** and **Messages API** pages are the most relevant for this course.
- **Pricing & models:** [https://www.anthropic.com/pricing](https://www.anthropic.com/pricing) — current per-token pricing for every Claude model.
- **Your instructor.** Everything practical — which model to pick for a task, how to structure messages, how to handle errors, how to read your usage dashboard, how to use the Python `anthropic` library — will be taught hands-on starting in **Session 01**. You do not need to study the docs in advance.

After Steps 1–5 you have an account, a funded balance, a saved API key, and your machine configured to find it automatically. You are ready to make your first API call in Session 01.

---

## Common things that go wrong

- **`git: command not found`** or **`'git' is not recognized`** — Git is not installed yet, or your terminal has not picked it up. Close the terminal, open a new one, and try again. If that still does not work, go back to **Step 1**.
- **`fatal: destination path 'AI_AnalystLAB' already exists and is not an empty directory`** — you already cloned the repository. Either skip the clone and run `git pull` instead (Step 3), or delete the existing `AI_AnalystLAB` folder and re-run the clone.
- **`Could not resolve host: github.com`** — your computer cannot reach GitHub. Check your internet connection and try again.

---

## What's next?

Once you have the `AI_AnalystLAB` folder on your computer:

1. Open the **`Session00`** sub-folder.
2. Open the file **`AI_AnalystLAB00.ipynb`** — this is the Session 00 notebook.
3. Follow the instructions inside it to install Python, set up a virtual environment, install the course packages, and run a small test that confirms everything works.

The Session 00 notebook is the **next** step after this README. If you cannot open `.ipynb` files yet, do not worry — the notebook itself will tell you how to install Visual Studio Code, which is the program we use to read and run notebooks.

---

![](_img/DK_Logo_White_150.png)

## Course details

- **Course:** AI Analyst LAB
- **Year:** 2026
- **Lecturer:** [Goran S. Milovanović, PhD](https://www.linkedin.com/in/gmilovanovic/), Chief Scientist & Owner, [DataKolektiv](https://datakolektiv.com)
- **Contact:** [hello@datakolektiv.com](mailto:hello@datakolektiv.com)
- **License:** [GPLv3](LICENSE)
