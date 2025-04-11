#### [FAST LIO] on ROS2
<br>

#### a. [livox sdk2] 설치
gcc 버전 체크 
> gcc --version

소스 다운로드    
> mkdir -p ros2_lio/src    
> cd ros2_lio/src    
> git clone https://github.com/Livox-SDK/Livox-SDK2.git    
> cd ./Livox-SDK2

빌드
> mkdir build    
> cd build    
> cmake .. && make -j    
> sudo make install    
<img width="1117" alt="Screenshot 2025-04-11 at 08 33 41" src="https://github.com/user-attachments/assets/6bff5d59-5344-4734-b5f1-302ee73c8b04" />


#### b. [livox ros driver2] 설치
소스 다운로드
> cd ros2_lio/src    
> git clone https://github.com/Livox-SDK/livox_ros_driver2.git livox_ros_driver2    

빌드    ==> 버전 관련해서 에러가 남...    
> cd livox_ros_driver2    
> source /opt/ros/humble/setup.sh //or source install/setup.sh    
> ./build.sh humble    

—————————————————————————————————————----------------------------------    
ROS version is: ROS2    
Starting >>> livox_ros_driver2    
Starting >>> livox_sdk2    
[Processing: livox_ros_driver2, livox_sdk2]                                                         
Finished <<< livox_ros_driver2 [44.3s]                                          
--- stderr: livox_sdk2                                        
CMake Warning:
  Manually-specified variables were not used by the project:

    HUMBLE_ROS
    ROS_EDITION
—————————————————————————————————————----------------------------------

<img width="1117" alt="Screenshot 2025-04-11 at 09 09 51" src="https://github.com/user-attachments/assets/2245577e-856f-40e9-be24-7e759f13fe62" />






[FAST LIO]: https://github.com/hku-mars/FAST_LIO/tree/ROS2
[livox ros driver2]: https://github.com/Livox-SDK/livox_ros_driver2
[livox sdk2]: https://github.com/Livox-SDK/Livox-SDK2/blob/master/README.md
