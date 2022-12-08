# XceptionV2

## 목표
`xception` 모델의 구조를 깊이 파악하고 개선 할 수 있는 점을 개선해가는 방향을 잡을 것임 


### 중간결과

#### 최적의 결과

1. inception A
![image](https://user-images.githubusercontent.com/71626430/199387802-e761cb50-218d-429f-9693-c30face6948b.png)

2. inception B

![image](https://user-images.githubusercontent.com/71626430/199387822-226766a3-4614-4856-a108-bf6629e1c3b0.png)

3. inception C
![image](https://user-images.githubusercontent.com/71626430/199387842-5569f155-228f-4bf0-b34f-e7c319240f67.png)

각각의 `inception module`을 `Xception` 모델의 residual Block에 끼워 넣는 실험을 진행함 

![image](https://user-images.githubusercontent.com/71626430/199388037-68e7cc77-657a-4ee2-822e-f9cc4c3ff39c.png)

이와 같은 순서 
EntryFlow : inception A => inception B

ExitFlow : inception C

를 넣었을 때 `test accuracy : 88,05%` 로 기본 `Xception`보다 더 높은 성능을 보여줌

# Data Augmentation

1. Albumentation을 이용한 augmentation
  - horizontal Flip, vertical Flip 조합을 이용했을 때 가장 성능이 좋았음
2. GAN을 이용한 DATA Augmentation
  - DCGAN
  - LSGAN
  - WGAN-GP
  위의 세 GAN을 이용해 테스트 
  - DCGAN과 LSGAN은 데이터의 양이 적어 loss가 발산하는 문제가 있었음
  - WGAN-GP가 느리지만 안정적으로 학습이 잘되는 모습을 보여줌

