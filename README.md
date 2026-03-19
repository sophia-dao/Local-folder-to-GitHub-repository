# Publishing a Local Folder to GitHub (VS Code + Git)

![GitHub repo size](https://img.shields.io/github/repo-size/sophia-dao/Local-folder-to-GitHub-repository)
![GitHub last commit](https://img.shields.io/github/last-commit/sophia-dao/Local-folder-to-GitHub-repository)
![GitHub stars](https://img.shields.io/github/stars/sophia-dao/Local-folder-to-GitHub-repository?style=social)
![GitHub forks](https://img.shields.io/github/forks/sophia-dao/Local-folder-to-GitHub-repository?style=social)
![License](https://img.shields.io/github/license/sophia-dao/Local-folder-to-GitHub-repository)

This guide shows **two ways** to publish a local project to GitHub:

* 🧭 **Manual (create repo on GitHub website)**
* ⚡ **Automatic (create repo from local using VS Code or CLI)**

---

## Table of Contents

* [🚀 Prerequisites](#-prerequisites)
* [📁 1. Open Your Project in VS Code](#-1-open-your-project-in-vs-code)
* [🔧 2. Initialize Git](#-2-initialize-git)
* [➕ 3. Stage and Commit Files](#-3-stage-and-commit-files)
* [🧭 Method A — Create Repo on GitHub Website](#-method-a--create-repo-on-github-website)
* [⚡ Method B — Create Repo from Local (No Website)](#-method-b--create-repo-from-local-no-website)

  * [Using VS Code](#using-vs-code)
  * [Using GitHub CLI](#using-github-cli)
* [📤 Push to GitHub](#-push-to-github)
* [🔁 Future Updates](#-future-updates)
* [⚠️ Common Issues](#️-common-issues)
* [💡 Tips](#-tips)

---

## 🚀 Prerequisites

* Git installed (`git --version`)
* A GitHub account
* VS Code installed
* (Optional) SSH configured for GitHub

---

## 📁 1. Open Your Project in VS Code

* Open VS Code
* Go to **File → Open Folder**
* Select your project folder

---

## 🔧 2. Initialize Git

Open the terminal in VS Code:

```bash
git init
```

---

## ➕ 3. Stage and Commit Files

```bash
git add .
git commit -m "Initial commit"
```

---

## 🧭 Method A — Create Repo on GitHub Website

1. Go to [https://github.com](https://github.com)
2. Click **New repository**
3. Enter a repository name
4. **Do NOT** initialize with README, `.gitignore`, or license
5. Click **Create repository**

### 🔗 Connect Local Repo to GitHub

#### Option A — Using SSH (recommended)

```bash
git remote add origin git@github.com:YOUR_USERNAME/YOUR_REPO.git
```

#### Option B — Using HTTPS

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
```

---

## ⚡ Method B — Create Repo from Local (No Website)

### Using VS Code

1. Go to **Source Control** (left sidebar)
2. Click **Initialize Repository** (if needed)
3. Click **Commit**
4. Click **Publish to GitHub**
5. Choose **Public** or **Private**

👉 This automatically:

* creates the repo on GitHub
* sets the remote
* pushes your code

---

### Using GitHub CLI

```bash
gh repo create YOUR_REPO --source=. --private --push
```

👉 This command:

* creates the repository
* links it as `origin`
* pushes your code

---

## 📤 Push to GitHub

(Needed for Method A or if you didn’t auto-push)

```bash
git branch -M main
git push -u origin main
```

---

## 🔁 Future Updates

After the first push, use:

```bash
git add .
git commit -m "update"
git push
```

---

## ⚠️ Common Issues

### ❌ Remote already exists

```bash
git remote set-url origin <repo-url>
```

---

### ❌ Repository not found

* Make sure the repo exists on GitHub
* Check that the username and repo name are correct
* Verify you have access permissions

---

### ❌ HTTPS authentication issues

GitHub no longer supports passwords for HTTPS.

Use one of:

* GitHub CLI (`gh auth login`)
* Personal Access Token
* Or switch to SSH

---

### ❌ SSH prompts every time

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

---

## 💡 Tips

* Use `.gitignore` to avoid committing unnecessary files (e.g., `node_modules`, `.DS_Store`)
* Use meaningful commit messages
* Push frequently to avoid losing work

---

## ✅ Done!

Your project should now be live on GitHub 🎉
