# Development Environment Setup Guide - Weeks 1-2

## Introduction

Welcome to the first step of your journey to becoming an AI engineer! In these first two weeks, we'll set up your development environment - think of this as building your workshop with all the tools you'll need. Don't worry if some terms are unfamiliar; we'll explain everything as we go along.

## Week 1: Basic Setup and Understanding

### Day 1-2: Understanding Development Environments

#### What is a Development Environment?
A development environment is like your digital workspace - it's where you'll write, test, and run your code. Think of it as a carpenter's workshop, but for programming. Just as a carpenter needs specific tools organized in a certain way, programmers need specific software tools set up correctly to work effectively.

#### Core Components We'll Install:
1. Python: The programming language we'll use
2. Conda: A tool that helps manage Python and other packages
3. Git: A system to track changes in your code
4. Visual Studio Code: A powerful text editor for writing code

### Day 3-4: Command Line Basics

The command line is a text-based way to interact with your computer. While it might seem intimidating at first, it's incredibly powerful and essential for programming.

#### Essential Command Line Commands:
```bash
# Windows (Command Prompt)
dir                     # List files in current directory
cd folder_name         # Change directory
cd ..                  # Go up one directory
mkdir folder_name      # Create new directory
echo Hello > file.txt  # Create a text file

# macOS/Linux (Terminal)
ls                     # List files in current directory
cd folder_name         # Change directory
cd ..                  # Go up one directory
mkdir folder_name      # Create new directory
touch file.txt         # Create a text file
```

### Day 5: Installing Python

#### Windows:
1. Visit python.org/downloads
2. Download the latest Python version (3.11 or newer)
3. Run the installer
4. **Important**: Check "Add Python to PATH" during installation
5. Verify installation:
   ```bash
   python --version
   ```

#### macOS:
1. Open Terminal
2. Install Homebrew if not installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. Install Python:
   ```bash
   brew install python
   ```

#### Linux:
```bash
sudo apt update
sudo apt install python3
```

## Week 2: Advanced Setup and Integration

### Day 1-2: Installing and Configuring Conda

Conda is a package manager that helps you install and manage Python packages and their dependencies.

#### Installing Miniconda:
1. Visit docs.conda.io/en/latest/miniconda.html
2. Download the appropriate installer for your system
3. Run the installer
4. Verify installation:
   ```bash
   conda --version
   ```

#### Creating Your First Environment:
```bash
# Create a new environment
conda create -n aienv python=3.11

# Activate the environment
conda activate aienv

# Verify Python version in the environment
python --version
```

### Day 3-4: Installing Git and Basic Configuration

#### Windows:
1. Download Git from git-scm.com
2. Run the installer (use default settings)
3. Open Git Bash after installation

#### macOS:
```bash
brew install git
```

#### Linux:
```bash
sudo apt install git
```

#### Basic Git Configuration:
```bash
# Configure your identity
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set default branch name
git config --global init.defaultBranch main
```

### Day 5: Installing and Setting Up Visual Studio Code

1. Download VS Code from code.visualstudio.com
2. Install recommended extensions:
   - Python
   - Jupyter
   - Git Graph
   - Python Indent
   - autoDocstring

#### Configuring VS Code:
1. Open VS Code
2. Press Ctrl+Shift+P (Windows/Linux) or Cmd+Shift+P (macOS)
3. Type "Python: Select Interpreter"
4. Choose the Python from your conda environment

## Final Steps and Verification

### Testing Your Setup:
1. Open VS Code
2. Create a new file named `test.py`
3. Enter this code:
   ```python
   print("Hello, AI Engineering!")
   ```
4. Run the file using the play button

### Creating Your First Git Repository:
```bash
# Create a new directory
mkdir ai_learning

# Navigate to it
cd ai_learning

# Initialize git repository
git init

# Create a README file
echo "# AI Engineering Learning Journey" > README.md

# Add and commit the file
git add README.md
git commit -m "Initial commit"
```

## Troubleshooting Guide

### Common Issues and Solutions:

1. **Python not found in PATH**
   - Windows: Reinstall Python, ensuring "Add to PATH" is checked
   - macOS/Linux: Add Python to PATH manually in ~/.bashrc or ~/.zshrc

2. **Conda not recognized**
   - Windows: Restart terminal after installation
   - macOS/Linux: Source your shell configuration file

3. **Git authentication issues**
   - Verify your git config settings
   - Ensure email matches your Git provider account

## Next Steps

Once you've completed this setup:
1. Practice basic command line operations daily
2. Create a few test Python files
3. Make some test git commits
4. Get comfortable with VS Code's interface

Remember: Take your time with this setup phase. A solid foundation will make your learning journey much smoother. If you encounter any issues, try searching for the exact error message online - this is a crucial skill in programming!
