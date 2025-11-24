# 🚗 Object Speed Tracking Using Computer Vision (OpenCV)

A Python-based computer vision tool that tracks an object in a video and calculates its real-time speed based on frame-by-frame movement using OpenCV.

## 📌 Overview

This project allows you to:
- Upload any video  
- Select a real-world reference line (in meters)  
- Select an object to track  
- Automatically calculate:  
  - Distance traveled  
  - Speed (m/s)  
  - Time progression  
- Export results to a CSV file  

The system uses the OpenCV **CSRT Tracker**, manual scaling via a reference line, and pixel-to-meter conversion.

## 🎥 Features

- ✔ Real-time object tracking  
- ✔ Accurate speed calculation  
- ✔ Optional video rotation  
- ✔ Interactive reference line selection  
- ✔ Interactive ROI selection  
- ✔ Auto CSV export  
- ✔ Works with any video where the object moves straight and the camera is stable  

## 🛠️ Technologies Used

- Python 3  
- OpenCV  
- NumPy  
- CSV Writer  
- Argparse  

## 📂 Project Workflow

1. Load the video  
2. Rotate video if required  
3. Select a reference line of known length (default: **2m**)  
4. Select the object's ROI for tracking  
5. Track the object across frames using CSRT tracker  
6. For each frame:
   - Calculate the object's center  
   - Measure pixel displacement  
   - Convert pixels → meters  
   - Compute speed using frame duration  
7. Save the speed/time data to a CSV  

## 🧮 How Speed Is Calculated

The program measures frame-to-frame movement of the object.

### Formula:
speed (m/s) = distance_moved / frame_time


Where:  
- `distance_moved` = converted object displacement in meters  
- `frame_time` = time duration of one frame  

## 📦 Installation

### 1. Clone the Repository
git clone https://github.com/your-username/your-repo.git
cd your-repo

## Usage
Basic Command
python speed_tracker.py input_video.mp4 output_name 0.02

## Arguments
Argument	Description
video_in	Input video file path
csv_out	Output CSV file base name
f	Duration of a single frame in seconds
-r	(Optional) Rotate video (0°, 90°, 180°, 270°)
-l	(Optional) Reference line length in meters (default = 2m)
🎮 Controls
During Reference Line Selection

### Left Click + Drag → Draw reference line

### SPACE → Confirm

### ESC → Exit

### During Tracking

### SPACE → Pause

### S → Save CSV

### R → Reset tracking points

### ESC → Quit

## 📁 CSV Output Format
time (s)	speed (m/s)	distance (m)

Auto-created files are saved like:

speed_export0.csv
speed_export1.csv
...
