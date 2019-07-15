# Navigation
The model uses URDF model for Gazebo, integrated with ROS

The model has all the inputs required buy the [ROS navigation stack](http://wiki.ros.org/navigation/Tutorials/RobotSetup) 

This includes 

### Sensor transformations 
at ```/tf```

### Odometry source  
at ```/odom```

### Laser scan  
The bot is also equiped with a [laser based on Hokuyo Top-URG](http://wiki.ros.org/hokuyo_node).
The laser data can be viewed in rviz

at the topic ```/mybot/laser/scan```

as required by sensor sources  

### Point Cloud 
It has a sterio pair of simple RGB cameras publishing to 
```/mybot/camera1/image_raw``` and 
```/mybot/camera2/image_raw```
rostopics respectively 

The camera images can be visualized using 
```$ rosrun image_view image_view image:=/mybot/camera1/image_raw```
```$ rosrun image_view image_view image:=/mybot/camera2/image_raw```

The camera images will be used to create a point cloud as required by the sensor sources 

### Command velocity messages 
being listened to at ```/cmd_vel```
which control where the robot is going in the simulation 

The robot can be moved in the simulation using 
```
$ rostopic pub /cmd_vel geometry_msgs/Twist "linear:
  x: 0.0
  y: 0.0
  z: 0.0
angular:
  x: 0.0
  y: 0.0
  z: 0.0"
```
specifying the angular and transational values 



