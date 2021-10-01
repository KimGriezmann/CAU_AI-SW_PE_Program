# **CAU AI/SW PE program**
------------------------------------


<br/>
<br/>

## **1. 프로젝트 소개**
------------------------------------
### **1-(1) PE 프로그램**
- 중앙대학교 SW 복수전공 학부연구생 (시각영상미디어연구실)


<br/>


### **1-(2) 프로젝트 주제** 
- 다층 퍼셉트론(MLP)과 순환신경망(RNN) 기반 한국 프로야구 결과 예측 모델 개발


<br/>


## **2. 프로젝트 내용**
-------------------------------------------------------------
### **2-(1) 문제 정의**

- 어떤 타구가 좋은 타구일까?
- 타자 성적 예측 모형 개발을 통한 잔여 기간 KBO 타자 OPS 예측 (2021.09.15 ~ 2021.10.08) 

<br/>


### **2-(2) 분석 목표**

![분석목표](https://user-images.githubusercontent.com/80115212/135224326-42d98241-5498-4289-81e8-d7fc894cb85e.PNG)

- 최근 n일간의 성적으로 이후 24일간의 성적을 예측   
- 이때, home/away(홈/원정)로 나누어 각각 예측하여 가중 평균

<br/>


### **2-(3) 데이터 수집 및 전처리**
- 스탯티즈에서 타석 상황 데이터 수집 
- 타구 트래킹(HTS) 데이터와 병합
- 오류 검출 및 새로운 컬럼 정의

<br/>


### **2-(4) 3가지의 배럴(Barrel) 정의**
- Power Barrel
    * 순장타율(장타율 - 타율)을 기준으로 탐색
    * 순장타율 0.5이상 Power Barrel로 정의
![power_barrel](https://user-images.githubusercontent.com/80115212/135222920-97f03021-248f-4220-8fbf-b42a7bf6559a.PNG)


- Contact Barrel
    * 단타율(안타+직선타) 기준으로 탐색
    * 단타율 0.7이상 Contact Barrel로 정의
![contact_barrel](https://user-images.githubusercontent.com/80115212/135222960-22e07502-95a9-4c69-b3b9-2ac9f64f59c4.PNG)


- Clutch Barrel
    * WPa(승리 기여도) 기준으로 탐색
    * WPa 0.0815이상 Clutch Barrel로 정의
![clutch_barrel](https://user-images.githubusercontent.com/80115212/135222980-c26ed82a-72a4-415b-acbb-0a1ed2fa0329.PNG)


cf. 타구속도와 발사각도를 범주화하여 탐색

<br/>


### **2-(5) OPS 예측**
- 세이버메트릭스에 기반한 17개의 지표 계산 
- 선수 수준(4년간의 평균) 지표 계산
- ML
    * Extra Trees
    * Random Forest
    * LGBM
- DL
    * Multi Layer Perceptron


- Hyper Parameter 탐색


cf. RMSE를 통해 모델 성능 비교

<br/>


## **3. 분석 결과**
------------------------------------
### **3-(1) 좋은 타구(Barrel) 정의**
![barrel_result](https://user-images.githubusercontent.com/80115212/135224883-ebf0b7c1-9566-45e1-8366-57e8d1c08eb4.PNG)


### **3-(2) OPS 예측**
![result](https://user-images.githubusercontent.com/80115212/135225398-c957fca1-b9b0-4917-8eda-9d5a67c4cdd7.PNG)
