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

## 활성 함수 (Activation Function)

- 신호를 입력받아 처리하는 함수
- ![](https://miro.medium.com/max/1170/1*abHGVMc8bTFVFSvB6ZYaBg.png)
- 신경망에서는 기본적으로 비선형 활성 함수를 사용

### 시그모이드 함수
- ![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/88/Logistic-curve.svg/1200px-Logistic-curve.svg.png)

- 입력 값에 대해서 0 이하이면 0.5 이하, 0 이상이면 0.5 이상의 값을 출력하는 함수 (Scaling)
- 시그모이드 함수의 경우, Back Propagation 과정 중에 Gradient Vanishing 현상이 발생할 수 있음

## 경사 하강법

- Gradient Descent Method

## Universal Approximation Theorem

- Hidden Layer가 1개 이상인 신경망은 학습 데이터 내에서 어떤 함수든 근사시킬 수 있다

- "신경망이 엄청 좋은 모델이구나"
    - 학습 데이터 내에서만 한정 (과적합의 문제 발생)

- "Hidden Layer가 1개 이상이면 굳이 Layer를 깊게 해야 하나?"
    - 깊은 Layer = 복잡한 모델

# NN의 단점

## Overfitting

- 완벽히 해결하는 방법은 없음
- 실험 설계를 통해 적절히 나누어 적절한 모델과 변수를 선택해야 함

## Gradient Vanishing Problem
- 기울기가 사라지는 현상
- Sigmoid 함수의 output은 0~1 사이이나, 미분 할 경우 최댓 값은 0.25
- Hidden Layer가 깊어질 수록 sigmoid 를 미분하여 곱하는데 값이 점점 0에 수렴하게 됨