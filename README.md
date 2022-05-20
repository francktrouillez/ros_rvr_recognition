ros_rvr_recognition
=========

Package for Sphero RVR robot recognition using a 4-cameras vision module.


### Features

 * Sphero RVR robot recognition using color segmentation
 
 * Sphero RVR robot recognition using [ArUco][1] markers

 * Sphero RVR robot recognition using a neural network [EfficientDet0][2]
 
### ROS API

#### Messages

 * rvr_recognition/PointArray.msg

        Header header
        geometry_msgs/Point[] points


### Usage

 * Start the vision module with the 4 cameras.
    ```
    roslaunch rvr_recognition vision_module_cameras.launch
    ```

 * Start the recognition using one of the methods implemented, where you need to choose between the three.
    ```
    roslaunch rvr_recognition rvr_recognition_{aruco, color, nn}.launch
    ```

 * The result of the detection is published on the `rvr_localisation` topic.
    ```
    rostopic echo /rvr_localisation
    ```
 * The result can also be visualized by launching nodes that publish images to a topic representing the detection around the robot.
    ```
    roslaunch rvr_recognition rvr_recognition_view.launch
    ```


[1]: http://www.sciencedirect.com/science/article/pii/S0031320314000235 "Automatic generation and detection of highly reliable fiducial markers under occlusion by S. Garrido-Jurado and R. Muñoz-Salinas and F.J. Madrid-Cuevas and M.J. Marín-Jiménez 2014"
[2]: https://arxiv.org/abs/1911.09070 "EfficientDet: Scalable and Efficient Object Detection by M. Tan, R. Ruoming and Q.V. Le 2019"
