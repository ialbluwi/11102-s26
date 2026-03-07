---
layout: page
title: Installation Guide
description: Complete setup guide for VSCode, Python, and GitHub Copilot
nav_exclude: true
---

# Installation Guide

This guide will help you install VSCode, Python, and GitHub Copilot on your computer. Follow the instructions for your operating system (Windows, macOS, or Linux).

## Table of Contents

1. [VSCode Installation](#vscode-installation)
2. [Python Installation](#python-installation)
3. [VSCode + Python Setup](#vscode--python-setup)
4. [GitHub Copilot Installation](#github-copilot-installation)
5. [Troubleshooting](#troubleshooting)

---

## VSCode Installation

### Windows

1. Visit [code.visualstudio.com](https://code.visualstudio.com)
2. Click the **Download** button for Windows
3. Run the downloaded installer (`.exe` file)
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose installation location (default is fine)
   - **Important**: Check "Add to PATH" (allows you to open VSCode from terminal)
   - Check other options as desired (Create desktop icon, Add "Open with Code" actions)
5. Click **Install** and wait for completion
6. Click **Finish** to launch VSCode

**Verify Installation**: Open either Command Prompt or PowerShell:
- **Command Prompt**: Press `Win + R`, type `cmd`, and press Enter (or search for "Command Prompt" in the Start menu)
- **PowerShell**: Press `Win + R`, type `powershell`, and press Enter (or search for "PowerShell" in the Start menu)

Then type:
```
code --version
```

You should see the VSCode version number (e.g., `1.XX.X`).

### macOS

**Option 1: Direct Download (Recommended for beginners)**

1. Visit [code.visualstudio.com](https://code.visualstudio.com)
2. Click **Download** for Mac
3. The browser will download a `.zip` file
4. In Finder, double-click the zip to extract it
5. Drag the **Visual Studio Code.app** to the **Applications** folder
6. Launch VSCode from Applications or Spotlight search (⌘ + Space, type "code")
7. **Enable the `code` command in Terminal:**
   - Open VSCode
   - Press `⌘+Shift+P` to open the Command Palette
   - Type and run **"Shell Command: Install 'code' command in PATH"**
   - Restart your terminal

**Option 2: Using Homebrew (For advanced users)**
```bash
brew install --cask visual-studio-code
```

**Verify Installation**: Open Terminal and type:
```bash
code --version
```

You should see the VSCode version number (e.g., `1.XX.X`).

### Linux

**Ubuntu/Debian:**

The easiest method is to download and install the `.deb` package directly from Microsoft, which also sets up the apt repository for automatic updates:

1. Visit [code.visualstudio.com/download](https://code.visualstudio.com/download)
2. Click the **.deb** button to download the package
3. Install it with:
```bash
sudo apt install ./code_*.deb
```

**Fedora/RHEL:**
```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\nautorefresh=1\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" | sudo tee /etc/yum.repos.d/vscode.repo > /dev/null
dnf check-update
sudo dnf install code
```

**Arch:**
```bash
sudo pacman -S code
```

**Verify Installation**: Open terminal and type:
```bash
code --version
```

You should see the VSCode version number (e.g., `1.XX.X`).

---

## Python Installation

### Windows

1. Visit [python.org](https://www.python.org/downloads/)
2. Click the yellow **Download Python** button (gets the latest version)
3. Run the installer (`.exe` file)
4. **CRITICAL**: Check the box "Add Python to PATH" at the bottom
5. Click **Install Now**
6. Wait for installation to complete
7. Close the installer

**Verify Installation**: Open either Command Prompt or PowerShell:
- **Command Prompt**: Press `Win + R`, type `cmd`, and press Enter (or search for "Command Prompt" in the Start menu)
- **PowerShell**: Press `Win + R`, type `powershell`, and press Enter (or search for "PowerShell" in the Start menu)

Then type:
```
python --version
```

You should see: `Python 3.x.x` (version number may differ)

### macOS

**Option 1: Using Homebrew (Recommended)**

If you don't have Homebrew installed, run:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then install Python:
```bash
brew install python3
```

**Option 2: Direct Download**

1. Visit [python.org](https://www.python.org/downloads/)
2. Click **Download Python**
3. Run the installer
4. Follow the installation wizard
5. Run the "Install Certificates.command" script if prompted

**Verify Installation**: Open Terminal and type:
```bash
python3 --version
```

You should see: `Python 3.x.x`

### Linux

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv
```

**Fedora/RHEL:**
```bash
sudo dnf install python3 python3-pip
```

**Arch:**
```bash
sudo pacman -S python python-pip
```

**Verify Installation**: Open terminal and type:
```bash
python --version    # Arch uses 'python' by default
python3 --version   # Ubuntu/Debian/Fedora use 'python3'
```

You should see: `Python 3.x.x`

---

## VSCode + Python Setup

Once you have both VSCode and Python installed, configure them to work together.

### Step 1: Install Python Extension in VSCode

1. Open VSCode
2. Click the **Extensions** icon on the left sidebar (or press `Ctrl+Shift+X` / `⌘+Shift+X`)
3. Search for **"Python"** (look for the official one by Microsoft)
4. Click **Install**
5. Wait for installation to complete

You should also install:

- **Pylance** - For code intelligence (usually installs with Python extension)
- **Pylint** - For code linting (will prompt you to install; click **Install**)

### Step 2: Create a Test Python File

1. Create a new folder for your work (e.g., `python-projects`)
2. Open that folder in VSCode: **File** → **Open Folder**
3. Click **New File** and name it `test.py`
4. Type:
```python
print("Hello, World!")
```

5. Save the file (`Ctrl+S` / `⌘+S`)

### Step 3: Run Your First Python Program

- Right-click the file and select **Run Python File in Terminal**
- Or click the **Run** button (▷ play icon) in the top right corner of the editor

You should see `Hello, World!` printed in the terminal.

### Step 4: Configure Python Interpreter (if needed)

If Python doesn't work, select the correct interpreter:

1. Press `Ctrl+Shift+P` / `⌘+Shift+P` to open Command Palette
2. Type **"Python: Select Interpreter"**
3. Choose the Python version you installed

---

## GitHub Copilot Installation

### Prerequisites

- A GitHub account (free, student, or professional)
- VSCode with Python extension installed

### Step 1: Get GitHub Copilot Access

**For Students:**

1. Visit [github.com/education](https://github.com/education)
2. Sign up for **GitHub Student Developer Pack**
3. You'll get free Copilot Pro access for students
4. Wait for approval (usually instant for students with `.edu` email)

**For Others:**

GitHub offers multiple access options:

- **Copilot Free** (Recommended to start): No credit card required. Includes 2,000 code completions and 50 chat messages per month at no cost. Just sign in with your GitHub account in VSCode.
- **Copilot Pro**: Starts with a **30-day free trial**, then $10/month. Includes unlimited completions and chat.

Visit [github.com/features/copilot](https://github.com/features/copilot) to compare plans and sign up.

### Step 2: Install Copilot Extension in VSCode

1. Open VSCode
2. Click **Extensions** (`Ctrl+Shift+X` / `⌘+Shift+X`)
3. Search for **"GitHub Copilot"** (by GitHub)
4. Click **Install**
5. Wait for installation to complete

### Step 3: Authorize GitHub Copilot

1. After installation, you'll see a notification to authorize
2. Click **Allow** or **Sign In**
3. Your browser will open to GitHub
4. Click **Authorize Visual Studio Code**
5. You'll be redirected back to VSCode
6. Click **Open** to confirm

You should now see a Copilot icon in the sidebar.

### Step 4: Use Copilot

**Start Coding:**

- Copilot activates automatically when you type
- It suggests completions as you code
- Press `Tab` to accept a suggestion
- Press `Escape` to dismiss it
- Press `Ctrl+Enter` / `⌘+Enter` to see multiple suggestions

**Ask Copilot Questions:**

- Click the **Copilot Chat** icon in the sidebar
- Type your question (e.g., "How do I read a file in Python?")
- Copilot will provide code examples and explanations

---

## Troubleshooting

### VSCode Won't Open

**Windows:**

- Try opening PowerShell and typing: `code`
- If that fails, uninstall and reinstall VSCode
- Make sure you selected "Add to PATH" during installation

**macOS:**

- Try: `open /Applications/Visual\ Studio\ Code.app`
- To enable the `code` command in Terminal, use the built-in VSCode method:
  1. Open VSCode
  2. Press `⌘+Shift+P` to open the Command Palette
  3. Type and run **"Shell Command: Install 'code' command in PATH"**
  4. Restart your terminal

**Linux:**

- Use your package manager to reinstall: `sudo apt install --reinstall code` (Ubuntu)

### Python Not Found

**Windows:**

- Add Python to PATH manually:
  1. Search **"Environment Variables"** in Windows
  2. Click **Edit the system environment variables**
  3. Click **Environment Variables** button
  4. Under "User variables", click **New**
  5. Variable name: `PATH`
  6. Variable value: `C:\Users\YourUsername\AppData\Local\Programs\Python\Python312` (adjust version number)
  7. Click **OK** and restart

**macOS:**

- In most cases, `brew install python3` sets up the correct symlinks automatically. If `python3` still isn't found, run:
```bash
  brew link python3
```

- If you need to add it to PATH manually, the path depends on your Mac's chip:

  - **Apple Silicon (M1/M2/M3/M4):**
```bash
    echo 'export PATH="/opt/homebrew/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
    source ~/.zshrc
```

  - **Intel Mac:**
```bash
    echo 'export PATH="/usr/local/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
    source ~/.zshrc
```

- Replace `3.12` with your installed Python version in either case.

**Linux:**

- On Ubuntu/Debian/Fedora, use `python3` instead of `python` in commands.
- On Arch Linux, use `python` (which points to Python 3 by default).

### VSCode Can't Find Python

1. Press `Ctrl+Shift+P` / `⌘+Shift+P`
2. Type **"Python: Select Interpreter"**
3. Choose the correct Python installation
4. If you don't see any options:
   - Close VSCode
   - **Windows**: Open Command Prompt and verify `python --version` works
   - **macOS/Linux**: Open Terminal and verify `python3 --version` works
   - Reopen VSCode

### Copilot Not Appearing

1. Check you're logged into GitHub in VSCode:
   - Click your profile icon (bottom left)
   - Click **Sign in with GitHub**
2. Verify you have Copilot access:
   - Log into [github.com](https://github.com)
   - Check your account settings → Copilot
3. Reinstall the extension:
   - Go to Extensions
   - Find **GitHub Copilot**
   - Click the three dots and select **Uninstall**
   - Restart VSCode
   - Reinstall Copilot

### "Module Not Found" Error

When running Python files:
```
ModuleNotFoundError: No module named '...'
```

**Solution:**

1. Install the missing module using pip:
```bash
   pip install module_name
```

   (or `pip3` on macOS/Linux)

2. Make sure your Python interpreter in VSCode matches where you installed packages:
   - Press `Ctrl+Shift+P` / `⌘+Shift+P`
   - Type **"Python: Select Interpreter"**
   - Choose the correct interpreter

### Keyboard Shortcuts Not Working

If `Ctrl+Shift+X` doesn't work to open Extensions:

**Windows/Linux:**

- Try: **File** → **Preferences** → **Keyboard Shortcuts**
- Search for the command you want
- Click the pencil icon to reassign a shortcut

**macOS:**

- Use `⌘` (Command) instead of `Ctrl`
- Shortcuts are: `⌘+Shift+X` for Extensions, `⌘+Shift+P` for Command Palette

### Still Having Issues?

1. **Check the basics:**
   - Restart VSCode
   - Restart your computer
   - Make sure you have internet connection
2. **Get help:**
   - Visit [VSCode Docs](https://code.visualstudio.com/docs)
   - Search [GitHub Issues](https://github.com/microsoft/vscode/issues)
   - Ask on [Stack Overflow](https://stackoverflow.com) or your course forum
3. **Installation verification:**
   - Open Terminal/PowerShell in VSCode (press `` Ctrl+` ``)
   - Type: `python --version` (or `python3` on Mac/Linux)
   - Type: `pip --version` (or `pip3`)
   - Type: `code --version`
   - All three should show version numbers

---

## Quick Reference

### Essential Commands
```bash
# Check versions
python --version          # (or python3 on Mac/Linux)
pip --version             # (or pip3 on Mac/Linux)
code --version

# Install packages
pip install package_name  # (or pip3 on Mac/Linux)

# Open folder in VSCode
code .                    # (. means current folder)
code /path/to/folder

# Run Python file
python file.py            # (or python3 on Mac/Linux)
```

### Keyboard Shortcuts

| Action          | Windows/Linux  | macOS        |
|-----------------|----------------|--------------|
| Command Palette | `Ctrl+Shift+P` | `⌘+Shift+P`  |
| Extensions      | `Ctrl+Shift+X` | `⌘+Shift+X`  |
| Terminal        | `` Ctrl+` ``   | `` ⌃+` ``    |
| Save            | `Ctrl+S`       | `⌘+S`        |
| Format Code     | `Shift+Alt+F`  | `⇧+⌥+F`      |

Good luck! 🚀