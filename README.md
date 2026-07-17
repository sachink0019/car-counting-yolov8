# 🚗 Car Counting using YOLOv8, SORT & OpenCV

A computer vision project that detects, tracks, and counts vehicles crossing a defined line in a video, using **YOLOv8** for object detection, **SORT** for multi-object tracking, and **OpenCV** for video processing and visualization.

![Demo](demo.gif)
<!-- Replace demo.gif with your actual demo file path, or embed a GIF/video link here -->

## 📌 Overview

This project processes a pre-recorded traffic video and counts the total number of cars that cross a user-defined line, giving a simple but effective way to measure traffic flow without manual counting. Each car is assigned a persistent tracking ID via SORT, ensuring it's counted only once even as it's re-detected across multiple frames.

## 🛠️ Tech Stack

- **YOLOv8** — real-time object detection to identify vehicles in each frame
- **SORT (Simple Online and Realtime Tracking)** — assigns consistent IDs to detected vehicles across frames, preventing duplicate counts
- **OpenCV** — video I/O, frame processing, drawing the counting line and bounding boxes
- **Python**

## ⚙️ How It Works

1. Load the input video frame-by-frame using OpenCV.
2. Run YOLOv8 inference on each frame to detect vehicles.
3. Pass detections to SORT, which tracks each vehicle across frames and assigns it a unique, persistent ID.
4. Draw bounding boxes and tracking IDs around detected cars.
5. Check if a tracked car's centroid crosses a predefined counting line.
6. Increment and display the running count on the video output — each unique ID is counted only once.

## 📂 Project Structure

```
car-counting-yolov8/
├── main.py                # Entry point — runs detection + counting
├── requirements.txt        # Python dependencies
├── models/                 # YOLOv8 weights
├── videos/                 # Sample input video(s)
├── output/                 # Processed output video(s)
└── README.md
```

## 🚀 Installation

```bash
git clone https://github.com/<your-username>/car-counting-yolov8.git
cd car-counting-yolov8
pip install -r requirements.txt
```

## ▶️ Usage

```bash
python main.py --video videos/sample.mp4 --output output/result.mp4
```

## 📊 Results

- Successfully detects and counts cars crossing the line in a sample traffic video.
- Demo video/GIF included above showing detection + live count overlay.

<!-- Add specific numbers here if you have them, e.g.:
- Achieved ~X FPS on [hardware]
- Counted X cars accurately in a Y-minute test video
-->

## 🔮 Future Improvements

- Add direction-wise counting (in/out)
- Multi-lane counting
- Speed estimation
- Real-time webcam/CCTV feed support

## 🙌 Acknowledgements

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- OpenCV

---

⭐ If you found this project useful, consider giving it a star!
