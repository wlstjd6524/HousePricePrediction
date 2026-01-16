[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/gmRFsg7-)
# House Price Prediction
## Team
<table>
  <tr>
    <td> <div align=center> 👑 </div> </td>
    <td> <div align=center> 🙍 </div> </td>
    <td> <div align=center> 🙍 </div> </td>
    <td> <div align=center> 🙍‍♂ </div> </td>
  </tr>
  <tr>
    <td> <div align=center> <b>이진성</b> </div> </td>
    <td> <div align=center> <b>고아연</b> </div> </td>
    <td> <div align=center> <b>윤소정</b> </div> </td>
    <td> <div align=center> <b>김대섭</b> </div> </td>
  </tr>
  <tr>
    <td> <img width="1024" height="1024" alt="Image" src="https://github.com/user-attachments/assets/173c3970-a60c-49de-8b86-593894732cfd" /> </td>
    <td> <img width="1024" height="1024" alt="Image" src="https://github.com/user-attachments/assets/3e52d169-0141-4dfb-b36b-004f87f01905" /> </td>
    <td> <img width="1024" height="1024" alt="Image" src="https://github.com/user-attachments/assets/9e7c51c7-d3c8-4512-a3b2-0c35905e2256" /> </td>
    <td> <img width="1024" height="1024" alt="Image" src="https://github.com/user-attachments/assets/e3e981fc-f821-4ef9-a30b-cd4b5c350a26" /> </td>
  </tr>
  <tr>
    <td> <div align=center> <a href="https://github.com/wlstjd6524"> <img alt="Github" src ="https://img.shields.io/badge/Github-181717.svg?&style=plastic&logo=Github&logoColor=white"/> </div> </td>
    <td> <div align=center> <a href="https://github.com/ayoun88"> <img alt="Github" src ="https://img.shields.io/badge/Github-181717.svg?&style=plastic&logo=Github&logoColor=white"/> </div> </td>
    <td> <div align=center> <a href="https://github.com/Lucia128"> <img alt="Github" src ="https://img.shields.io/badge/Github-181717.svg?&style=plastic&logo=Github&logoColor=white"/> </div> </td>
    <td> <div align=center> <a href="https://github.com/"> <img alt="Github" src ="https://img.shields.io/badge/Github-181717.svg?&style=plastic&logo=Github&logoColor=white"/> </div> </td>
    </tr>
</table>

## 0. Overview
### Environment
- OS : Windows10 / VSCode SSH Server - Jupyter Notobook
- Python 3.10
- LightGBM
- Optuna
- Pandas, Numpy, Scikit-Learn, math, tqdm

### Evaluation
- 평가지표로는 RMSE 를 활용
<img width="246" height="101" alt="Image" src="https://github.com/user-attachments/assets/b05b3732-f668-460a-ae12-d6b55627605b" />

## 1. Competiton Info

### Overview

- House Price Prediction | 아파트 실거래가 예측
- 서울의 아파트 실거래가 데이터를 기반으로 아파트 실거래가를 예측하는 대회

### Timeline

- December 01, 2025 - Make Study1
- December 03, 2025 - Setting Guidelines
- December 04 ~ 06, 2025 - Data EDA Start
- December 07 - Create with Derivative Variables Guidelines & Adopting Model and Data Classification Methods
- December 08 ~ 09 - Modeling & Tuning | Create file for submission

## 2. Components

### Directory

<img width="498" height="370" alt="Image" src="https://github.com/user-attachments/assets/72a4d5aa-4cd7-4e96-966d-58be93bbd2a6" />

## 3. Data descrption

### Dataset overview

주요 데이터는 .csv 형태로 제공되며, 목표는 서울시 아파트의 각 시점의 거래금액을 예측하는 것입니다. <br>
학습 데이터는 (111822, 52) 의 사이즈를 가지고 있으며, 예측해야 할 값(Target) 을 포함한 여러가지 아파트에 대한 정보가 담긴 변수들이 제공됩니다. <br>

