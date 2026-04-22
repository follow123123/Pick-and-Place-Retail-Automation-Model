To run inference with the detection model a pi camera for red cubes with only required args, issue:

```
# In CLI
python yolo_detect_module.py --target red --model v1.pt --source picamera0

# In other program
from yolo_detect_module.py import detect_objects

detect_objects(
  target="red"
  model_path="{path}/v1.pt",
  img_source="picamera0"
)
```
### How does it return
*Currently it returns target name (e.g. "red cube") and count at the end of the whole function. You need to manually press q to end to get the results.

Here are all the arguments for yolo_detect.py or yolo_segment.py:

- `--model`: Path to a model file (e.g. `my_model.pt`).
- `--source`: Source to run inference on. The options are:
    - Image file (example: `test.jpg`)
    - Folder of images (example: `my_images/test`)
    - Video file (example: `testvid.mp4`)
    - Index of a connected USB camera (example: `usb0`)
    - Index of a connected Picamera module for Raspberry Pi (example: `picamera0`)
- `--thresh` (optional): Minimum confidence threshold for displaying detected objects. Default value is 0.5 (example: `0.4`)
- `--resolution` (optional): Resolution in WxH to display inference results at. If not specified, the program will match the source resolution. (example: `1280x720`)
- `--record` (optional): Record a video of the results and save it as `demo1.avi`. (If using this option, the `--resolution` argument must also be specified.)

### Deploy on Raspberry Pi
Remember to pip install picamera2
[How to Run YOLO Detection Models on the Raspberry Pi](https://www.ejtech.io/learn/yolo-on-raspberry-pi)
