# tutlebot3_cammra
## Please complete turtlebot3_setup first
### on the rasberry pi
  * $ sudo apt update
  * $ sudo apt install -y python3-pip git python3-jinja2 \
    libboost-dev libgnutls28-dev openssl libtiff-dev pybind11-dev \
    qtbase5-dev libqt5core5a libqt5widgets5 meson cmake \
    python3-yaml python3-ply \
    libglib2.0-dev libgstreamer-plugins-base1.0-dev
  * $ sudo apt install ros-humble-camera-ros
  * $ git clone https://github.com/raspberrypi/libcamera.git
  * $ cd libcamera
  * $ meson setup build --buildtype=release -Dpipelines=rpi/vc4,rpi/pisp -Dipas=rpi/vc4,rpi/pisp -Dv4l2=true -Dgstreamer=enabled -Dtest=false -Dlc-compliance=disabled -Dcam=disabled -Dqcam=disabled -Ddocumentation=disabled -Dpycamera=enabled
  * $ ninja -C build
  * $ sudo ninja -C build install
  * $ sudo ldconfig
  * $ ros2 launch turtlebot3_bringup camera.launch.py format:=RGB888
### on the PC(ubuntu 22.04)
  * $ rqt
