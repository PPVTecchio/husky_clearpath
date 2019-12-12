# Working with Clearpath Husky simulations

## Using joystick teleop commands on Husky

> roslaunch husky_clearpath run_teleop.launch

### Using XBOX ONE Wireless Controller

Follow the driver installation guide provided on https://github.com/atar-axis/xpadneo by Florian Dollinger to install Ubuntu support to this joystick. It will create the necessary file /dev/input/js* so you can use the provided launch files. I followed the steps provided on Connection to connect my joystick for the first time, but later on, every time I turned the controller on, Ubuntu would automatically connect to it.

## Understanding existing launch files necessary for Go2Goal

I created a launch file that calls necessary launch files from Clearpath Robotics tutorials to execute the Go2Goal service by using the respective button on RViz. After that, I started to dissect the launch files, to understand what they were calling and some of the parameters and arguments necessary to its use. Then, I read a bit about AMCL method from the original paper and other websites.

The big but for me so far is that on the paper AMCL does not seem to need an initial location for it to initialize the localization of the robot, as it should disperse probable points throughout the entire given map, BUT it doesn't seem to do that. When, we start it up, it assumes that the robot is at the origin and the dispersed pose beliefs are quite concentrated around this position. So, after I start the robot elsewhere, AMCL does not correctly localize the robot, and adjust its location around the map. I tried setting up larger covariances but it did not work as I wished.

This behavior seems strange to me. I will probably come back to this latter on.

I also looked at the other bring up files from Clearpath for the Husky robot, such as URDF configuration and the move_base node. But I was not that attentive to this.

In order to run our launch files just call one of the following:
> roslaunch husky_clearpath run_go2goal.launch

> roslaunch husky_clearpath run_go2goal_no_launches.launch

> roslaunch husky_clearpath run_go2goal_set_init_position.launch
