#### For Mac 



   
# macOS Python Setup 

## Purpose
- Installing the latest stable Python version on macOS
- Creating a virtual environment

---

## Requirements
- Internet connection
- Visual Studio Code (recommended)

---

## Setup Steps

### 1. Install Python using browser

- Go to [Python Downloads](https://www.python.org/downloads/) 
- Download recent stable package of Python file for macOS and double click to install it
- GO to terminal, and enter `python --version` to check the installation.

### 1. Install Python using Homebrew

- If you do not have Homebrew, install it first:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- Then install python
```bash
brew install python
```
- Verify the installation using `python3 --version`.

### 1. Creating virtual environment
- Navigate to your project directory
```bash
cd path/to/your/project
```
- Create a virtual environment named "test", 

```bash
python3 -m venv .test
```
-  To activate the environment
```bash
source .venv/bin/activate
```