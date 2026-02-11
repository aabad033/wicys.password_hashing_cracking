# wicys.password_hashing_cracking

Welcome to our Hashing / Password Cracking workshop!

See [Hashing](Hashing.md)

See John The Ripper documentation: https://www.openwall.com/john/doc/ 

# John the Ripper Installation Guide
This guide walks through installing John the Ripper based on your environment.

Choose the setup that matches your system:

🪟 WSL (Windows Subsystem for Linux)

🍎 macOS (Homebrew) 

🐧 Linux VM (Ubuntu / Kali)


Windows Subsystem for Linux (WSL) is a component of Microsoft Windows that allows the use of a Linux environment from within Windows, foregoing the overhead of a virtual machine and being an alternative to dual booting.

# Installing John the Ripper

## For WSL:

Step 1: Install WSL (If Not Installed Yet)
Open PowerShell as Administrator and run:
```bash
wsl --install
```

Restart your computer when prompted.

After reboot:
Open Ubuntu from the Start Menu
Create a username + password

Step 2: Update the System

Inside the Ubuntu terminal:
```bash
sudo apt update && sudo apt upgrade -y
```
This ensures all packages are current.

Step 3: Install Required Base Tools:
```bash
sudo apt install john build-essential git wget curl unzip -y
```

Step 4: Verify Installation
```bash
john --version
```

## For Homebrew
Step 1: Check if Homebrew is Installed

Open Terminal and run:
```bash
brew --version
```

If not, then:
Step 2: Install Homebrew
Run:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installation, you may need to add Homebrew to your PATH. The installer will show you a command like:
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Run what it tells you.

Verify:
```bash
brew --version
```

Step 4: Install John the Ripper

Run:
```bash
brew update
brew install john
```
Verify:
```bash
john --version
```

## For Linux / Kali VM
You only need to install John The Ripper (Kali already has this installed):


Step 3: Install John the Ripper
```bash
brew update
brew install john
```
Open terminal and type:
```bash
sudo apt update && sudo apt upgrade -y
```
then
```bash
sudo apt install john -y
```
check:
```bash
john --version
```

