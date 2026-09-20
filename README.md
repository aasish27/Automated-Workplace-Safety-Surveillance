# Automated Workplace Safety Surveillance

Automated Workplace Safety Surveillance is a computer vision project that detects missing Personal Protective Equipment (PPE) in real time and provides voice alerts when a safety violation is detected.

The system can work with both live webcam input and recorded video, making it useful for basic workplace safety monitoring.

## Key Features

* Real-time detection of PPE such as hardhats, masks, and safety vests
* Voice alerts when required PPE is missing
* GPU acceleration when available
* Support for webcam and video file input
* 5-second cooldown between repeated voice alerts
* YOLOv8-based object detection

## Technologies Used

* Python
* YOLOv8
* OpenCV
* pyttsx3
* Python Threading

## Project Structure

```text
├── Dataset for AWSS/          # Dataset used for training/testing
├── Programs/                  # Main program files
│   ├── PPE_DETECTION_PRO.py   # PPE detection and alert system
│   └── alert_systems.py       # Voice alert implementation
├── Video/                     # Input video files
├── Sample Output.mp4          # Sample detection output
├── ppe_model.pt               # Trained YOLO model
└── README.md
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/automated-workplace-safety-surveillance.git
cd automated-workplace-safety-surveillance
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

For Windows:

```bash
venv\Scripts\activate
```

For macOS/Linux:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the Model

Make sure `ppe_model.pt` is available in the root directory of the project.

## Usage

### Webcam

Run the main detection program:

```bash
python Programs/PPE_DETECTION_PRO.py
```

The system will start processing the webcam feed and display the detected PPE.

### Video File

To process a recorded video, update the video path in:

```python
cv2.VideoCapture()
```

with the location of the video file.

Press `q` to stop the program.

## How It Works

1. The system captures frames from a webcam or video file.
2. YOLOv8 processes each frame to identify PPE.
3. The detected objects are displayed on the video.
4. The system checks whether the required PPE is present.
5. If required PPE is missing, a voice alert is generated.
6. A 5-second cooldown prevents the same alert from being triggered continuously.

## Sample Output

The repository includes a sample output video demonstrating the PPE detection system.

https://github.com/user-attachments/assets/c5db4638-6a82-44bc-a846-7bf7187ca8fc

## Customization

### Change Alert Frequency

The alert interval can be modified in:

```text
Programs/alert_systems.py
```

### Add or Modify PPE Classes

The PPE classes can be updated through the `classNames` list in:

```text
Programs/PPE_DETECTION_PRO.py
```

## Testing

The system can be tested using different webcam and video inputs to verify:

* PPE detection accuracy
* Missing PPE detection
* Voice alert generation
* Alert cooldown behavior
* Performance with different lighting and camera conditions

## Future Improvements

* Add more PPE categories
* Improve detection under different lighting conditions
* Add detection logs and reports
* Add an IoT-based alert system
* Develop a web dashboard for monitoring safety violations

## Author

**Aasish M**

AI & ML Developer | AI & DS Student
