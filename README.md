# Transformations_Robotics
Converting a RGBD image into Point Cloud and applying Transformations to convert it into Global Frame.

### Using Open3d to Convert RGBD images recieved from SUN RGB-D dataset (S.Song, CVPR 2015 (https://rgbd.cs.princeton.edu/)) into Point Cloud Data in .pcd format

- Read two images color.jpg and depth.png given in current folder using Open3D. 
- Converted it into a point cloud using the default camera parameters
( o3d.camera.PinholeCameraIntrinsicParameters.PrimeSenseDefault ). 
- Created a "world" frame and combine this (just use operator) with the above point cloud and save it as scene.pcd . 
- Wrote function one_one to visualize scene.pcd

### Rotations, Euler angles and Gimbal Lock

- Generated a cube at some point on the ground and create another frame at the center of this object.
- Combined these both as a single point cloud cube.pcd . (You can pick a point on the ground by using the get_picked_points method of the class open3d.visualization.VisualizerWithEditing .)
Now read both the point clouds scene.pcd and cube.pcd in a script. 
- All tasks are on the object cube.pcd (along with the axes ) with scene.pcd in the background (static).
- Given a sequence of ZYX Euler angles, generated the rotation. 
- In our case, our object (with its respective axis) undergoes rotation with the background being fixed (with its respective axis).
Note: Throughout this assignment, we will be using the standard ZYX Euler angle convention.
Wrote a function two_one to show the above by animation (cube rotating along each axis one by one)
