# AI Analyst LAB

![](_img/Ghost_TheSyntheticBanner.png)

Welcome! This repository contains the course material for **AI Analyst LAB**, a hands-on course on using AI as a data analyst, by [DataKolektiv](https://datakolektiv.com).

**Lecturer:** [Goran S. Milovanović, PhD](https://www.linkedin.com/in/gmilovanovic/), Chief Scientist & Owner, DataKolektiv

---

## What this README is for

This README walks you through the **one-time setup** of getting the course code onto your computer. After this, every week your instructor will add new sessions, and you will just run a single command (`git pull`) to update your local copy.

If you have never used GitHub, Git, or a terminal before, **do not worry** — every step is explained, and you cannot break anything by following the instructions. Plan to spend about **10–15 minutes** on this.

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
- **Personal Access Token (PAT)** — a long random string that acts like a password. We will create one. Git uses it to prove that you are allowed to download our private repository.

---

## What you will do (overview)

You will go through six numbered steps:

1. Make sure you have a free **GitHub account**.
2. **Accept the invitation** that your instructor sent you.
3. Generate a **Personal Access Token (PAT)**.
4. Install **Git** on your computer (skip if you already have it).
5. **Clone** the repository onto your computer.
6. Learn how to **pull updates** later in the course.

Steps 1–4 happen in your web browser. Steps 5–6 happen in your terminal.

---

## Step 1 — GitHub account

### If you already have a GitHub account

Skip ahead to Step 2. **But first — make sure your instructor has your GitHub username** (the short name you chose on GitHub, *not* your email address). Email it to them now if you have not already.

### If you do NOT have a GitHub account

1. Open [https://github.com/signup](https://github.com/signup) in your browser.
2. Enter your **email address** and click **Continue**.
3. Create a **password** and click **Continue**.
4. Choose a **username**. This will be your public identity on GitHub — pick something professional (e.g., your full name without spaces). Click **Continue**.
5. Solve the "verify you are human" puzzle.
6. Click **Create account**.
7. GitHub will email you a **verification code**. Paste it on the next screen.
8. You can skip any onboarding questions GitHub asks ("How will you use GitHub?" etc.) — click **Skip personalization** at the bottom of the form.
9. **Email your GitHub username to your instructor** (the short name from step 4 — *not* your email address).
10. Wait for the instructor to send you an invitation, then continue with Step 2.

---

## Step 2 — Accept the invitation to the course repository

Your instructor will invite you to this repository. Once they do:

1. Check the inbox of the email associated with your GitHub account. You will receive a message from `noreply@github.com`. The subject line looks like **"\[GitHub\] @goranmilovanovic has invited you to ..."**.
2. Open the email and click the **"View invitation"** button.
3. If you are not already signed in to GitHub, sign in.
4. On the page that opens, click **"Accept invitation"**.

**Verify it worked:** open [https://github.com/datakolektiv/AI_AnalystLAB](https://github.com/datakolektiv/AI_AnalystLAB) in your browser while signed in.

- If the page loads and shows the repository, you have access — continue to Step 3.
- If you see **"404 — page not found"**, the invitation has not been accepted yet. Go back to step 2 above, or contact your instructor.

---

## Step 3 — Generate a Personal Access Token (PAT)

A PAT is a long random string that Git will use as your password. We will create a token restricted to **only this one repository** and **only the read permission** — it cannot be used for anything else, and it is safe even if accidentally shared (though you should still keep it private).

1. Open this link in your browser: [https://github.com/settings/personal-access-tokens/new](https://github.com/settings/personal-access-tokens/new)
2. If GitHub asks you to confirm your identity (a dialog called "Sudo mode"), enter your GitHub password.
3. Fill in the form **exactly as follows**:
   - **Token name:** `AI_AnalystLAB-clone`
   - **Expiration:** select **90 days** (or longer if you prefer).
   - **Description:** `For pulling course updates` (optional).
   - **Resource owner:** click the dropdown and select **`datakolektiv`**.
   - **Repository access:** click **"Only select repositories"**, then in the new dropdown that appears choose **`datakolektiv/AI_AnalystLAB`**.
   - **Permissions** → expand **"Repository permissions"** → scroll down to **"Contents"** → set it to **"Read-only"**.
4. Click the green **"Generate token"** button at the bottom of the page.
5. A new page appears with your token. It is a long string starting with `github_pat_…`.
   - **Copy it immediately** using the small "copy" button next to the token.
   - **Paste it somewhere safe** — for example, a temporary text file on your desktop, or a password manager. **GitHub will NOT show this token again.** If you lose it, you will have to repeat this step to generate a new one.

---

## Step 4 — Install Git (skip if you already have it)

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

- If you see something like `git version 2.50.x`, you already have Git — **skip to Step 5**.
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

## Step 5 — Clone the repository

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
4. Git will prompt you for two pieces of information:
   - **`Username for 'https://github.com':`** — type your **GitHub username** (the short name you chose in Step 1 — *not* your email address) and press ENTER.
   - **`Password for ...`** — **paste the PAT** you saved in Step 3 and press ENTER.

   > ⚠️ **Important:** when you paste the PAT, the terminal **does not show the characters** — not even dots. That is a security feature, not a bug. Just paste (CTRL + V on Windows/Linux, CMD + V on macOS) and press ENTER.

5. After a few seconds, you should see output similar to:
   ```
   Cloning into 'AI_AnalystLAB'...
   remote: Enumerating objects: ...
   Receiving objects: 100% ...
   ```
   When your terminal prompt comes back, the clone is complete.

6. Verify a new folder named **`AI_AnalystLAB`** appeared:
   - **Windows:** type `dir` and press ENTER.
   - **macOS / Linux:** type `ls` and press ENTER.

---

## Step 6 — Pulling future updates

Whenever your instructor adds new course material, you do **not** clone the repository again. Instead, you "pull" the new changes into your existing folder.

Open your terminal and run:

```
cd AI_AnalystLAB
git pull
```

If you opened a new terminal session and `cd AI_AnalystLAB` does not work, use the full path:

- **Windows:** `cd C:\Users\<your-name>\AI_AnalystLAB`
- **macOS / Linux:** `cd ~/AI_AnalystLAB`

Your PAT is cached on your computer, so Git will **not** ask for credentials again — until the token expires (after 90 days, or whatever you chose in Step 3). When the token expires, repeat **Step 3** to create a fresh PAT.

---

## Common things that go wrong

- **`Authentication failed`** — you typed your *email address* as the username instead of your GitHub *username*, or the PAT was pasted with extra whitespace. Try the clone again carefully.
- **`Repository not found` or `404`** — you have not accepted the invitation. Go back to **Step 2**.
- **`git: command not found`** or **`'git' is not recognized`** — Git is not installed, or your terminal has not picked it up yet. Close the terminal, open a new one, and try again. If that still does not work, go back to **Step 4**.
- **A browser window opened asking you to sign in to GitHub** — that is fine. Sign in there and let "Git Credential Manager" finish. The clone should then proceed without asking for your PAT. If that works, you do not strictly need the PAT — but keep it for backup.

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
