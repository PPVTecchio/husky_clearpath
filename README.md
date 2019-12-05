# Working with Clearpath Husky simulations

## Using joystick teleop commands on Husky

> roslaunch husky_clearpath run_teleop.launch

### Using XBOX ONE Wireless Controller

Follow the driver installation guide provided on https://github.com/atar-axis/xpadneo by Florian Dollinger to install Ubuntu support to this joystick. It will create the necessary file /dev/input/js* so you can use the provided launch files. I followed the steps provided on Connection to connect my joystick for the first time, but later on, every time I turned the controller on, Ubuntu would automatically connect to it.