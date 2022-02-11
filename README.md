# Requirements
Make sure to install the `transforms3d` Python package by running
```bash
pip3 install transforms3d
```
Starting the ROS launch files without installing this package may result in an unexpected behavior.

# Launching the sim
After building and sourcing the code, run
```bash
ros2 launch turtle_tf2_py turtle_tf2_demo.launch.py
```
The turtle can be controlled by running the following node from another terminal
```bash
ros2 run turtlesim turtle_teleop_key
```

# Useful commands
## Using `view_frames`
TF2 diagrams can be viewed by running
```bash
ros2 run tf2_tools view_frames.py
```
This will generate a `view_frames.{pdf, gv}` files at the location of running the node.

## Using `tf2_echo`
`tf2_echo` reports the transform between any two frames broadcasted over ROS.
```bash
ros2 run tf2_ros tf2_echo source_frame target_frame
# Example
# ros2 run tf2_ros tf2_echo turtle1 turtle2
```
The result is the `target_frame` with respect to the `source_frame`, resolved in the `source_frame`.

## RViz and TF2
Starting rviz with the `*.rviz` configuration file
```bash
ros2 run rviz2 rviz2 -d $(ros2 pkg prefix --share turtle_tf2_py)/rviz/turtle_rviz.rviz
```

# References
- [Tutorial](https://docs.ros.org/en/foxy/Tutorials/Tf2/Introduction-To-Tf2.html)