# Win323 - Complete Standalone Installation Guide

## Quick Start - Choose Your Operating System

### 🪟 Windows
1. **Download** `setup.bat` from the repository
2. **Right-click** → "Run as Administrator"
3. **Wait** for automatic download and installation (~10-15 minutes)
4. **Done!** Win323 opens automatically when complete

Alternative with Python:
```batch
python setup.py
```

### 🍎 macOS
1. **Open Terminal**
2. **Download** `setup.sh` or run:
```bash
chmod +x setup.sh
./setup.sh
```
3. **Wait** for automatic download and installation (~10-15 minutes)
4. **Done!** Win323 is ready to use

### 🐧 Linux
1. **Open Terminal**
2. **Download** `setup.sh` or run:
```bash
chmod +x setup.sh
./setup.sh
```
3. **Wait** for automatic download and installation (~10-15 minutes)
4. **Done!** Win323 is ready to use

## What the Setup Script Does

The setup scripts automate everything:

1. ✅ **Check System** - Detects OS and architecture
2. ✅ **Download Node.js** - If not already installed (if needed)
3. ✅ **Install Dependencies** - All npm packages
4. ✅ **Build Application** - Compiles TypeScript to JavaScript
5. ✅ **Create Executable** - Builds standalone `.exe` (Windows), `.app` (macOS), or `.AppImage` (Linux)
6. ✅ **Create Launcher** - Easy-to-use launch scripts
7. ✅ **Create Shortcut** - Desktop shortcut for quick access
8. ✅ **Generate README** - Quick reference guide

## Installation Steps Breakdown

### Step 1: Requirements Check
- Checks if Python 3 is installed
- Checks if Node.js is installed
- Downloads Node.js if needed (~200MB)

### Step 2: Dependency Installation
- Downloads and installs all npm packages
- Installs Electron, React, TypeScript, and build tools
- Size: ~500MB of dependencies

### Step 3: Application Build
- Compiles TypeScript code to JavaScript
- Bundles React components
- Optimizes for distribution

### Step 4: Executable Creation
The script creates a complete standalone executable:

**Windows:**
- `Win323.exe` (standalone executable)
- `launch_win323.bat` (launcher script)
- Ready for distribution

**macOS:**
- `Win323.app` (complete macOS application)
- `launch_win323.sh` (launcher script)
- Ready for distribution

**Linux:**
- `Win323` (AppImage executable)
- `launch_win323.sh` (launcher script)
- Ready for distribution

### Step 5: Installation Complete
After setup, you'll have:
```
win323_dist/
├── Win323.exe (or .app / AppImage)
├── launch_win323.bat (or .sh)
├── README.txt
└── [supporting files]
```

## Running Win323

After setup completes, to launch Win323:

### Windows
- **Option 1:** Double-click `Win323.exe` in the `win323_dist` folder
- **Option 2:** Double-click `launch_win323.bat`
- **Option 3:** Click the desktop shortcut "Win323"

### macOS
- **Option 1:** Double-click `Win323.app` in the `win323_dist` folder
- **Option 2:** Double-click `launch_win323.sh`

### Linux
- **Option 1:** Double-click `Win323` in file manager
- **Option 2:** Run in terminal: `./launch_win323.sh`

## First Use

When you launch Win323 for the first time:

1. **Welcome Screen** appears with "Get Started" button
2. **Click "Get Started"** to enter Setup Wizard
3. **Configure VM:**
   - Enter VM name (e.g., "Windows-Work")
   - Choose OS (Windows 10 or 11)
   - Set CPU cores (recommended: 4)
   - Set RAM (recommended: 8GB)
   - Set storage (recommended: 100GB)
4. **Click "Launch VM"**
5. **Automatic Setup** begins:
   - Creates virtual machine (30%)
   - Configures resources (60%)
   - Initializes system (90%)
   - Completes setup (100%)
6. **VM Launches** automatically with everything ready!

## Troubleshooting Setup

### "Python not found" Error
**Windows:**
- Download Python from https://www.python.org/downloads/
- Install with "Add Python to PATH" checked
- Run setup again

**macOS/Linux:**
```bash
# macOS
brew install python3

# Ubuntu/Debian
sudo apt-get install python3
```

### "Node.js installation failed" Error
The script will try to auto-install Node.js. If it fails:
1. Download from https://nodejs.org/
2. Install manually
3. Run setup script again

### Setup Takes Too Long
- First setup takes 10-20 minutes (downloads ~1GB of dependencies)
- Subsequent setups are much faster
- Internet speed affects download time
- Modern SSD recommended for faster builds

### "npm not found" Error After Setup
- Node.js may not have been added to PATH
- Restart your computer
- Run setup again

## System Requirements

**Minimum:**
- OS: Windows 10, macOS 10.13, or Linux (Ubuntu 18.04+)
- RAM: 8GB
- Storage: 50GB free space
- CPU: 2 cores with virtualization support

**Recommended:**
- OS: Windows 11, macOS 11+, or Ubuntu 20.04+
- RAM: 16GB
- Storage: 256GB SSD
- CPU: 4+ cores with virtualization support

## What's Inside the Executable

The Win323 executable contains everything you need:
- ✅ Electron runtime
- ✅ React UI components
- ✅ VM management engine
- ✅ All dependencies bundled
- ✅ No need to install anything else!

## Uninstalling Win323

### Windows
1. Delete the `win323_dist` folder
2. Delete the desktop shortcut "Win323" (if created)
3. Done!

### macOS
1. Drag `Win323.app` to Trash
2. Empty Trash
3. Done!

### Linux
1. Delete the `win323_dist` folder
2. Done!

## Getting Help

If you encounter issues:

1. **Check System Requirements** - Ensure your system meets minimum requirements
2. **Enable Virtualization** - Check BIOS that CPU virtualization is enabled
3. **Free Disk Space** - Ensure 50GB+ free space
4. **Report Issues** - Visit https://github.com/zero-webs/win323/issues

## Next Steps After Installation

1. ✅ Run setup script
2. ✅ Launch Win323
3. ✅ Create first VM with one-click setup
4. ✅ Enjoy seamless Windows virtualization!

---

**Win323** - Making Windows virtualization easy for everyone! 🚀
