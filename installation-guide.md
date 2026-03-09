---
layout: page
title: Installation Guide
description: Complete setup guide for VSCode, Python, and GitHub Copilot
nav_exclude: true
---

# Installation Guide

This guide will help you install VSCode, Python, and GitHub Copilot on your computer. Follow the instructions for your operating system (Windows, macOS, or Linux).

## Table of Contents

1. [Using the Terminal](#using-the-terminal)
2. [VSCode Installation](#vscode-installation)
3. [Python Installation](#python-installation)
4. [VSCode + Python Setup](#vscode--python-setup)
5. [GitHub Copilot Installation](#github-copilot-installation)
6. [Troubleshooting](#troubleshooting)

---

## VSCode Installation

### Windows

1. Visit [code.visualstudio.com](https://code.visualstudio.com)
2. Click the **Download** button for Windows
3. Run the downloaded installer (`.exe` file)
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose installation location (default is fine)
   - ⚠️ **Important**: Check "Add to PATH" (allows you to open VSCode from [terminal](#using-the-terminal))
   - Check other options as desired (Create desktop icon, Add "Open with Code" actions)
5. Click **Install** and wait for completion
6. Click **Finish** to launch VSCode

### macOS

1. Visit [code.visualstudio.com](https://code.visualstudio.com) and click **Download for macOS**
2. Double-click the downloaded file in your Downloads folder
3. Drag the **Visual Studio Code.app** to the **Applications** folder
4. Launch VSCode from Applications or Spotlight search (⌘ + Space, type "code")
5. Use the Command Palette (`⌘+Shift+P`) and run **"Shell Command: Install 'code' command in PATH"** to enable opening VSCode from the [terminal](#using-the-terminal) with `code` command
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-install-path-command.png' | relative_url }})

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

### Verify Installation
```bash
code --version
```

You should see the VSCode version number (e.g., `1.XX.X`)
![VSCode Extensions view]({{ '/assets/images/installation-guide/terminal-vscode-version.png' | relative_url }})

---

## Python Installation

### Windows

1. Visit [python.org](https://www.python.org/downloads/)
2. Click the yellow **Download Python** button (gets the latest version)
3. Run the installer (`.exe` file)
4. ⚠️ **CRITICAL**: Check the box "Add Python to PATH" at the bottom
5. Click **Install Now**
6. Wait for installation to complete
7. Close the installer

### macOS

1. Visit [python.org](https://www.python.org/downloads/)
2. Click **Download Python**
3. Run the installer
4. Follow the installation wizard

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

### Verify Installation
```bash
python --version    # Windows and Arch use 'python'
python3 --version   # macOS/Ubuntu/Debian/Fedora use 'python3'
```

You should see: `Python 3.x.x`
![VSCode Extensions view]({{ '/assets/images/installation-guide/terminal-python-version.png' | relative_url }})

---

## VSCode + Python Setup

Once you have both VSCode and Python installed, configure them to work together.

### Step 1: Install Python Extension in VSCode

1. Open VSCode
2. Click the **Extensions** icon on the left sidebar (or press `Ctrl+Shift+X` / `⌘+Shift+X`)
3. Search for **"Python"** (look for the official one by Microsoft)
4. Click **Install**
5. Wait for installation to complete

You may also want to install:

- **Pylint** - For code linting (it checks your code for possible errors and style issues).

![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-python-extension.png' | relative_url }})

### Step 2: Create a Test Python File

1. Create a new folder for your work (e.g., `python-projects` on your Desktop)
2. Open that folder in VSCode and select the folder you created
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-open-folder.png' | relative_url }})
3. Click **New File** and select **Python File**
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-new-file.png' | relative_url }})
4. Type in the file:
```python
print("Hello, World!")
```
5. Save the file (`Ctrl+S` / `⌘+S`) and name it `main.py`
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-python-main-file.png' | relative_url }})

### Step 3: Run Your First Python Program

Click the **Run** button (▷ play icon) in the top right corner of the editor

![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-python-main-run.png' | relative_url }})

If that doesn't work, make sure the run configuration is set to "Run Python File" (you can select it from the dropdown next to the Run button)

![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-python-main-run-debug.png' | relative_url }})

VSCode will open the **[Terminal](#using-the-terminal)** panel at the bottom of the window (below the editor).
If you do not see it, open it from **View → Terminal**.
You should see `Hello, World!` printed there.
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-python-main-output.png' | relative_url }})

### Step 4: Configure Python Interpreter (if needed)

If your Python file does not run properly then select the correct interpreter:

1. Press `Ctrl+Shift+P` / `⌘+Shift+P` to open Command Palette
2. Type **"Python: Select Interpreter"**
3. Choose the option that says **Python 3** (this is the Python program VSCode will use to run your code). If you see more than one, pick the newest version.
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-python-interpreter.png' | relative_url }})

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
![VSCode Extensions view]({{ '/assets/images/installation-guide/github-student-developer-pack.png' | relative_url }})

### Step 2: Install Copilot Extension in VSCode

1. Open VSCode
2. Click **Extensions** (`Ctrl+Shift+X` / `⌘+Shift+X`)
3. Search for **"GitHub Copilot"** (by GitHub)
4. Click **Install**
5. Wait for installation to complete
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-copilot-extension.png' | relative_url }})

### Step 3: Authorize GitHub Copilot

1. After installation, you'll see a notification to authorize
2. Click **Allow** or **Sign In**
3. Your browser will open to GitHub
4. Click **Authorize Visual Studio Code**
5. You'll be redirected back to VSCode
6. Click **Open** to confirm

You should now see a Copilot icon in the sidebar.
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-copilot-icon.png' | relative_url }})

### Step 4: Use Copilot

**Start Coding:**

- Copilot activates automatically when you type
- It suggests completions as you code
- Press `Tab` to accept a suggestion
- Press `Escape` to dismiss it
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-copilot-multiple-suggestions.png' | relative_url }})

**Ask Copilot Questions:**

- Click the **Copilot Chat** icon in the top sidebar
- Type your question (e.g., "How do I read a file in Python?")
- Copilot will provide code examples and explanations
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-copilot-chat.png' | relative_url }})

### Step 5: Enable or Disable Copilot

If you want to pause Copilot suggestions, or turn them back on later, you can do it from VSCode.

**Quick toggle from the status bar:**

- Click the Copilot icon in the bottom status bar
- Choose whether to disable or enable suggestions
![VSCode Extensions view]({{ '/assets/images/installation-guide/vscode-copilot-enable-disable.png' | relative_url }})

---

## Using the Terminal

Many of the commands in this guide are run in a *terminal* (also called a *command prompt* or *shell*). A terminal is a program that lets you type text commands to control your computer instead of clicking with a mouse. You can think of it as talking directly to the operating system.

### Opening a terminal

- **Windows**: Search for **Command Prompt** or **PowerShell** in the Start menu, or press `Win+R`, type `cmd` (for Command Prompt) or `powershell`, and press Enter.
- **macOS**: Open **Terminal** from `Applications → Utilities`, or press `⌘+Space` and type `Terminal`.
- **Linux**: Look for **Terminal** in your application menu. You can often press `Ctrl+Alt+T` as a shortcut.

### Example

```bash
# prints "Hello, world" to the screen
echo Hello, world
```
![VSCode Extensions view]({{ '/assets/images/installation-guide/terminal-hello-world.png' | relative_url }})

---

## Troubleshooting

### VSCode Won't Open

**Windows:**

- Try running the following command on the [terminal](#using-the-terminal):
```bash
code
```
- If that fails, uninstall and reinstall VSCode
- Make sure you selected "Add to PATH" during installation

**macOS:**

- Try running the following command on the [terminal](#using-the-terminal):
```bash
open /Applications/Visual\ Studio\ Code.app
```
- To enable the `code` command in [Terminal](#using-the-terminal), open the Command Palette (`⌘+Shift+P`), run **"Shell Command: Install 'code' command in PATH"**, and restart your [terminal](#using-the-terminal)

**Linux:**

- Use your package manager to reinstall: `sudo apt install --reinstall code` (Ubuntu)

### Python Not Found

This appears in the [terminal](#using-the-terminal) when you run a Python command, but your system does not know where Python is.
This usually means one of three things:
- Python is not installed
- You used the wrong command (`python` vs `python3`)
- Python is installed but not added to your PATH.

Example messages:
- Windows: `'python' is not recognized...`
- macOS/Linux: `command not found: python` or `python3: command not found`

**Windows:**

- Add Python to PATH manually:
  1. Search **"Environment Variables"** in Windows
  2. Click **Edit the system environment variables**
  3. Click **Environment Variables** button
  4. Under "User variables", click **New**
  5. Variable name: `PATH`
  6. Variable value: `C:\Users\YourUsername\AppData\Local\Programs\Python\Python312` (adjust version number)
     - Replace `YourUsername` with your Windows account name.
   - To find it, open [Command Prompt](#using-the-terminal) and run: `echo %USERNAME%`
     - Example: if the command shows `aboud`, use `C:\Users\aboud\AppData\Local\Programs\Python\Python312`
   7. Click **OK**, then restart both the [terminal](#using-the-terminal) and VSCode

**macOS:**

Add Python to your PATH manually. The command is different depending on your Mac type:

- **Apple Silicon (M1/M2/M3/M4):** run:
```bash
echo 'export PATH="/opt/homebrew/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

- **Intel Mac:** run:
```bash
echo 'export PATH="/usr/local/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

- Replace `3.12` with the Python version you installed.

**Linux:**

- On Ubuntu/Debian/Fedora, use `python3` instead of `python` in commands.
- On Arch Linux, use `python` (which points to Python 3 by default).

### VSCode Can't Find Python

This issue happens when VSCode is installed correctly, but it cannot detect a usable Python interpreter for your workspace.

Common signs include:
- At the bottom of VSCode (the bottom horizontal strip, called the status bar), you do not see a Python version selected (for example, `Python 3.12`).
- When you try to run a `.py` file, VSCode asks you to select an interpreter, or shows errors like "Python interpreter is invalid/not found".
- Helpful coding features stop working, such as code suggestions/autocomplete (IntelliSense) and warnings for possible mistakes (linting).

Typical causes:
- Python is not installed (or installation is incomplete).
- VSCode is pointing to an old or removed interpreter path.
- The Python extension is not installed or not fully activated.
- The interpreter exists, but VSCode has not selected it for this workspace.

1. Press `Ctrl+Shift+P` / `⌘+Shift+P`
2. Type **"Python: Select Interpreter"**
3. Choose the correct Python installation
4. If you don't see any options:
   - Close VSCode
   - **Windows**: make sure `python --version` produces a Python 3 number
   - **macOS/Linux**: make sure `python3 --version` produces a Python 3 number
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
   - Ask an AI coding agent (e.g., GitHub Copilot Chat in VS Code)
   - Ask on Ed if you still need help
3. **Installation verification:**
   - Open a [terminal](#using-the-terminal) in VSCode (press `` Ctrl+` `` or `` ⌃+` ``)
   - Type: `python --version` (or `python3` on Mac/Linux)
   - Type: `pip --version` (or `pip3`)
   - Type: `code --version`
   - All three should show version numbers

---

## VSCode Keyboard Shortcuts

| Action          | Windows/Linux  | macOS        |
|-----------------|----------------|--------------|
| Command Palette | `Ctrl+Shift+P` | `⌘+Shift+P`  |
| Extensions      | `Ctrl+Shift+X` | `⌘+Shift+X`  |
| Terminal        | `` Ctrl+` ``   | `` ⌃+` ``    |
| Save            | `Ctrl+S`       | `⌘+S`        |
| Format Code     | `Shift+Alt+F`  | `⇧+⌥+F`      |

Good luck! 🚀