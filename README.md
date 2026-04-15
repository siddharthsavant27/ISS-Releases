# Visionize AI Updates🤖

Welcome to the **Intelligent Surveillance System** release repository. This repository hosts the standalone Windows executable (`.exe`) for our real-time AI-powered CCTV analytics suite. 

No Python installation, no confusing setups, and no terminal commands are required—just download and run.

---

## 🚀 Easy Installation

1. Go to the [**Releases**](../../releases) tab on the right side of this repository.
2. Download the latest `ISS-Launcher.exe` file.
3. Place the file anywhere on your Windows machine (Desktop, Documents, etc.).
4. Double-click the launcher to automatically download and start the application.

> **💡 Pro Tip:** The launcher handles everything—downloading updates, managing versions, and launching the main app. You only need to run the launcher each time!

---

## 🚀 How the Launcher Works

The `ISS-Launcher.exe` is a smart bootstrap that ensures you always have the latest version of the Intelligent Surveillance System.

### Automatic Update Flow

1. **Version Check**: When launched, the launcher checks your current version (stored in `version.txt`)
2. **GitHub Query**: It fetches the latest release tag from GitHub API
3. **Smart Comparison**: If a newer version exists, it automatically downloads it
4. **Seamless Launch**: After updating (or if already up-to-date), it launches the main `app.exe`
5. **Silent Error Handling**: If offline or GitHub is unreachable, it launches your existing version without interruption

### First-Time Setup

When you run the launcher for the first time:
- No `app.exe` exists locally
- The launcher downloads the latest version automatically
- A friendly progress window shows "Downloading ISS Update..."
- Once complete, the main application launches

### Update Window

During updates, you'll see a clean overlay window

---

## 🌟 Key Features

The Intelligent Surveillance System operates entirely on your local machine using a robust standalone desktop GUI. It continuously processes your screen or camera feed in real-time using ONNX-accelerated AI models.

### 🔍 Monitoring Modes
- **🧑‍🤝‍🧑 Person Detection**: Tracks and counts unique human pedestrians moving through your field of view dynamically.
- **🚲 Bike Violations**: Accurately detects and counts illegal motorcycle/bike presences in restricted zones (like footpaths).
- **🚗 Traffic Flow Tracker**: Monitors and estimates 2-wheeler and 4-wheeler vehicle traffic density in real-time.

### 📊 Professional Data Export
- **Automated Midnight Reports**: The desktop app runs silently in the background and automatically generates a timestamped `.csv` file detailing your tracking counts at exactly **12:00 AM** every night.
- **Manual Data Dumps**: Need standard reports during your shift? Click the "Download Report" button on our Tkinter dashboard to instantly export the current counts to the `reports/` folder.

---

## 📁 File Structure

After first launch, your folder will contain:
Your chosen folder/
├── ISS-Launcher.exe # The launcher (run this)
├── app.exe # Main application (auto-downloaded)
├── version.txt # Current version tracking
└── reports/ # Generated CSV reports folder

---

## 🛠️ FAQs & Support

**Does this require an internet connection?**
- **First launch**: Yes (to download the main application)
- **Subsequent launches**: No—the launcher works offline and launches your existing version
- **Edge-AI tracking**: No internet required after initial download

**What if I'm offline when an update is available?**
The launcher silently fails the version check and launches your current version. Next time you're online, it will auto-update.

**Where do the downloaded reports go?**
The `.csv` files will explicitly be generated inside a `reports/` folder located in the exact same directory where you placed the `.exe` file.

**My application is being flagged by Windows Defender?**
Since this executable hasn't been put through an expensive Microsoft code-signing certificate yet, Windows SmartScreen may halt it initially. Click **"More Info" -> "Run Anyway"**.

**How do I manually force an update?**
Delete the `version.txt` file and run the launcher again—it will re-download the latest version.

**Can I run the launcher from a network drive?**
Yes! The launcher and main app work perfectly from network locations, USB drives, or any writeable directory.

---

## 🔧 Technical Details

- **Launcher Language**: Python (compiled to standalone EXE with PyInstaller)
- **Update Mechanism**: GitHub API v3 REST calls
- **Download Method**: Chunked streaming for reliability
- **Version Tracking**: Simple text file (`version.txt`)
- **Process Management**: Detached subprocess spawn (launcher closes after starting main app)

---

## 📝 Version History

- **v2.0+**: Introduced intelligent launcher with auto-update capabilities
- **v1.x**: Manual download required for each update

---

*Designed & Built for eZpedal by Siddharth | 2026*
