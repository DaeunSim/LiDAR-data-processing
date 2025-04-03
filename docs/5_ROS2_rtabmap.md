#### RTAB-Map (Real-Time Appearance-Based Mapping)    
<br>

#### a. rtabmap 패키지 설치 ==> launch 파일을 찾을 수 없음
rtab-map 설치
> sudo apt install ros-humble-rtabmap-ros

launch 설치
> sudo apt install ros-humble-rtabmap-launch
> ros2 launch --help

rtab-map GUI 설치
> sudo apt install ros-humble-rtabmap-viz

ros2 설정 파일 실행
> source .bashrc

</br>    

#### b. rtabmap 빌드로 재시도 ===> launch 파일 확인
소스 파일 폴더 생성
> mkdir -p ~/ros2_ws/src    
> cd ~/ros2_ws    

repo 복제
> git clone https://github.com/introlab/rtabmap.git src/rtabmap    
> git clone --branch ros2 https://github.com/introlab/rtabmap_ros.git src/rtabmap_ros

rtabmap_ros rtabmap_costmap_plugins 빌드 ===> 패키지 에러남
> colcon build --packages-select rtabmap_ros rtabmap_costmap_plugins    
<img width="1063" alt="Screenshot 2025-04-01 at 21 37 16" src="https://github.com/user-attachments/assets/9ed4ce88-68f6-49b5-863d-18f7f3600839" />

rtabmap_ros 재빌드 (패키지 제외)
> colcon build --packages-ignore rtabmap_msgs rtabmap_python rtabmap_conversions rtabmap_rviz_plugins rtabmap_sync rtabmap_util rtabmap_odom rtabmap_slam rtabmap_viz rtabmap_demos rtabmap_examples

환경 파일 실행
> source install/setup.bash

launch 파일 위치
> ros2_ws/install/rtabmap_launch/share/rtabmap_launch/launch/rtabmap.launch.py

launch 파일 실행
> ros2 launch rtabmap_launch rtabmap.launch.py
<img width="1164" alt="Screenshot 2025-04-01 at 22 32 01" src="https://github.com/user-attachments/assets/206447ee-74da-466a-aa91-fea260b23da2" />
실행시 먹통되는 현상이 있음    
<img width="1221" alt="Screenshot 2025-04-03 at 19 59 33" src="https://github.com/user-attachments/assets/044430a2-adae-46d0-8fc5-1659dc6ba0ce" />

</br>    

#### c. video 실행    
샘플 비디오 다운로드 (ros_ws/sample/test.avi 파일명으로 저장)
> https://github.com/introlab/rtabmap/wiki/Stereo-mapping    

비디오 재생을 위해서는 opencv 설치 필요          
> sudo apt install ros-humble-image-transport
> sudo apt install ros-humble-cv-bridge    
> sudo apt install libopencv-dev    
> sudo apt install ros-humble-rclpy    
> sudo apt install libjpeg-dev    
> sudo apt install libpng-dev    
> sudo apt install libgstreamer1.0-dev    
> sudo apt install libgstreamer-plugins-base1.0-dev    
> sudo apt install build-essential    
> sudo apt install pkg-config    
> sudo apt install libboost-all-dev

repo 복제
> cd ~/ros2_ws/src
> git clone https://github.com/ros-drivers/video_stream_opencv.git

빌드 ==> video_stream_opencv 빌드 실패 ===> CMakeList 쪽에서 에러가 남...
> colcon build --packages-ignore rtabmap_msgs rtabmap_python rtabmap_conversions rtabmap_rviz_plugins rtabmap_sync rtabmap_util rtabmap_odom rtabmap_slam rtabmap_viz rtabmap_demos rtabmap_examples










