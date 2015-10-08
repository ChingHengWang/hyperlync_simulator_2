#Hyperlynch Mobile Robot Simulator 2.0

* key point : two measurement point sensor with prepared static map can achieve the basic localization in condition of no apparent odometry error such as long distance movement of andbot but no wheel contact the ground(no odometry information)
* key condition : no large movement of andbot with no contact between wheel and ground


#Situation
* simulation run gazebo and andbot and load the static map(my_map2.yaml) by mapserver, and andbot just use Hokuyo sensor like the single beam ,



##1
* urdf model
* Hokuyo sensor (Two measurement)

		Run *roslaunch hyperlync_robot hyperlync_simulator.launch* for the single beam

##2
* Static Map - run map server to provide /map topic to move_base node
* Navigation move_base
		Run *roslaunch hyperlync_robot move_base.launch*

##3
* amcl - no need for slam_gmapping (no need to mapping just localization)
		Run *roslaunch hyperlync_robot robot_mapping.launch*


##4
* Go on Rviz, click on *2D Nav Goal* and point and click on the Rviz map as goal for the robot
		Run rosrun rviz rviz -d /home/zach/catkin_ws/src/hyperlync_simulator/hyperlync_robot/andbot.rviz

