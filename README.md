# Insurance_claim-Fraud-Project

## 주제 설정
- 해결하고자 하는 문제, 시나리오: 의료서비스 제공자의 의료보험 청구 사기 탐지
- 문제 해결의 필요성:<br>
  a. '사기': 사실을 오인시키는 등의 방법으로 남을 기망, 무단으로 경제적 이득을 얻거나 다른 사람으로 하여금 얻게 하는 행위. 도덕적으로 큰 죄 <br>
  b. healthcare fraud, 의료보험 사기도 그 중 하나<br>
  c. 미국 의료보험 체계에서, 의료서비스 제공자(의사, 간호사, 약사 등)는 환자의 진료 상세를 기록, 보험 가입자(환자)를 대신하여 보험금을 청구<br>
  d. 의료보험 사기는 1) 제공되지 않은 의료 서비스를 청구하거나 2) 의료 서비스에 대해 중복 청구하거나 3) 제공된 의료서비스를 오기재하거나 4) 실제 제공된 내역보다 부풀려 보험금을 청구하거나 5) 의료보험 대상이 아닌 서비스에 대해 대상인 서비스로 청구하는 등의 식으로 나타남.<br>
  e. 그렇기에, 본 프로젝트에서는 의료서비스 제공자의 보험금 청구가 '잠재적으로' 사기 행위일지 예측하고 상기 경제적 손실 방지를 도모하고자 함<br>
  f. 경제적 손실 방지 뿐만 아니라 적법한 방식으로 불특정 다수가 필요할 때 이용할 수 있는 건강한 의료보험 체계 형성에 기여할 수 있음<br>

## 진행 기간
2022.07.22-07.28(5일)

## 문제 해결 접근 방식 설정
- 특정 청구 건이 사기인지 아닌지 (0/1) 이진 분류<br>
- 해결하고자 하는 문제 정의에 적절한 타겟 선정: 'PotentialFraud' (Yes/No)<br>
- 타겟을 잘 설명할 수 있을 만한 특성에 대한 가설 설정:<br>
  a. 가입자의 연령(Age: D0D-D0B)<br>
  b. 가입자의 기저질환(ChronicCond_) 여부, 특정 질환(RenalDisease) 여부<br>
  c. 보험금(청구.배상), 납부한 보험료<br>
  d. 보험금 청구기간<br>

상기 특성들이 보험 청구건이 사기로 예측될 확률에 영향을 줄 것이다.<br>

## [데이터 전처리, EDA, 인코딩 & 시각화](https://github.com/aurorave/Insurance_claim-Fraud-Project/blob/main/02.%20AI_14_%EB%B0%95%EC%84%B1%ED%9D%AC(Colab_1%20of%202).ipynb)
- 머신러닝에 적합한 형태로 데이터타입 변경
- 특성의 분포 확인, 이상치 제거
- 피처 상관 분석, 시각화

## [모델링 및 모델해석](https://github.com/aurorave/Insurance_claim-Fraud-Project/blob/main/02.%20AI_14_%EB%B0%95%EC%84%B1%ED%9D%AC(Colab_2%20of%202).ipynb)
- 타겟 클래스 불균형 보정 (SMOTE)
- 기준모델baseline model 선정, 모델링 성능 평가
- 문제 정의에 맞는 평가지표 선택, 모델 성능 설명
- 여러 수치적 지표 및 permutation importance, pdp, shap 등을 활용해 최종모델 설명
