# Artificial Neural Network

## Perceptron
- 1957년 개발된 최초의 AI 모형으로 선형 분류 모형의 형태를 가짐
- 특정 임계값의 초과 여부를 판단하는 함수를 적용 (1, -1로 결과 값을 내보내 분류)

### 활성화 함수 (Activation Function)
- 퍼셉트론의 임계값 초과 여부를 판단하는 함수
- 초기에 가중치를 랜덤하게 설정한 후 모델의 에러과 가중치를 개선해 나감
- 선형 분류 모형이기에 비선형 문제는 해결할 수 없음

## MLP
- Multi Layer Perceptron
- 기존의 퍼셉트론은 Input Layer, Output Layer로만 구성되어있으나, 중간에 Hidden Layer를 넣은 형태

### 구조
- Input Node의 수는 Input Data의 변수의 수
- Hidden Layer와 Hidden Node의 수는 사용자가 지정하는 하이퍼파라미터
- Output Layer는 최종적으로 모델의 결과값을 의미
    - 회귀분석을 하고자 하는 경우 Output Node의 수는 1
    - 0부터 9까지 숫자 분류하는 경우 Output Node의 수는 10
![](https://deepestdocs.readthedocs.io/en/latest/004_deep_learning_part_2/image/0040_fig0.jpg)


## Feed Forward & Back Propagation
![](https://www.researchgate.net/publication/303744090/figure/fig3/AS:368958596239360@1464977992159/Feedforward-Backpropagation-Neural-Network-architecture.png)

### Feed Forward

Input에서 가중치와 Hidden Layer을 거쳐 Output을 내보내는 과정

### Back Propagation

- Feed Forward 과정을 통해 모델의 예측 값과 실제 값의 차이(Error)를 계산함
- 이 에러를 바탕으로 신경망들의 가중치를 갱신함
- 뒤에서부터 갱신을 진행하기 때문에 Back Propagation 과정이라고 부름


위 두 과정을 반복하여 가중치를 업데이트 하면서 신경망의 Output 값이 실제 값에 가까워지며 모델 학습이 이루어짐

Feed Forward와 Back Propagation의 한 과정을 Epoch(세대)라고 부름
