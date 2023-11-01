# 망간 농도 예측(수정중)
### 망간예측 표준모델개발
    
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/gapple95/Taewha-Water-Level-Predict.git/HEAD) 
## 1. 목적
  - 댐 하류 도시 중소하천(27개)의 재해 실시간 모니터링과 홍수분석을 위한 시스템(K-water모델) 제공 및 운영 중
  - 데이터 관리 미흡 등으로 홍수 예측 수준 저하 및 시스템 활용 저조
   <br> * <i>홍수 시 댐 방류에 대한 <b>정확성, 신뢰성, 예측 가능성</b>이 현저히 떨어짐</i>
  - 예측 알고리즘(시계열)을 적용하여 도시 하천에 적합한 AI 모델개발
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
  - 수위국, 댐 방류, 강우, 조위(2012 ~ 2021)
  - 상류(댐), 중류(도심), 하류(조위)

## 3. 분석실행
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Kwater-AILab/Water-Level-Predict/HEAD)


## 4. 향후목표
  - (기술확산) 개발  AI 표준 모델을 타 유역에 확장 브랜드화 추진
  - (사업적용) 현업 홍수재해통합 관리사업 확대시 핵심 요소로 탑재
