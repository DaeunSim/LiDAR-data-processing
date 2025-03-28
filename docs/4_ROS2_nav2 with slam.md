#### ROS2의 SLAM Toolbox 패키지를 사용한 2D SLAM 실습

#### Tutorials: https://docs.nav2.org/tutorials/docs/navigation2_with_slam.html

##### 1. Ubuntu 22.04에 [ROS2 Humble] 설치
<img width="800" title="talker-listener example" alt="Screenshot 2025-03-12 at 22 38 39" src="https://github.com/user-attachments/assets/41103801-b811-4b3c-be86-579cdda45661" />

##### 2. Navigation2, Turtlebot3, and SLAM Toolbox 설치

&emsp; a. Navigation2 설치    
&emsp; sudo apt install ros-humble-navigation2    
&emsp; sudo apt install ros-humble-nav2-bringup

&emsp; b. Turtlebot3 설치     
&emsp; sudo apt install ros-humble-turtlebot3*    

&emsp; c. ~/.bashrc에 path 추가    
&emsp; source /opt/ros/<ros2-distro>/setup.bash    
&emsp; export TURTLEBOT3_MODEL=waffle  # Iron and older only with Gazebo Classic    
&emsp; export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:/opt/ros/humble/share/turtlebot3_gazebo/models # Iron and older only with Gazebo Classic

     
&emsp; d. Turtlebot3 실행       
&emsp; ros2 launch nav2_bringup tb3_simulation_launch.py headless:=False

<img width="800" title="turtlebot3-launch-error" alt="Screenshot 2025-03-28 at 22 37 45" src="https://github.com/user-attachments/assets/95c5637d-3dbc-4368-81ac-245500201147" />


...? /opt/ros/humble/share 폴더에는 turtlebot3_gazebo 패키지가 존재하지 않음 ==> 앱 실행시 에러남: 패키지 추가 설치 또는 환경 설정 수정 필요해보임     
...? 튜토리얼에서 말하는 Jazzy and newer, Iron and older 버전의 의미를 모르겠음   










[ROS2 Humble]: https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html
