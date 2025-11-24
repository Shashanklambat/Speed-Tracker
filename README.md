🚗 Object Speed Tracking Using Computer Vision (OpenCV)

A Python-based computer vision tool that can track an object in a video and calculate its real-time speed based on the movement of the object across frames.

📌 Overview

This project allows you to:

Upload any video

Select a real-world reference line (in meters)

Select an object to track

Let the program track the object frame by frame

Automatically calculate:

Distance traveled

Speed (m/s)

Time progression

Export results to a CSV file

This system uses OpenCV CSRT Tracker, manual scaling via reference line, and pixel-to-meter conversion.

🎥 Features

✔ Track object motion in real-time
✔ Calculates speed using frame-to-frame displacement
✔ Lets user rotate video if required
✔ Interactive reference line selection
✔ Interactive ROI selection
✔ Auto CSV export of speed vs time
✔ Works on any video where object moves straight & perpendicular to camera

🛠️ Technologies Used

Python 3

OpenCV

NumPy

CSV Writer

Argparse

📂 Project Workflow

Load video input

Rotate video if needed

Select a reference line of known length (default 2 meters)

Select the object ROI to track

CSRT tracker follows object frame-by-frame

For each frame:

Find center point

Measure pixel movement

Convert to meters using scale

Compute speed = distance / frame_time

Save results to CSV

🧮 How Speed Is Calculated

The program tracks the center of the object in every frame

Calculates pixel displacement

Converts pixels → meters using reference line

Divides by frame duration to get speed

Formula:

speed (m/s) = distance_moved / frame_time

📦 Installation
1. Clone the Repository
git clone https://github.com/your-username/your-repo.git
cd your-repo

2. Install Dependencies
pip install opencv-python numpy

▶️ Usage
Basic Command
python speed_tracker.py input_video.mp4 output_name 0.02

Arguments
Argument	Description
video_in	Input video file path
csv_out	Output CSV file base name
f	Duration of a single frame in seconds
-r	(Optional) Rotate video (0°, 90°, 180°, 270°)
-l	(Optional) Reference line length in meters (default = 2m)
🎮 Controls
During scale selection

Left Click + Drag: Draw reference line

SPACE: Confirm selection

ESC: Exit program

During tracking

SPACE: Pause

S: Save CSV

R: Reset tracked points

ESC: Quit

📁 CSV Output Format
time (s)	speed (m/s)	distance (m)

Data is saved with auto versioning:

speed_export0.csv
speed_export1.csv
...

📌 Limitations

Object must move in a straight line

Camera must be fixed

Speed accuracy depends on correct reference line selection

🚀 Future Improvements

Support for multiple object tracking

Automatic scale detection

Speed visualization graphs

Integration with YOLO for object detection
