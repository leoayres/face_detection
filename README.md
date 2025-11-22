

# 👤 Face Detection with OpenCV + face_recognition

A Python project for robust **face detection** using a combination of **OpenCV** for video/image handling and **face_recognition** for high-accuracy face localization.

---

## 🔧 Features

* Real-time face detection from webcam
* Face detection in image files or video files
* High-accuracy face localization via `face_recognition` (dlib-based)
* Bounding boxes drawn around detected faces
* Optional saving of processed frames (images or video)
* Works in headless environments or GUI-based setups
* Lightweight and easy to integrate as a module for larger computer vision systems

---

## 🚀 Getting Started

### Prerequisites

Install required Python libraries:

```bash
pip install opencv-python face_recognition
```

If working in a headless environment, you may use:

```bash
pip install opencv-python-headless face_recognition
```

**Note:** `face_recognition` depends on `dlib`, which may require system-level build tools (CMake, Boost, etc.) depending on your OS.

---

## ▶️ Usage

### **1. Detect faces via webcam**

```bash
python detect_faces.py --source webcam
```

This launches your webcam, detects all faces in real-time, and displays boxes around them.

---

### **2. Detect faces in an image**

```bash
python detect_faces.py --source path/to/image.jpg --output path/to/output.jpg
```

This detects faces in the image, draws bounding boxes, and saves the annotated image to `--output`.

---

### **3. Detect faces in a video file**

```bash
python detect_faces.py --source path/to/video.mp4 --output path/to/annotated_video.mp4
```

It processes the video frame-by-frame, detects faces, annotates each frame, and outputs a new video with face boxes.

---

## 🧩 How It Works

1. **Frame / Image Loading**
   The script reads images or video frames using OpenCV (`cv2.VideoCapture` or `cv2.imread`).

2. **Face Detection (face_recognition)**

   * Uses `face_recognition.face_locations()` to get face bounding boxes.
   * Can be configured with different model options (“hog” or “cnn”) for faster CPU or more accurate GPU detection.

3. **Drawing Bounding Boxes**

   * For each detected face, draws a rectangle around the face on the frame.
   * Optionally, you can add custom labels or drawing styles.

4. **Output / Display**

   * If `--output` is provided, annotated images or video are saved.
   * Otherwise, the script shows the annotated video in a window (if GUI available).

---


---

## 📈 Performance Tips

* Use `model="hog"` in `face_recognition.face_locations()` for CPU environments (faster detection).
* Use `model="cnn"` if you have GPU support (more accurate, slower on CPU).
* Process frames at a lower resolution to boost FPS.
* Use batch processing for video frames to reduce overhead.

---

## 🤝 Contributing

Contributions are very welcome!
Feel free to open issues or submit pull requests to improve functionality, add new features, or sharpen performance.

---

## 📜 License

This project is licensed under the **MIT License**.