<img width="1498" height="201" alt="Image" src="https://github.com/user-attachments/assets/e80b2573-1cd4-4219-8654-affea89c05e4" /> <br>

학습 데이터의 기간은 200701 ~ 202306 입니다. <br>
각 변수들은 아래와 같은 결측치 비율을 가지고 있습니다. <br> 

<img width="1062" height="434" alt="Image" src="https://github.com/user-attachments/assets/99049c51-5032-41ac-af03-0b49457d08f2" /> <br>

또한 아파트 거래금액에 영향을 미칠 수 있는 추가 외부 데이터인 버스정류장 정보 와 지하철역 정보 데이터도 제공됩니다. <br> 

<img width="612" height="169" alt="Image" src="https://github.com/user-attachments/assets/a89114e7-c9ee-43b6-b906-86beaeaf5110" />

<img width="413" height="171" alt="Image" src="https://github.com/user-attachments/assets/9a9ecc6a-413d-495b-89a1-077f1110027c" />

추가적으로 팀원들과 회의를 거쳐서 진행한 아파트 거래금엑에 영향을 미칠 수 있는 요인을 생각해보고 추가로 고려할 수 있는 외부데이터인 초,중,고등학교 정보가 들어있는 데이터셋과 금리에 대한 정보가 담긴 외부데이터셋을 적용하였습니다. <br>


### EDA

<img width="790" height="390" alt="Image" src="https://github.com/user-attachments/assets/96682efc-bfd4-46a7-b4f3-d68a10b5f5fd" /> <br>
실제 실거래가 분포(Target) 를 나타낸 그래프 <br>
실거래가 분포(Target)는 **강한 우측 꼬리** 를 가진 비대칭 분포를 나타낸다.

<img width="790" height="390" alt="Image" src="https://github.com/user-attachments/assets/0b6f174b-e99d-4d8f-add7-32357eb136e7" /> <br>
log1p 변환을 통해 분포가 정규분포 형태로 안정화되어 모델 학습에 더 적합한 형태가 되었다.

<img width="589" height="390" alt="Image" src="https://github.com/user-attachments/assets/5ce36ed1-178b-419f-950e-8cd5fafe83e4" /> <br>
전용면적 과 Target(가격) 간의 상관관계를 나타낸 그래프<br>
전용면적이 클수록 가격이 전반적으로 상승하는 양의 상관관계가 관찰된다.

<img width="1389" height="390" alt="Image" src="https://github.com/user-attachments/assets/3bcd47b6-e57b-4f58-8168-d58dbc0e0334" /> <br>
연도별 평균 실거래가 추이를 나타낸 그래프<br>
2013년 이후로 꾸준한 상승세가 나타나며, 2020년 이후 급격한 가격 상승이 두드러는걸 파악할 수 있다.

<img width="1389" height="390" alt="Image" src="https://github.com/user-attachments/assets/86fd1c99-5fb0-4dea-845e-8677ff6c13a6" /> <br>
연도별 거래량 변화를 나타낸 그래프<br>
2015년 거래량이 가장 높으며, 2021년 이후 급격한 감소가 나타난다.

<img width="1189" height="390" alt="Image" src="https://github.com/user-attachments/assets/2e10625d-a5b9-47f4-bfb4-ca8c297be0c6" /> <br>
월별 평균 실거래가 추이를 나타낸 그래프<br>
계절적 패턴을 분석함으로서, 6월에 가격이 가장 높고 3월이 가장 낮아, 완만한 계절적 패턴이 확인된다.

<img width="1790" height="390" alt="Image" src="https://github.com/user-attachments/assets/753e2cab-34cb-46f9-9933-e8eef2e77be8" /> <br>
전체 기간 월별 평균 실거래가 추이<br>
장기적 관점으로 전체적으로 완만한 상승 흐름을 보이다가, 2020년 이후 급격한 가격 상승이 두드러진다.

