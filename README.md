
# Cricket Ball Detection & Tracking System

A computer vision pipeline for detecting and tracking a cricket ball from a single fixed-camera feed. The system uses **YOLOv8** for object detection and a **Kalman Filter** for robust tracking and occlusion handling.

## 🚀 Features
- **Detection:** Accurate ball localization using custom-trained YOLOv8.
- **Tracking:** Kalman Filter integration to handle motion blur and temporary occlusions.
- **Output:**
  - Processed video with **Green Dot** overlay on the ball.
  - CSV file (`annotations.csv`) containing frame-by-frame coordinates (`x, y`) and visibility flags.

## 🛠️ Setup & Usage
1. **Clone Repository:**

git clone https://github.com/yourusername/cricket-ball-tracking.git
cd cricket-ball-tracking


2. **Install Dependencies:**
   pip install ultralytics opencv-python-headless pandas numpy


3. **Run Inference:**
- Place your input video as `video.mp4` and model weights as `best.pt`.
- Run the script:
  ```
  python main.py
  ```

## 📂 Repository Structure
- `code/` - Main inference and tracking scripts.
- `annotations/` - Generated CSV output files.
- `results/` - Processed videos with overlays.


## 📊 Approach
- **Model:** YOLOv8 (Fine-tuned on cricket datasets).
- **Logic:** Detections feed into a Kalman Filter. If detection is lost, the filter predicts position for up to 5 frames before terminating the track.

