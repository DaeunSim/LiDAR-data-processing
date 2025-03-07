#### PointNet이란?
###### 참고 : https://medium.com/@itberrios6/introduction-to-point-net-d23f43aa87d2
  - Point Cloud(=3차원 공간의 위치한 점들의 집합)을 입력받아 특징을 추출하여 어떠한 물체를 나타내는지 인식할 수 있는 딥러닝 모델
  - 포인트 클라우드의 회전이나 포인트들의 순서에 영향을 받지 않고 동일한 결과를 추출
    ex) 포인트들은 x,y,z 좌표를 가짐. A(2,2,1), B(2,2,0)로 입력이 되든 B(2,2,0), A(2,2,1) 순서로 입력이 되든 결과는 동일함.
  - 각각의 포인트들의 위치와 특징들을 학습하고(영역별로 특징을 추출하고 그 특징들로 전체적인 형상을 파악) 추출된 특징들을 인코딩하여 물체를 인식하고 분류.
  - Max pooling으로 전체적인 형상을 파악
    - [what is max pooling?]
    - [what is dimensionality reduction?]
    - 특정 사이즈의 kernel를 이동시키면서 특징을 추출하고, 관련이 없는 정보나 노이즈를 제거.
      이 과정은 feature map의 크기를 줄이기 때문에 빠른 계산이 가능. [Feature map]은 입력 데이터에서 특정 패턴이나 특징(텍스쳐, 선 등)들을 찾아낸 결과물.
  - T-Net 이란 neural network가 사용되어 포인트 클라우드의 회전이나 이동에 영향을 받지 않고 특징 추출.
  - [PointNet 결과물]
  - 포인트들의 관계나 구조 파악(=포인트들의 분포도나 인접한 포인트들이 형성하는 기하학적 특징), 복잡한 환경에서 물체를 정확하게 인식하거나,
    세밀한 패턴을 파악하는데 한계점이 존재. 이를 보완한 모델이 [PointNet++]

#### VoxelNet이란?
###### 참고 : https://medium.com/@minjinsormyagmarsuren/voxelnet-implementation-234d3d965a89
  - Point Cloud를 3D Voxel(=3차원의 큐브 형태)로 변환하여 객체를 감지.
  - Voxel feature encoding(VFE) layer를 통해 각 voxel내의 point들의 정보를 모아서 하나의 특징 표현으로 변환
  - 3D Convolution은 인접한 voxel들의 특징을 결합하여 처리. 이 과정을 통해 객체의 전체적인 형태와 패턴을 인식하고 더 세부적인 3D 공간 정보를 추출.
  - 특징을 추출한 후 RPN (=Region Proposal Network)이 객체가 있을만한 영역을 제안.


[PointNet++]: https://proceedings.neurips.cc/paper_files/paper/2017/file/d8bf84be3800d12f74d8b05e9b89836f-Paper.pdf
[PointNet 결과물]: https://stanford.edu/~rqi/pointnet/
[what is max pooling?]: https://www.alooba.com/skills/concepts/deep-learning/max-pooling/
[what is dimensionality reduction?]: https://www.ibm.com/think/topics/dimensionality-reduction
[Feature map]: https://www.ultralytics.com/glossary/feature-maps#:~:text=Feature%20maps%20are%20a%20fundamental,understand%20and%20interpret%20complex%20patterns
