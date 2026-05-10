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

You will go through three numbered steps:

1. Install **Git** on your computer (skip if you already have it).
2. **Clone** the AI Analyst LAB repository onto your computer.
3. Learn how to **pull updates** later in the course.

Because this repository is **public**, you do not need a GitHub account, an invitation, or a password to clone it.

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
