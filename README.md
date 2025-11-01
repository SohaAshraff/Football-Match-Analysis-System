# Football Match Analysis - CV System

Advanced computer vision pipeline for automated football match analysis with player detection, team classification, and persistent jersey number recognition.

---

## 🎯 Features

- **Multi-Object Detection**: Players, goalkeepers, referees, and ball
- **Team Classification**: Automated color-based differentiation
- **Jersey Number Recognition**: Advanced OCR with 4 preprocessing methods
- **Persistent Tracking**: Maintains numbers during occlusions (~5 sec)
- **Professional Visualization**: Color-coded annotations with legend

---

## 🛠️ Tech Stack

Python • OpenCV • EasyOCR • PyTorch • Roboflow • ByteTrack 

---

**Set API Key:**
```bash
export ROBOFLOW_API_KEY='your_api_key_here'
```

---

## 🚀 Usage

### Google Colab
1. Upload video file
2. Set Roboflow API key in secrets (🔑 icon)
3. Run all cells
4. Download output video

### Key Parameters
```python
SOURCE_VIDEO_PATH = "input.mp4"
TARGET_VIDEO_PATH = "output.mp4"
MIN_DETECTIONS_TO_LOCK = 3        # Lock after 3 detections
FRAMES_TO_KEEP_INVISIBLE = 150    # ~5 sec persistence
```

---

## 🔬 How It Works

1. **Detection**: Roboflow model detects players/ball (confidence > 0.3)
2. **Tracking**: ByteTrack maintains consistent player IDs
3. **Classification**: Color-based team clustering
4. **OCR**: Multi-method preprocessing → EasyOCR → Validation
5. **Persistence**: Confidence-based locking keeps numbers visible
6. **Visualization**: Annotate + Legend → Output video

---



## ⚙️ Configuration
```python
# Detection
CONFIDENCE_THRESHOLD = 0.3
NMS_THRESHOLD = 0.5

# Jersey Tracking
MIN_DETECTIONS_TO_LOCK = 3
CONFIDENCE_LOCK_THRESHOLD = 0.5
FRAMES_TO_KEEP_INVISIBLE = 150
CONFIDENCE_DECAY_RATE = 0.98
```

---

## 📁 Structure
```
├── notebook/
│   └── Football_Analysis.ipynb
├── output/
│   └── sample_output.mp4
└── README.md
```

---

## ⚠️ Limitations

- Video quality dependent
- Best with clear, contrasting jersey numbers
- Heavy occlusions may temporarily lose tracking
- CPU processing is slower (~5 FPS)

---

## 🚀 Future Improvements

- [ ] Real-time optimization
- [ ] Player statistics (speed, distance)
- [ ] Action recognition (goals, passes)



---
