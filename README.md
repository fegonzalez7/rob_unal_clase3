# Robotics - UNAL - LAB3

## Requirements
### Dynamixel wizard
To test the dynamixel motors there is no better way than the official robotis software. [Here](https://emanual.robotis.com/docs/en/software/dynamixel/dynamixel_wizard2/) you will find an extensive installation tutorial. Once it is installed should look like this:
![](https://i.postimg.cc/wMLrh23Y/Screenshot-from-2022-03-04-20-44-38.png) 

### Dynamixel_workbench package
The *dynamixel_workbench* is necessary to control the dynamixel interface in ROS. Further info about the package is available here. The installation process just requires you to run the command:
```console
sudo apt install ros-noetic-dynamixel-workbench
```

To confirm a successful installation type:
```console
rospack find dynamixel_
```
And press *tab* to autocomplete. It should look like this:
![](https://i.postimg.cc/mg85NtZk/Screenshot-from-2022-03-04-20-52-05.png)

------
## *Dynamixel Wizard*
It is a powerful tool to test and set up the dynamixel line. We are gonna make some basic tests connecting one motor.
 
 1. **Connect the dynamixel line:** Details during the class.
 2. **Open dynamixel wizard:** Just in case.

 ![](https://i.postimg.cc/wMqNVTjx/Screenshot-from-2022-03-04-21-09-04.png)

 3. **Set up the connection parameters**: In the main menu goto to *Tools*, *Options*. Or just press *F4*. Use the parameters provided in the following picture:

 ![](https://i.postimg.cc/6302yJLk/Screenshot-from-2022-03-04-21-03-55.png)

 4. **Scan for the device**: In the main menu press the icon *Scan*, it should start a search with the provided params.

 ![](https://i.postimg.cc/VL5rLhSh/Screenshot-from-2022-03-04-21-13-26.png)
 ![](https://i.postimg.cc/rsHpr8dP/Screenshot-from-2022-03-04-21-14-33.png)

 5. **Play with the device:** If the connection is successful now you can play with the dynamixel motor. Remember just change the items that the professor indicates to you during the class. (Obviously, the important stuff is lock-red).

 ![](https://i.postimg.cc/Gmy4vsxJ/Screenshot-from-2022-03-04-21-03-09.png)

 6. **Disconnect the device and close:** Once the fun is over, it is time to disconnect the dynamixel device and close the dynamixel wizard.

 ![](https://i.postimg.cc/5tJ2vK0b/Screenshot-from-2022-03-04-23-04-31.png)

------
## *dynamixel_one_motor* package
Goto to the *catkin_ws*, clone the [repo](https://github.com/fegonzalez7/dynamixel_one_motor.git) and source:
```console
cd ~/catwin_ws/src
git clone https://github.com/fegonzalez7/dynamixel_one_motor.git
cd ..
source devel/setup.bash
```

Make sure that the FTDI is connected:
```console
lsusb
```

Check the USB ports and grand root permissions to the port:
```console
ls /dev/tty*
sudo chmod 777 /dev/ttyUSB0
```
*Normally USB0 is the port

Now launch the dynamixel_one_motor node:
```console
roslaunch dynamixel_one_motor one_controller.launch
```
It should look like this:

![](https://i.postimg.cc/y8414p0c/Screenshot-from-2022-03-04-22-53-53.png)

In a new terminal check the topics and nodes:
```console
rostopic list
rosservice list
```
![](https://i.postimg.cc/TPTThy7P/Screenshot-from-2022-03-04-22-54-35.png)

In contrast to the *turtlesim* that uses a topic to move the turtle, in the dynamixel package we must to use a Service. You will learn how to do it in class.

-----

### Acknowledgments:

 - Jose Manuel Fajardo
 - Sebastian Realpe
 - Hans Milos Toquica

This repo has taken a lot of effort, so consider leaving a star, follow me, and if you feel generous I have Paypal (just kidding).
