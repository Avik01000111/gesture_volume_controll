# 🔊 Hand Gesture Volume Control using MediaPipe & Pycaw

This real-time Python project lets you **control system volume** using **hand gestures** detected via a webcam. It uses **MediaPipe Hands** to detect landmarks and adjusts volume based on the distance between the **thumb and index finger**.

---

## ✨ Features

* Real-time volume control via hand gestures 🖐️
* Uses webcam input and MediaPipe hand tracking.
* Calculates distance between thumb and index finger.
* Maps hand distance to system volume range (0% - 100%).
* Displays a visual volume bar on screen.

---

## 🧰 Requirements

Install the required libraries:

```bash
pip install opencv-python mediapipe numpy pycaw comtypes
```

> 🔔 **Windows only**: `pycaw` is used to control system volume and works on **Windows OS** only.

---

## 🎥 How It Works

1. **Hand Detection**: Uses MediaPipe to detect and track hand landmarks in real-time.
2. **Gesture Measurement**: Measures the distance between the tip of the thumb (`id 4`) and the index finger (`id 8`).
3. **Volume Mapping**:

   * Minimum distance (\~50px) → Volume = 0%
   * Maximum distance (\~220px) → Volume = 100%
4. **System Volume Adjustment**: Volume is set using `pycaw` Windows Audio API.

---

## 📐 Landmarks Used

| Finger    | Landmark ID |
| --------- | ----------- |
| Thumb Tip | `4`         |
| Index Tip | `8`         |

---

## 📁 Project Structure

```
📂 your_project_folder/
├── 📄 volume_control.py         # Main Python script
```

---

## 🖼️ Output UI

* Green line between thumb and index = Measuring
* Red line = Minimum volume detected
* Vertical bar = Real-time volume level
* Text = Volume % displayed on screen

---

## ▶️ How to Run

```bash
python volume_control.py
```

* Move thumb and index finger closer → Volume ↓
* Move them apart → Volume ↑
* Press **`q`** to quit

---

## 💡 Use Cases & Extensions

* Contactless volume control for presentations or music systems.
* Extend to control **brightness**, **media playback**, or **mouse**.
* Add audio feedback or gestures for **mute**, **pause**, or **skip**.

---

## ❗ Notes

* Tested and works only on **Windows** (due to Pycaw).
* Webcam access is required.
* MediaPipe provides fast and accurate hand tracking but may vary with lighting.

---

## 📝 License

This project is open-source under the **MIT License**.

---

## 🙌 Acknowledgements

* [MediaPipe by Google](https://mediapipe.dev/)
* [Pycaw - Python Core Audio Windows Library](https://github.com/AndreMiras/pycaw)
* [OpenCV](https://opencv.org/)

