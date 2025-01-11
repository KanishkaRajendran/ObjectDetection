# Object Detection with YOLOv8

This repository contains a Python implementation for detecting objects and their sub-objects in video frames using the YOLOv8 model. The script processes a video file, detects objects, and generates an output video with bounding boxes and an accompanying JSON file containing detailed detection data.

## Features

- Object detection using the YOLOv8 model.
- Identification of sub-objects for specified object classes (e.g., `person` and `car`).
- Outputs:
  - Annotated video with bounding boxes for detected objects and sub-objects.
  - JSON file containing metadata for all detected objects.

## Requirements

To run this project, you need the following dependencies:

- Python 3.7 or higher
- OpenCV
- NumPy
- Ultralytics YOLOv8
- Google Colab (optional for running the provided notebook)

Install the dependencies using the following command:

```bash
pip install ultralytics opencv-python-headless numpy
```

## File Descriptions

- `main.py`: The main Python script for processing the video.
- `output.json`: The JSON file containing metadata for all detected objects.
- `output_video.mp4`: The annotated video with bounding boxes.
- `drive_link.txt`: A file containing a shared Google Drive link to access additional resources.

## Usage

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/object-detection-yolov8.git
cd object-detection-yolov8
```

### 2. Run the Script

Provide the path to your input video file and specify the output JSON and video file paths. Example usage:

```bash
python main.py
```

Ensure the following variables are updated in the `main.py` file:

```python
video_path = "path/to/your/input/video.mp4"
output_json_path = "output.json"
output_video_path = "output_video.mp4"
```

### 3. Use Google Colab (Optional)

To run this code in Google Colab, use the provided notebook link:

[Google Colab Notebook](https://colab.research.google.com/drive/1AeZf-GE1jzEYOv6pLNu_CYXGOOjDN4Uc?usp=sharing)

You can directly click the link above to open the notebook and try out the code.

Upload your video file to Colab and execute the notebook cells to process the video.

### 4. Additional Resources

A Google Drive folder containing relevant resources can be accessed using the link in the `Demo_Video.md` file included in this repository.

## How It Works

1. **Object Detection**:
   - The YOLOv8 model detects objects in each frame of the input video.
   - For specific classes (`person` and `car`), the script performs sub-object detection within the bounding box of the parent object.

2. **Annotated Output**:
   - Bounding boxes and labels are drawn on the video frames for objects and sub-objects.
   - The annotated frames are compiled into an output video.

3. **JSON Metadata**:
   - Metadata for each detected object is saved in a JSON file, including:
     - Object class
     - Unique object ID
     - Bounding box coordinates
     - Sub-object information (if applicable)

## Example Output

- **JSON File:**

```json
[
    {
        "object": "person",
        "id": 1,
        "bbox": [50, 100, 200, 400],
        "subobject": [
            {
                "object": "bag",
                "id": 2,
                "bbox": [60, 150, 180, 300]
            }
        ]
    }
]
```

- **Annotated Video:**
  The output video includes bounding boxes and labels for detected objects and sub-objects.

## Customization

- **Change Classes for Sub-Object Detection:**
  Modify the `if` condition in the `detect_objects` function to add or remove classes for sub-object detection:

  ```python
  if class_name == "person" or class_name == "car":
  ```

- **Model Configuration:**
  Replace the YOLOv8 model with a different version (e.g., `yolov8s.pt`) by updating the following line:

  ```python
  model = YOLO('yolov8n.pt')
  ```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments

- [Ultralytics](https://ultralytics.com/) for the YOLOv8 model.
- OpenCV for video processing.
- Google Colab for enabling easy experimentation and deployment.

---
