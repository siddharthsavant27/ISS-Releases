# Intelligent-surveillance-system 🎥

An advanced, lightweight, real-time Computer Vision CCTV analytics suite. This project leverages the ultra-fast **YOLOv11 ONNX** inference engine wrapped in a beautifully styled, hardware-accelerated native desktop dashboard built with **Tkinter** & **OpenCV**. 

![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![Framework](https://img.shields.io/badge/Framework-ONNX%20%7C%20OpenCV-orange)

## 🚀 Key Features

* **Real-time Analytics Dashboard:** A sleek, fully native Python Tkinter GUI featuring dark slate themes, hardware-accelerated video rendering, CSS-like component alignment, and smooth interactive animations. No browser, Flask, or web-backend overhead.
* **Three Core Monitoring Modes:**
  * 🧑 **Person Detection:** Monitor and track unique pedestrian footprints using robust Centroid Tracking.
  * 🚲 **Bike Violations:** specifically filter and track illegal 2-wheelers traversing pedestrian/restricted paths.
  * 🚗 **Traffic Flow:** Analyze and count moving instances of 2-Wheelers and 4-Wheelers.
* **High-Fidelity AI Feeds:** We solved the traditional "blurred scaling" issue by ensuring the AI outputs (`predict()`) map dynamically onto the native resolution screen captures (`mss()`), interpolating down cleanly via `cv2.INTER_AREA`.
* **Automated & Manual CSV Reporting:** 
  * The system polls your clock to automatically dump a daily traffic CSV log asynchronously at exactly `00:00:00` (Midnight).
  * Includes a simple one-click manual CSV export button straight in the dashboard GUI.
* **Standalone Executable Compilation:** Pre-configured for deployment with **PyInstaller**. Converts the entire OpenCV Python environment and ONNX models into a portable, single-file `.exe`.

## 🛠️ Project Structure

* `gui.py` - The overarching Tkinter Graphical Interface running the async `root.after()` event loop.
* `main.py` - The legacy CLI-based OpenCV interface. 
* `onnx_yolo.py` - Contains the rigorous preprocessing and ONNX Non-Maximum Suppression (NMS) mechanics to bridge YOLO to Python tracking safely.
* `tracker.py` - A sophisticated Euclidean distance-based object `CentroidTracker` that maps detections over sequential frames.
* `/modules` - The AI handler scripts (`bike.py`, `person.py`, `traffic.py`).
* `/models` - The directory housing `.onnx` logic weights (e.g. `yolo11n.onnx`).
* `/reports` - Directory where daily `.csv` tracking exports are saved.

## 💾 Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/Intelligent-surveillance-system.git
   cd Intelligent-surveillance-system
   ```

2. **Install core dependencies:**
   ```bash
   pip install opencv-python onnxruntime numpy mss pillow
   ```

3. **Run the Application:**
   ```bash
   python gui.py
   ```

## 📦 Building the Standalone `.EXE`

To package the tool into a completely standalone Windows Executable (requiring absolutely zero Python setup for end-users), leverage PyInstaller:

```bash
pip install pyinstaller
pyinstaller --onefile --windowed --add-data "models;models" gui.py
```

Your fully featured `gui.exe` application will appear inside the `/dist` directory. 

## 👨‍💻 Developed By

Designed and developed by **Siddharth | eZpedal**.
