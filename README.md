### Running the demo with TB3
First, you'll need to launch the whole simulation stack, nav2 stacks and slam stacks per robot. For that just launch::
```
export TURTLEBOT3_MODEL=waffle
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:/opt/ros/${ROS_DISTRO}/share/turtlebot3_gazebo/models
ros2 launch multirobot_map_merge multi_tb3_simulation_launch.py slam_gmapping:=True
```
Now run the merging node:
```
ros2 launch multirobot_map_merge map_merge.launch.py
```

By default, the demo runs with known initial poses. You can change that by launching again both launch commands with the flag `known_init_poses:=False`

Then you can start moving each robot with its corresponding rviz2 interface by sending nav2 goals. To see the map merged just launch rviz2:
```
rviz2 -d <your/ros2_ws>/src/m-explore-ros2/map_merge/launch/map_merge.rviz
```

**Note**: If you want to use slam_toolbox, launch `multirobot_map_merge` with the following flag instead: `slam_toolbox:=True`. Remember to use the experimental branch mentioned above.
#adding other more Bots
