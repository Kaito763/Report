# tutlebot3_slam
## 攝影
* **在raspberry pi上**
    * $ ros2 launch turtlebot3_bringup camera.launch.py format:=RGB888
* **在pc上**
    * $ rqt
## 建構地圖
* **在raspberry pi上**
    * If you are using LDS-01
    * $ echo 'export LDS_MODEL=LDS-01' >> ~/.bashrc
* **在raspberry pi上**
    * $ export TURTLEBOT3_MODEL=burger
    * $ ros2 launch turtlebot3_bringup robot.launch.py
* **在pc上(ubuntu 22.04)**
    * 第1個視窗
    * $ export TURTLEBOT3_MODEL=burger
    * $ ros2 launch turtlebot3_cartographer cartographer.launch.py
    * 第2個視窗
    * $ export TURTLEBOT3_MODEL=burger
    * $ ros2 run turtlebot3_teleop teleop_keyboard
## 錯誤紀錄
* **相關資料**
    * 官網: https://emanual.robotis.com/docs/en/platform/turtlebot3/sbc_setup/#sbc-setup
    * 故障與排除: https://emanual.robotis.com/docs/en/platform/turtlebot3/appendix_raspi_cam/#trouble-shooting
    * SSH 至樹梅派
    * 使用 ROS2 list 檢查 Camera Node 是否開啟
    * 在樹梅派上 也可List Camera Node
    * 必須用以下指令來開啟 Camera Node:ros2 launch turtlebot3_bringup camera.launch.py format:=RGB888
    * 按造官網的文件 開啟的Camera Node是無法透過RQT預覽影像的
* **結論:**
    * TurtleBOT 官方所提供的 ROS文件 "不完全可用" !!!
    * 一旦斷線必須重新開機
    * 資料來源:https://emanual.robotis.com/docs/en/platform/turtlebot3/slam/#run-slam-node

  
  



















