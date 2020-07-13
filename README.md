# OpenCV CCTV

A small software to create CCTV for single camera. Completely created on __Python 3.6__, can detect faces, people and movements, stream video. Recorded videos have an info plate on top of the screen, which you can change from the configuration variable. The system can recognize movement and record the moving object as it moves, or it can record video continuously.  The code also supports custom hooks. The software was tested on Raspberry Pi

##### How to isntall

Copy the repository to your Linux system. 

```
git clone https://github.com/iRTEX-Creative/OpenCV-Webcam-Recorder-and-Streamer.git
```

Browse to the repository folder.

```
cd OpenCV-Webcam-Recorder-and-Streamer
```

Install Python libraries

```
pip3 install cv2
pip3 install numpy
```

Start ```main.py```

```
python3 main.py
```

### Hooks
The system sends signals at every activity by hooking. You can hang your functions on these hooks.

```
def execute (e=None):
    # The body of your function
    pass

Hooks.set('Hook', lambda E: execute(E))
```

#### Table of hooks

| Hook | Arg | Description|
| ------ | ------ |  ------ |
| on_face_detect | frame with face | Executing when the camera detect the face. |
| on_eye_detect | frame with eye | Executing when the camera detect the eye. |
| on_body_detect | frame with body | Executing when the camera detect the body. |
| on_body_upper_detect | frame with body | Executing when the camera detect the upper body. |
| on_body_lower_detect | frame with body | | Executing when the camera detect the lower. |
| on_start_webserver | None | Executing when web server is ready started. |
| on_wait_camera | number camera in for | Executing when system wait camera. To be inside the iteration of the cycle, not outside it. |
| on_init | True | Executing when system started. |
| on_release | None | Executing when OpenCV 'cap' and video record release. |
| on_frame_send_to_server | JPG frame | Executing when web server send frame. |
| on_motion_detect | frame | Executing when the camera detect movement. |
| on_save_video | frame | Executing when the system write frame in video. To be inside the iteration of the cycle, not outside it. |
| on_before_write_frame | frame | Executing when the frame is ready to be recorded, but not yet recorded. |
| on_setup_cfg | configuration object | Executing when configs ready to use. |
| on_exit | True | Executing when system exiting. |
---
![Git size](https://img.shields.io/github/languages/code-size/iRTEX-Creative/OpenCV-Webcam-Recorder-and-Streamer)
![GitHub All Releases](https://img.shields.io/github/downloads/iRTEX-Creative/OpenCV-Webcam-Recorder-and-Streamer/total)
