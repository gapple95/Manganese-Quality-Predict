# 망간 농도 예측
### 망간예측 표준모델개발
    
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/gapple95/Taewha-Water-Level-Predict.git/HEAD) 
## 1. 목적
![주요 취수원의 원수 망간 농도 그림](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/5cf793e7-82ef-425c-b2de-f7716c304a76)
  - 광역 취수원 전체에서 망간이 검출
    <br> * <i> 12개소의 원수 평균농도는 먹는물 수질기준(0.05mg/L이하) 상회 </i>
  - 취수원이 호소수인 운문(정) 등 4개소는 동절기 전도(Turn-over)시점 등에는 고농도(0.4mg/L이상) 발생
  - 인천 적수 사태를 계기로 사회적 이슈로 대두
  - 데이터 융합형 예측 지표를 개발하여 하이브리드 AI 모형 개발
  <table border=0 align=center>
  <tr>
  <td>정확성</td><td>최대 오차 50%(1m ↑) 이상</td><td> 👉 </td><td>오차 10%(10cm↓) 이내</td>
  </tr>
  <tr>
  <td>신속성</td><td>실제 강우 상황 예측 불가</td><td> 👉 </td><td>3시간 ~ 6시간 사전 예측</td>
  </tr>
  <tr>
  <td>표준화</td><td>도시/지역별 특성 미고려</td><td> 👉 </td><td>지역특성 3단계로 표준화</td>
  </tr>
  </table>

 - 도시 하천의 특성별로 댐-하천-강우-해양 영향 인자를 구분하는 머신러닝 학습 방식으로 주요 지점별 수위를 예측

## 2. 데이터 현황
  - 주암댐/대청댐 및 화순 정수장
  - 수심, 수온, 용존산소, 전기전도도, 저수위, 평균기온, 최대기온, 최소기온, 풍속(2009 ~ 2019)
  - 화순(정) 원수 망간 농도, 주암댐 수심별 수질, 수문, 기상

## 3. 과업 수행 내용
### (1) 새로운 시뮬레이션 변수를 도입
  - 밀도 성층 변화 PEA(Potential Energy Anomaly)
  - 수층을 완전 혼합 시키는데 필요한 단위 체적당 일인데 수층의 현재 위치에너지와 수층이 수직적으로 완전히 혼합되었을 경우의 위치 에너지 차이
<br> ![PEA 그림](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/7d651f26-5f9b-4619-b13f-26f3fd3a5dfd)

### (2) 변수에 대한 보완책을 마련
  - 데이터 일관성을 유지하고 신뢰할 수 잇는 데이터 확보
    <br> * <i> Raw, 제거, Mean/Median, Zero or Frequent, K-nn Imputation, MICE, Deep Learning 등 </i>
  - 오결측 값이 다른 데이터와 관계가 있는지 확인 후, 전통적 방식 또는 신규 방식의 선택 적용하여 데이터 보간
<br> ![데이터 일관성 확보 노력 그림](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/6a4e0ce0-5fee-4cf8-a572-3f8323f58f8b)

### (3) 예측 모델 개발 및 선정
  - 과거자료(Sequence length)를 고려한 정확성 검토
<br> ![sequence length 그림](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/36ad2d56-73c1-4c75-b5f2-c92db3f0d37d)
  - 취수장 유입을 고려한 일별 예측으로 세분화(대청)
<br> ![예측예보 적용을 위한 최적 AI 모델 적용 결과 그림](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/6a7fb9e9-5781-47cb-bde2-5d7606af4bad)
  - 실 예보(예측) 활용을 위한 다수 모형 대상의 Ensemble 검토(대청)
<br> ![실예보(예측)활용을 위한 앙상블 검토](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/7ff853a7-5d72-4d8a-8014-58f31257c699)
  - 적용 기술의 표준화
<br> ![적용 기술의 표준화 그림](https://github.com/gapple95/Manganese-Quality-Predict/assets/50596733/5a4c9d00-df16-44ab-8086-5040571792e6)

## 4. 최종성과
### 성층 특성 반영 인자를 고려한 예측 결과 확보(baseline : 0.45 / 1단계 : 0.80 / 2단계 : 0.90)
  - (성과목표 달성) 0.45 (1일) -> 0.8 (3일 이상) 확보(주암 기준) -> 대청 확장
  - (성과) 논문1, 학술발표2, 실용화(컨설팅1, 멘토링1), SW등록(1, 추진중)
  - (기타) K-water WQE 시스템 내 반영 추진 (물환경처 등)
