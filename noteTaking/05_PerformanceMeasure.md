# 성능 지표

## MSE

- Mean Squared Error
- 회귀 모형에서 많이 사용되는 성능 지표
- 예측 값과 실제 값의 차이에 대해 평균 제곱합
- 낮을수록 좋은 성능

## MAPE

- Mean Absolute Percentage Error
- MSE에 비해 절대적인 지표
- 예측 값과 실제 값의 차이를 실제 값으로 나누어 실제 값 대비 몇 % 정도의 오차가 있는지

## 정확도

- 분류 문제에서 가장 많이 사용하는 성능 지표
- ![](https://miro.medium.com/max/1508/1*fUnVMuu91SR_Ehrfvne2iA.jpeg)
    - Accuracy : 정확도
    - Precision : 정밀도
    - Recall : 재현율
    - Specificity : 특이도

## F1-Measure

- Class Imbalance 상황에서 많이 사용하는 성능 지표
- Precision과 Recall의 조화 평균
- 불량 예측 시 정확한 예측 비율과 실제 불량 중 잘 예측한 비율