<img width="789" height="590" alt="Image" src="https://github.com/user-attachments/assets/20cfe756-9ade-4028-8525-6873562597a5" /> <br>
구별 평균 실거래가 Top25<br>
강남·서초·용산 등 주요 지역이 가장 높은 가격대를 형성하며, 지역 간 뚜렷한 가격 격차가 확인된다.

<img width="989" height="590" alt="Image" src="https://github.com/user-attachments/assets/eaf96f8d-ef02-4e69-a37c-875efc267a72" /> <br>
평균 실거래가 상위 10개 구 가격 분포<br>
상위 지역들은 높은 중앙값과 더불어 고가 아웃라이어가 다수 존재하는 넓은 가격 분포를 갖는다.

<img width="989" height="1190" alt="Image" src="https://github.com/user-attachments/assets/04c57672-fc91-4080-b8d6-dc0e264f4c87" /> <br>
구별 거래량 <br>
노원구가 가장 많은 거래량을 보이며, 주거 밀집 지역을 중심으로 거래 활동이 활발하다.

<img width="590" height="490" alt="Image" src="https://github.com/user-attachments/assets/1a0a6eda-4f2c-43c7-a8de-3f47e60e2534" /> <br>
강남여부에 따른 실거래가 분포<br>
강남권은 비강남권 대비 전반적으로 더 높은 가격대를 형성한다.

<img width="237" height="370" alt="Image" src="https://github.com/user-attachments/assets/43d8b0e7-d299-43d4-8606-6073170b7695" /> <br>
추가적으로 버스와 지하철역에 대한 결측치 EDA

<img width="315" height="540" alt="Image" src="https://github.com/user-attachments/assets/768ff147-583f-4198-ac08-e64eb2a28866" /> <br>
초,중,고등학교 데이터에 대한 결측치 EDA<br>
해당 좌표의 결측치의 동일한 학교 이름을 가진 중복데이터로 인해 drop 결정

### Data Processing
#### 3-1. 기본 전처리
- 제공된 학습 / 평가 데이터셋을 통합하여 공통 컬럼 기준으로 정리하였다.
- 문자열 타입 컬럼의 공백·이상 문자열을 정리하고, 필요 없는 식별자성 컬럼은 분석 대상에서 제외하였다.
- 결측치는 변수 특성에 따라 **0 대체, 삭제, 별도 카테고리 생성(UnKnown)** 방식으로 처리하였다.
- 
#### 3-2. Target 변환
- 원본 실거래가(target)는 우측으로 치우친 분포를 보였기 때문에  
  **`log1p(target)` 변환을 적용하여 분포를 정규분포에 가깝게 안정화**하였다.
- 모델 학습은 log1p(target)를 사용하고, 예측 결과는 제출 단계에서 다시 원래 스케일로 역변환하였다.

#### 3-3. 범주형 변수 인코딩
- 시군구, 법정동 등 범주형 변수는 LightGBM에서 활용할 수 있도록 **정수 인코딩(Label Encoding)** 하였다.
- 희소도가 높은 카테고리는 필요 시 상위 그룹으로 묶어 데이터 희소성을 완화하였다.

#### 3-4. 외부 데이터 결합
- 아파트 주변의 교통·교육 환경을 반영하기 위해 아래 외부 데이터를 추가로 결합하였다.
  - **버스정류장 / 지하철역 정보** : 단지별 인근 정류장·역 개수, 거리 기반 특성 생성
  - **학교 정보(초·중·고)** : 단지 반경 내 학교 수 및 유형별 카운트 생성
  - **금리 데이터** : 계약년월 기준으로 해당 시점의 기준금리를 매핑하여 경기·금리 환경 반영
- 모든 외부 데이터는 행정구역 또는 좌표/거리 기준으로 매칭하여 **단지 단위 Feature**로 통합하였다.

