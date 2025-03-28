#### LiDAR란 무엇인가?
  - LiDAR(=Ligiht Detection and Ranging)는 물체에게 레이저를 쏘아 반사되어 돌아오는 빛을 감지하여 물체의 특성 및 거리를 측정하는 기술이다.
  - 라이다 센서는 프레임 단위로 주변 환경을 스캔한다. 각 스캔마다 포인트 클라우드 데이터를 생성한다.
  - 실시간으로 주변 환경을 스캔하여 장애물을 감지하고 분류가 필요한 자율주행 자동차, 로봇, 및 고해상도 지도를 생성하는데 사용된다.

#### LiDAR의 동작 원리
  - 센서가 타켓 물체에게 레이저 빛을 쏜다.
  - 이 빛이 물체에 부딪혀 반사된다.
  - 라이다의 수신기(=Detector)가 반사된 빛을 감지한다.
  - 이 때 빛이 돌아오기까지 걸린 시간과 빛의 강도를 측정한다.
  - 측정된 시간과 빛의 속도를 이용하여 물체와의 거리를 측정한다.
  - 이 과정을 계속해서 반복하여 주변 환경을 그릴 수 있을만큼 데이터를 수집한다.

#### LiDAR 데이터 구조
  - 라이다 데이터는 포인트 클라우드(=Point cloud) 형태로 저장된다. 포인트 클라우드는 3D 공간에서 물체나 환경를 표현하기 위해
    사용되는 데이터 구조이자 포인트들의 집합이다. 데이터는 주로 .pcd (Point Cloud Data) 포맷의 파일로 저장된다.
    #### 포인트 클라우드
    - XYZ Coordinates : 각 포인트는 3D 공간에서의 X, Y, Z 좌표를 가진다.
    - Intensity : 반사된 빛의 강도로서 1~256 값을 가진다. 물체의 재질에 따라 다른 강도를 가진다.
      - 8비트 ADC(=Analog to Digital Converter)를 사용하는 경우 표현할 수 있는 값의 범위가 1~256이다.
      - ex) 금속 물체에서는 High Intensity를 가지고, 물에서 반사된 빛은 Low Intensity를 가진다.
    - Return Number : 한 번의 레이저 빛에서 여러 물체에서 반사될때 각 반사의 순서를 나타낸다. 
    - RGB : 색상 정보를 포함할 수 있다. (라이다 센서별로 다름)
    - Scan Angle : 포인트가 수집될 때의 레이저 빔의 각도 정보이다.
    - GPS Time : 포인트가 수집된 시간 정보를 나타낸다.

***

#### SLAM이란 무엇인가?
  - SLAM(=Simultaneous Localisation and Mapping)은 장소 정보가 없는 새로운 곳에서 길을 찾는 기술이다.
  - 자기가 어디에 있는지 위치를 계산하고(=Localisation), 주변 환경에 대한 정보를 수집하며 지도를 만든다(=Mapping)
  - 자율주행, 드론, 산업용 로봇등에 사용되며, GPS 신호가 없는 환경에서 유용하게 사용될 수 있다.

#### SLAM 동작 원리
  - 카메라나 LiDAR로 주변 환경에 대한 정보를 수집한다.
  - 이미지나 포인트 클라우드로 다른곳과 구별될 수 있는 특징적인 지점들을 인식하고 추출한다.
  - 가속도계(=로봇의 이동)와 자이로스코프로(=회전 측정)를 사용하여 로봇의 위치와 방향을 측정한다.
  - Kalman Filters(=실시간 위치 추적)/GraphSLAM(=전체 경로 최적화)과 같은 알고리즘을 이용하여 경로와 지도를 업데이트한다.
  - 이 과정을 반복하며 실시간으로 자신의 위치를 파악하고 지도를 개선해 나간다.

