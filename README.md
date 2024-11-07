# jaka dev ros2 humble
For example jaka_zu7
- [x] jaka_robot_v2.2/src/jaka_description only jaka_zu7
- [x] jaka_robot_v2.2/src/jaka_msgs
- [x] jaka_robot_v2.2/src/jaka_driver
- [x] jaka_robot_v2.2/src/jaka_zu7_moveit_config
- [ ] jaka_robot_v2.2/src/jaka_planner
## run (win robostack)
```
mamba install ros-humble-moveit ros-humble-joint-state-publisher-gui ros-humble-moveit-planners-chomp

colcon build --merge-install --cmake-args  -DCMAKE_BUILD_TYPE=Release  --event-handlers console_direct+
call install/setup.bat
ros2 launch jaka_description jaka_zu7_rviz_control.launch.py
```

```shell
ros2 launch jaka_driver robot_start_launch.launch.py ip:=192.168.56.101
ros2 service list
ros2 service type /jaka_driver/joint_move

ros2 service call /jaka_driver/joint_move jaka_msgs/srv/Move "{pose: [0,1.57,-1.57,1.57,1.57,0], has_ref: false, ref_joint: [0], mvvelo: 0.5, mvacc: 0.5, mvtime: 0.0, mvradii: 0.0, coord_mode: 0, index: 0}"

ros2 service call /jaka_driver/linear_move jaka_msgs/srv/Move "{pose: [111.126,282.111,271.55,3.142,0,-0.698], has_ref: false, ref_joint: [0], mvvelo: 100, mvacc: 100, mvtime: 0.0, mvradii: 0.0, coord_mode: 0, index: 0}"

ros2 service call /jaka_driver/get_fk jaka_msgs/srv/GetFK "{joint: [0,1.57,-1.57,1.57,1.57,0]}"

ros2 service call /jaka_driver/get_ik jaka_msgs/srv/GetIK "{ref_joint: [0,1.57,-1.57,1.57,1.57,0], cartesian_pose: [130.7,116,291,3.13,0,-1.5707]}"
```
## SDK 2.1.14


# jaka_robot
* Latest package: jaka_robot_v2.2 (Includes documents and source code)  
* Remember to compile the first time you use it.
* ROS1 support only