#### 3-5. 파생변수 로드맵
- 아파트 가격 구조를 잘 표현하기 위해 다음과 같은 파생변수를 생성하였다.
  - **지역 단위 평균 가격** : 구/동별 평균 실거래가, 평당가 등을 산출하여 지역 프리미엄을 반영
  - **면적 관련 변수** : 전용면적, 평수 변환, 면적 구간(bin) 등 규모에 따른 가격 차이 표현
  - **시간 변수** : 계약년월, 연·월, 경기/계절 효과를 반영할 수 있는 시계열 파생변수
  - **금리 매핑 변수** : 기준금리, 전월대비_금리증감 기반으로 만든 파생변수
  - **교통 접근성 파생변수** : 지하철, 버스 정류장 까지의 거리계산법으로 구현한 파생변수
  - **교육환경 파생변수** : 초,중,고등학교 까지의 거리계산법으로 구현한 파생변수
  - 이 외 EDA에서 유의미하다고 판단된 변수들을 추가 생성하고, 모델 성능과 Feature Importance를 기준으로 선별하였다.

#### 3-6. Feature Engineering
- 1. 구/동 단위 평균 가격 Feature
  - 동일한 면적·연식의 아파트라도 지역 프리미엄(구/동 수준) 에 따라 가격이 크게 달라질 것 이라고 생각했다.
  - 거래금액 / 전용면적으로 계산 후 지역 평균 적용, 지역 고정효과(가격 basline) 반영

- 2. 금리 Feature
  - 계약 시점의 금리 수준은 수요/공급 심리에 영향을 주며 가격에도 반영된다고 생각했다.
  - 외부 금리 데이터를 기준으로 '금리_증감률 = 금리(t) - 금리(t-1)' 식으로 계산하여 부동산 환경 반영

- 3. 교육환경 Feature
  - 초·중·고등학교 접근성은 가족 단위 수요에 큰 영향을 준다고 생각했다.
  - 학교 위치(경도, 위도)와 아파트 좌표를 비교하여 **Haversine 거리계산법** 을 통해 계산하였다.
  - 반경 500m 내 학교 개수를 카운트 하는게 목적

- 4. 버스 정류장 Feature
  - 버스 접근성이 높을수록 생활 편의성이 증가하며 가격에도 긍정적 영향이 있을거라고 판단
  - 버스 정류장 데이터의 좌표를 이용하여 아파트 좌표와 **Haversine 거리계산법** 계산
  - 버스정류장도 학교 위치와 같이 반경 500m 내 기준

- 5. 지하철역 Feature
  - 지하철역 또한 접근성이 높을수록 가격에 긍정적 영향이 있을거라고 판단
  - 지하철역 좌표와 아파트 좌표 간 거리 계산 **Haversine 거리계산법**
  - 지하철역도 반경 500m 내 지하철역 개수와, 필요시 가장 가까운 지하철역 거리에 대안.
  
- 6. 면적 Feature
  - 전용면적이 증가할수록 가격은 증가하지만, 구간별 민감도는 다르다고 판단
  - 따라서 전용면적을 평수로 변경하여 구간을 분리

- 7. 건물 노후도 Feature
  - 건축년도에 따라 가격이 달라지며, 노후도 구간에 따라 가격 민감도 차이가 존재한다고 판단
  - 노후도 또한 면적과 같이 '계약년 - 건축년도' 식으로 건물 Age 를 설정해 구간화

- 8. 강남여부 Feature
  - 강남권(강남·서초·송파·용산)은 명확한 프리미엄을 가진다고 판단
  - 구 단위로 나뉘어 df 에 따로 저장

## 4. Modeling

### Model descrition

- 본 프로젝트에서는 RandomForest 와 구조적 데이터에 강한 성능을 보이는 **LightGBM(Gradient Boosting)** 을 최종 모델후부로 선정하였다.
- 시간 상 RandomForest 를 돌려보지 못해 최종 채택 모델은 **LightGBM(Gradient Boosting)** 

