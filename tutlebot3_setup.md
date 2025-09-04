# tutlebot3_setup
## Install ros deb and turtlebot3 deb(on the PC)
  * open your microsoft store downlond ubuntu22.04
## On the PC terminal(ubuntu22.04)
**Visit** the (https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html) page  
```
  sudo apt install ros-humble-gazebo-*
```
```
  sudo apt install ros-humble-cartographer
```
```
  sudo apt install ros-humble-cartographer-ros
```
```
  sudo apt install ros-humble-navigation2
```
```
  sudo apt install ros-humble-nav2-bringup
```
```
  source /opt/ros/humble/setup.bash
```
```
  mkdir -p ~/turtlebot3_ws/src
```
```
  cd ~/turtlebot3_ws/src/
```
```
  git clone -b humble https://github.com/ROBOTIS-GIT/DynamixelSDK.git
```
```
  git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
```
```
  git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3.git
```
```
  sudo apt install python3-colcon-common-extensions
```
```
  cd ~/turtlebot3_ws
```
```
  colcon build --symlink-install
```
```
  echo 'source ~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc
```
```
  source ~/.bashrc
```
```
  echo 'export ROS_DOMAIN_ID=30 #TURTLEBOT3' >> ~/.bashrc
```
```
  echo 'source /usr/share/gazebo/setup.sh' >> ~/.bashrc
```
```
  echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc
```
```
  source ~/.bashrc
```
  ## Install ubuntu22.04 (on the rasberry pi)
  * 1.Download deb file
    
  ![](https://github.com/Kaito763/Report/releases/download/rasberry_pi/rasberry_pi1.png)
  
  ##Please prepare an SD card and insert it into the PC
  * 2.Run Raspberry Pi Imager.
  * 3.Click CHOOSE OS.
  * 4.Select Other gerneral-purpose OS.
  * 5.Select Ubuntu.
  * 6.Select Ubuntu Server 22.04.5 LTS (64-bit) that support RPi 3/4/400.
    (Choose Server OS, not desktop OS)
  ![](https://github.com/Kaito763/Report/releases/download/rasberry_pi/rasberry_pi2.png)
    
  * 7.Click CHOOSE STORAGE and select the micro SD card.
  * 8.Click Next to install Ubuntu.
  * 9.Click Edit Setting for wifi and ssh setting.

  ![](https://github.com/Kaito763/Report/releases/download/rasberry_pi/rasberry_pi3.png)
  
  * 10.Set username and password, Configure wireless LAN, Wireless LAN country. And activate Enable SSH with Use password authenication in SERVIES tab.

  ![](https://github.com/Kaito763/Report/releases/download/rasberry_pi/rasberry_pi4.png)

## Install ros deb and turtlebot3 deb(on the rasberry pi)
* 1.SD card  into the rasberry pi 
* 2.Enter your username and password
* 3.open your pc terminal,Enter the
```
    ssh username@rasberry pi IP# ex:ssh user@192.168.103.136
```
* 4.Enter the following command
```
   sudo apt install python3-argcomplete python3-colcon-common-extensions libboost-system-dev build-essential
```
```
   sudo apt install ros-humble-hls-lfcd-lds-driver
```
```
   sudo apt install ros-humble-turtlebot3-msgs
```
```
   sudo apt install ros-humble-dynamixel-sdk
```
```
   sudo apt install ros-humble-xacro
```
```
   sudo apt install libudev-dev
```
```
   mkdir -p ~/turtlebot3_ws/src && cd ~/turtlebot3_ws/src
```
```
   git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3.git
```
```
   git clone -b humble https://github.com/ROBOTIS-GIT/ld08_driver.git
```
```
   git clone -b humble https://github.com/ROBOTIS-GIT/coin_d4_driver
```
```
   cd ~/turtlebot3_ws/src/turtlebot3
```
```
   rm -r turtlebot3_cartographer turtlebot3_navigation2
```
```
   cd ~/turtlebot3_ws/
```
```
   echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc
```
```
   source ~/.bashrc
```
```
   colcon build --symlink-install --parallel-workers 1
```
```
   echo 'source ~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc
```
```
   source ~/.bashrc
```
```
   sudo cp `ros2 pkg prefix turtlebot3_bringup`/share/turtlebot3_bringup/script/99-turtlebot3-cdc.rules /etc/udev/rules.d/
```
```
   sudo udevadm control --reload-rules
```
```
   sudo udevadm trigger
```
```
   echo 'export ROS_DOMAIN_ID=30 #TURTLEBOT3' >> ~/.bashrc
```
```
   source ~/.bashrc
```
* 4.Depending on your LDS model, use the appropriate model: LDS-01, LDS-02, or LDS-03.
```
   echo 'export LDS_MODEL=LDS-01' >> ~/.bashrc # If you are using LDS-01
```
```
   echo 'export LDS_MODEL=LDS-02' >> ~/.bashrc # If you are using LDS-02
```
```
   echo 'export LDS_MODEL=LDS-03' >> ~/.bashrc # If you are using LDS-03
```
* 5.Apply changes with the command below.
```
source ~/.bashrc
```
* 6.Enter the following command
```
  sudo dpkg --add-architecture armhf  
```
```
  sudo dpkg --add-architecture armhf  
```
```
  sudo apt-get update  
```
```
  sudo apt-get install libc6:armhf
```
```
  export OPENCR_PORT=/dev/ttyACM0  
```
```
  export OPENCR_MODEL=burger
```
```
  rm -rf ./opencr_update.tar.bz2
```
```
  wget https://github.com/ROBOTIS-GIT/OpenCR-Binaries/raw/master/turtlebot3/ROS2/latest/opencr_update.tar.bz2   
```
```
  tar -xvf opencr_update.tar.bz2
```
```
  wget https://github.com/ROBOTIS-GIT/OpenCR-Binaries/raw/master/turtlebot3/ROS2/latest/opencr_update.tar.bz2   
```
```
  tar -xvf opencr_update.tar.bz2
```   
* 7.ssh username@rasberry pi IP#On the your pc terminal
* 8.Enter the following command
``` 
  export TURTLEBOT3_MODEL=burger
```
```
ros2 launch turtlebot3_bringup robot.launch.py
```
* 9.check your ROS_DOMAIN_ID#On the P_C and rasberry pi
```
  export ROS_DOMAIN_ID=30 
```
```
  export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
```
* 10.Enter the following command#On the PC(ubuntu22.04)
```
export TURTLEBOT3_MODEL=burger
```
```
ros2 run turtlebot3_teleop teleop_keyboard
```
* References
   https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/#pc-setup
  




  



















