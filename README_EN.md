[[Japanese](https://github.com/Kazuhito00/Person-Detection-using-RaspberryPi-CPU)/English] 

# Person-Detection-using-RaspberryPi-CPU
This repository is person detection model and demo script assuming CPU operation of Raspberry Pi 4.<br>

https://user-images.githubusercontent.com/37477845/165421632-600f5f63-51e5-4afa-a0d5-3abc59d0d711.mp4

Using PINTO's [TensorflowLite-bin](https://github.com/PINTO0309/TensorflowLite-bin), it works in about 45-60ms when 4 threads are running. * About 75ms in 1 thread.<br>
It works on laptops, but if you need precision, we recommend an object discovery model other than this repository.<br>
Also, when using a laptop PC, "model.onnx" is often faster. *Approximately 10ms on Core i7-8750H

# Requirement 
opencv-python 4.5.3.56 or later<br>
tensorflow 2.8.0 or later *Recommended to use [TensorflowLite-bin](https://github.com/PINTO0309/TensorflowLite-bin)<br>
onnxruntime 1.9.0 or later *Only when using model.onnx

# Demo
Here's how to run the demo.
```bash
python demo.py
```
* --device<br>
Specifying the camera device number<br>
Default：0
* --movie<br>
Specify video file *When specified, priority is given to the camera device<br>
Default：unspecified
* --width<br>
Width at the time of camera capture<br>
Default：640
* --height<br>
Height at the time of camera capture<br>
Default：360
* --model<br>
Storage path of the model to load<br>
Default：model/model.tflite
* --score_th<br>
Detection threshold<br>
Default：0.4
* --nms_th<br>
NMS threshold<br>
Default：0.5
* --num_threads<br>
Number of threads used *Valid only when using TensorFlow-Lite<br>
Default：None

# Demo(ROS2)
This is a demo for ROS2.

Terminal 1
```bash
ros2 run v4l2_camera v4l2_camera_node
```

Terminal 2
```bash
python3 ./demo_ros2.py
```

# Application Example
* [Person Tracking(Person Detection + motpy)](https://github.com/Kazuhito00/MOT-Tracking-by-Detection-Pipeline)<br><img src="https://user-images.githubusercontent.com/37477845/169438828-20b2de08-fdbd-4a6f-a297-84a4104dd462.gif" loading="lazy" width="60%">

# Reference
* [PINTO0309/TensorflowLite-bin](https://github.com/PINTO0309/TensorflowLite-bin)

# Author
Kazuhito Takahashi(https://twitter.com/KzhtTkhs)
 
# License 
Person-Detection-using-RaspberryPi-CPU is under [Apache 2.0 License](LICENSE).

# License(Movie)
The sample video uses "[London, England, Regent Street](https://www2.nhk.or.jp/archives/creative/material/view.cgi?m=D0002160979_00000)" from the [NHK Creative Library](https://www.nhk.or.jp/archives/creative/).
