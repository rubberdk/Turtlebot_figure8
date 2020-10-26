## Written By DK Kang


### Setup Instruction: ROS set-up
 -- It requires Turtlebot3 and ROS noetic
1. sudo apt-get update
2. sudo apt-get upgrade
3. install `ROS-noetic` from following website: http://wiki.ros.org/noetic/Installation/Ubuntu
4. install `python3`rosdep
	```
	sudo apt install python3-rosdep
	sudo rosdep init
	rosdep update
	```
5. install some dependencies `sudo apt install python3-vcstool git gitk python3-pip catkin-lint`
6. go to yout home dir `cd ~'
7. Create workspace: `mkdir ws` and `cd ws`
8. `mkdir src` and `cd src`
9. get files: `git clone https://github.com/ME495-EmbeddedSystems/homework02-rubberdk.git`
10. For detailed setup, please refer to following website: https://emanual.robotis.com/docs/en/platform/turtlebot3/setup/
10. Connect to your Turtlebot3
11. `ping turtlebot.local` to make sure you are connected
#Figure 8 Trajectory using ROSpy
## Figure 8 Trajectory
### node: `trajectory`
All nodes are located in the `nodes` file

`trajectory` publlishes:
1) `cmd_vel (geometry_msgs/Twist)` for `Turtlebot 3`
2) `path (nav_msgs/Path)` for trajectory display in `rviz`
3) `point (geometry_msgs/Point)` for `rqt_plot`

`trajectory` broacasts:
 A static transform from `world` to `odom`. The `world` frame and `odom` frame are co-located

`trajectory` gets Parameters from `trajectory.yaml` in `config`
 Parameters are:
1) `W`: The width of the figure eight
2) `H`: The height of the figure eight
3) `T`: The amount of time it takes to complete the figure eight
4) `pub_freq`: The frequency at which to publish the messages. This is a private parameter.

 This is how velcoties for `cmd_vel` are calculated:
 refer to the `Velocity_Calc.pdf` for a full document.
![alt text](https://github.com/ME495-EmbeddedSystems/homework02-rubberdk/blob/master/cal1.png)
![alt text](https://github.com/ME495-EmbeddedSystems/homework02-rubberdk/blob/master/cal2.png)
![alt text](https://github.com/ME495-EmbeddedSystems/homework02-rubberdk/blob/master/cal3.png)
### Launch
1) `cd` into `launch` file:
2) `roslaunch` the `firgure_eight` by:
		`roslaunch figure_eight.launch`



Turtlebot3:Burger 
[![](http://img.youtube.com/vi/LmW4-nmALRc/0.jpg)](http://www.youtube.com/watch?v=LmW4-nmALRc "")


=


