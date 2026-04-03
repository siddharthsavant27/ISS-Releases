# Intelligent Surveillance System 🎥

Welcome to the **Intelligent Surveillance System** release repository. This repository hosts the standalone Windows executable (`.exe`) for our real-time AI-powered CCTV analytics suite. 

No Python installation, no confusing setups, and no terminal commands are required—just download and run.

---

## 🚀 Easy Installation

1. Go to the [**Releases**](../../releases) tab on the right side of this repository.
2. Download the latest `Intelligent-surveillance-system.exe` file.
3. Place the file anywhere on your Windows machine (Desktop, Documents, etc.).
4. Double-click the `.exe` to launch the application instantly.

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

## 🛠️ FAQs & Support

**Does this require an internet connection?**
No, edge-AI tracks and processes all the surveillance frames purely locally.

**Where do the downloaded reports go?**
The `.csv` files will explicitly be generated inside a `reports/` folder located in the exact same directory where you placed the `.exe` file.

**My application is being flagged by Windows Defender?**
Since this executable hasn't been put through an expensive Microsoft code-signing certificate yet, Windows SmartScreen may halt it initially. Click **"More Info" -> "Run Anyway"**.

---
*Designed & Built for eZpedal by Siddharth | 2026*