### Modeling Process

- 모델링과정은 다음과 같이 진행하였다.
  
#### 1) 데이터 분리
- 전처리가 완료된 데이터를 기반으로 **Train / Validation** 데이터를 분리하였다.  
- 미래 데이터 예측 환경을 반영하기 위해 **시계열 기반 분리(계약년월 기준)** 을 적용하였다.

#### 2) Hyperparameter Tuning (Optuna)
- Optuna를 사용하여 LightGBM의 핵심 하이퍼파라미터를 탐색하였다.  
  (learning_rate, num_leaves, min_data_in_leaf, feature_fraction 등)  
- 평가 지표로는 RMSE를 사용하여 최적 조합을 도출하였다.

#### 3) Feature Selection
- Hyperparameter Tuning 을 기반으로 하여 Feature Importance를 산출하여  
  상위 변수들을 중심으로 **Top 60 Feature Set**을 구성하였다.  
- 중요도가 낮거나 중복된 특성은 제거하여 모델 단순화 및 성능 안정화를 유도하였다. <br>
<img width="989" height="1310" alt="Image" src="https://github.com/user-attachments/assets/a23d15c3-650d-4c0a-bff6-600f80dfb80f" />
  
#### 4) 최종 모델 학습
- 튜닝된 파라미터와 선정된 Top Feature Set을 사용해 최종 LightGBM 모델을 학습하였다.
- Target은 log1p 변환으로 학습 후, 예측 시 expm1을 적용하여 원래 스케일로 복원하였다.

#### 5) Test 예측 & 제출 파일 생성
- 학습된 모델로 Test 데이터를 예측하고 제출 형식에 맞게 `.csv` 파일을 생성하였다.

## 5. Result

### Leader Board
모델 튜닝과 Feature Engineering을 통해 성능을 지속적으로 개선하였으며,  
최종적으로 아래와 같은 점수를 기록하였다.

<img width="985" height="418" alt="Image" src="https://github.com/user-attachments/assets/1d653cba-8b3b-4660-b7cb-42c1c9f995ed" /> <br>

### Presentation

- [발표자료](https://github.com/user-attachments/files/24068715/AI.20._ML._._1.pptx)

## etc
Leader Board 에 관한 issue 가 하나 있었는데 바로 'GPU 서버 사용시간' 으로 인해 중간 성능의 RMSE 를 가진 Test Model 만 반영된 걸 볼 수 있었다. <br>
Leader Board 에 반영된 Model 의 RMSE 가 Local 환경에서 출력됐을 때에는 'RMSE: 8639.4712' 의 값을 가지고 있었는데 최종 모델 RMSE 값을 통해서 Leader Board 에 올렸을 때 얼만큼의 성능상승이 일어났는지 확인해보지 못한 점이 아쉬웠다.

<img width="498" height="192" alt="Image" src="https://github.com/user-attachments/assets/6c55fb39-9c09-479b-ac15-46ad6d86482b" />

### Meeting Log

- Utilize real-time zoom meetings <br>
<img width="346" height="309" alt="Image" src="https://github.com/user-attachments/assets/9c40c48d-70fe-4131-b79a-717f1ffbe8df" />

### Reference

- [LGBM 모델의 전반적인 개념과 파라미터 인지](https://for-my-wealthy-life.tistory.com/24)
- [LGBM 하이퍼파라미터튜닝 옵션](https://d22pinsights.tistory.com/27)
- [아파트 실거래가 예측 경진대회 해석](https://here-lives-mummy.tistory.com/22)
- [초,중,고등학교 Data](https://www.data.go.kr/)
- [금리 Data](https://www.bok.or.kr/portal/singl/baseRate/progress.do?dataSeCd=01&menuNo=200656)
