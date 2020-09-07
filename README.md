# jetson-nx-navbot

## ROSLAUNCH COMMANDS
catkin_make -DCMAKE_BUILD_TYPE=Release


roslaunch orb_slam2_ros orb_slam2_d435_rgbd.launch /orb_slam2_rgbd/load_map:=True /orb_slam2_rgbd/map_file:=/media/ghost/workspace/map.bin
roslaunch orb_slam2_ros orb_slam2_d435_rgbd.launch orb_slam2_rgbd/load_map:=True orb_slam2_rgbd/map_file:=/media/ghost/workspace/map.bin

-------------- Main Commands ---------------
roslaunch orb_slam2_ros orb_slam2_d435_rgbd_xavier.launch


roslaunch realsense2_camera rs_rgbd.launch
roslaunch realsense2_camera rs_rgbd.launch stereo_fps:=15 color_fps:=15


roslaunch darknet_ros_3d darknet_ros_intel3d.launch
roslaunch bbox3d bbox3d.launch
--------------------------------------------


rostopic hz /camera/depth_registered/points /orb_slam2_rgbd/pose

Topics:
  /orb_slam2_rgbd/map_points
  /projected_map
  /camera/depth_registered/points
  /orb_slam2_rgbd/pose

roslaunch octomap_server octomap_mapping.launch

roslaunch octomap_server octomap_mapping.launch cloud_in:=/camera/depth_registered/points frame_id:=/mapturtlebot


rosservice call /orb_slam2_rgbd/save_map /media/ghost/workspace/map.bin
