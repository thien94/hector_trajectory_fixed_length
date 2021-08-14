# hector_trajectory_fixed_length 

## Description 
Based on [`hector_trajectory_server`](http://wiki.ros.org/hector_trajectory_server).

- `hector_trajectory_server` is a node that saves trajectory data and makes it available using the ROS API.
- `hector_trajectory_fixed_length` works similarly, but only keeps a fixed number of latest poses in the memory (sliding window style).

## Example launch file

```
<?xml version="1.0"?>
<launch>
    <node pkg="hector_trajectory_fixed_length" type="hector_trajectory_fixed_length" name="est_path" output="screen" ns="estimator" >
        <param name="/target_frame_name" value="/world" />
        <param name="/source_frame_name" value="/imu" />
        <param name="/trajectory_update_rate" value="20.0" />
        <param name="/trajectory_publish_rate" value="20.0" />
        <param name="/max_trajectory_length" value="100" />
    </node>
</launch>
```