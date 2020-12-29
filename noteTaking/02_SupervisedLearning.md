# Supervised Learning

- 지도 학습 모델의 종류

## 선형 회귀 모델

- y = ax+b
- 독립 변수 하나만으로 종속 변수를 예측하는 모델

- ![](https://upload.wikimedia.org/wikipedia/commons/b/be/Normdist_regression.png)
- 선형 회귀 모델은 직선의 기울기를 예측 값과 실제 값의 제곱합이 줄어드는 방향으로 구함

- 변수가 여러개일 경우 __다중 선형 회귀 모델__ 이라 함 

- 장점
    - 변수의 설명력 측면에서 좋음
    - 직선의 방정식과 같은 모델이기 때문에 독립 변수가 종속 변수에 어떤 영향을 끼치는지 알 수 있음

## 회귀 계수 축소 모델

- 적절한 변수만 선택하여 모델에 사용하는 것
- MSE 값을 최소화 시키는 것과 더불어 회귀 계수 자체도 축소시키도록 Loss를 구성
- 종류
    - LASSO : 회귀 계수가 완전히 0이 되도록 축소시킬 수 있음
     ![](https://t1.daumcdn.net/cfile/tistory/9992333C5C41B55F29)
    - Ridge : 회귀 계수가 0으로 가까워지긴 하지만 완전히 0이 되진 않음
     ![](https://t1.daumcdn.net/cfile/tistory/9940C93D5C41B2EE13)
    - 변수를 선택하는 측면에서 LASSO가 우위에 있으나 성능 측면에서는 Ridge가 더 우위
    - ElasticNet은 LASSO와 Ridge의 중간 모델

## 의사 결정 나무
- Decision Tree : 해석력이 높고 직관적인 모델
- 종속 변수가 독립 변수의 어떤 특정 조건에 따라 잘 나뉠 수 있는지를 설명한 모델
- 높은 설명력을 가지나 Prediction의 성능인 부족해서 단일 모델보다는 이를 발전시킨 Ensemble 모델을 사용 
- ![](https://miro.medium.com/max/1400/1*WerHJ14JQAd3j8ASaVjAhw.jpeg)

## k-NN
- k Nearest Neighbor 알고리즘
- 가장 가까운 k개의 데이터를 이용하여 해당 데이터의 출력 값을 예측하는 직관적인 모델
- ![](https://blog.kakaocdn.net/dn/cvzGSE/btqw569xJ8n/DfckialHS6fgKmDZpy4L01/img.png)

## 신경망
- Neural Network : 딥러닝의 기초가 되는 모델
- Input, Hidden, Output (입력층, 은닉층, 출력층)으로 구성됨
- 각 층을 연결하는 노드의 가중값을 업데이트 하며 학습함
- MSE 와 같은 Loss 를 설정하고 이 Loss가 최소화 되는 지점을 찾기 위해 가중값을 업데이트 함
- 장점
    - 내가 지니고 있는 학습 데이터로 완벽한 모델을 만들 수 있음
    - 즉, 어떤 모델을 만들든 **학습 데이터 내**에서 정확도 100%에 이르는 모델을 구축
- 단점
    - **학습 데이터 내**에서만 정확도 100% (과적화)
- 신경망을 점차 가중치의 업데이트를 하면서 해결이 가능은 함
- ![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Overfitting.svg/1200px-Overfitting.svg.png)

## SVM
- Support Vector Machine : 신경망의 학습 성향에서 발생하는 과적합 문제에 대한 해결책을 제시한 모델
- ![](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2019/07/introduction-to-SVM.png)
- 직선을 그었을 때 클래스 간 거리가 비슷하도록 잘 긋도록 하는 학습 방법
- 장점
    - 학습 과정 내에서 어느 정도 과적합을 방지 가능
- 단점
    - 데이터의 차원이 커질 수록, 변수나 데이터가 많아질 수록 학습 시간이 매우 오래 걸림

## Ensemble Learning
- 다양한 모델을 만들어 우리가 예측하고자 하는 모델에 대한 다양한 의견을 수렴해 투표를 바탕으로 최종적인 예측 값을 만듬 
- 종류
    - Bagging : 데이터를 재구성해 모델을 만듦
    - RandomForest : 데이터와 변수를 랜덤으로 추출해 모델을 만듦
    - Boosting : 잘 맞추지 못하는 데이터를 좀 더 집중적으로 학습 (Gradient Boosting을 주로 사용)