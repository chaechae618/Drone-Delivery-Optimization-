## 🩸 AI-Based Blood Supply Demand Analysis & Drone Delivery Optimization  
📅 Jan. 2024 – Jun. 2024  
🎯 *Designing an AI-powered blood logistics system and optimal drone station placement strategy in Seoul*

---

### 🧩 Overview  
- 국내 혈액 보유량 감소 및 수급 불균형 해소를 위해,  
  **AI 기반 수요 예측 + 드론 배송 시뮬레이션**을 결합한 **스테이션 최적 입지 선정 및 물류 모델링 프로젝트**  
- 실제 병의원 위치와 혈액 수요 데이터를 기반으로 **서울시 단위 의료 드론 배송 시나리오** 설계  

---

### 📊 Data Summary

- **병의원 위치 정보**: 21,359건 (기관명, 주소, 위도/경도 등)  
- **병원별 혈액 청구 이력**: 937,409건 → 병합 후 156,469건 (460개 기관)  
- **최종 분석 대상**: 2023년 기준 30,745건, 366개 기관 (비정상 수요 제외)  

---

### 🔎 Exploratory Data Analysis (EDA)

#### 📈 1) 연도별 혈액 수요 추이  
- 2020~2023: 비교적 안정적  
- **2024년 수요 급감**(969,053팩) → 대표 연도 2023년으로 분석 기준 설정

#### 🗺 2) 자치구별 평균 출고량 분포  
- 서대문구, 송파구, 종로구에서 **수요 집중 현상**  
- 의료 인프라 밀집 지역의 **공간적 수요 편중 확인**

#### 📍 3) 혈액원–병원 평균 거리 분석  
- 서울 내 3개 혈액원(동부, 남부, 중앙)의 **관할 병원 평균 거리 평가**  
- 일부 병원이 혈액원과 **10km 이상 거리**에 위치 → 드론 배송 반경 고려 시 **입지 재배치 필요성 대두**

---

### 🧠 Key Insights

- **드론 배송이 어려운 사각지대** 존재 → 스테이션 추가 필요  
- **DJI FlyCart30**: 고수요 클러스터에서 **적재 한계 도달**  
- **AIRBILITY AB-0**: 시뮬레이션 대부분에서 **안정적 운용 가능**  
- 적재 및 충전 시간 반영 시 드론 운용 가용성이 실제와 크게 달라짐

---

### 🛠 Modeling & Optimization

- **Data & Analysis**: `Python`, `Pandas`, `NumPy`  
- **Spatial Optimization**: `KMeans`, `KDE`, `MCLP`, `PuLP`, `CBC Solver`  
- **Simulation**: 드론 성능 모델링 + 스케줄링 알고리즘  

---

### 🧪 System Design Workflow

#### 🚩 Step 1: 병원 클러스터링 및 후보지 도출  
- KMeans로 **의료 수요 권역화**  
- KDE 상위 10% 밀집 영역 기반 + MCLP로 **최적 스테이션 위치 도출**

#### 🚁 Step 2: 드론 성능 모델링  
- **AIRBILITY AB-0**, **DJI FlyCart30**:  
  - 최대 적재량, 속도, 비행거리 기반 성능 정의  
  - 배송 반경, 비행 시간 제약 조건 포함

#### 📦 Step 3: 드론 배송 시뮬레이션  
- 병원 수요 + 위치 기반 **하루 단위 배송 스케줄링 알고리즘** 구현  
- 드론 **충전/적재 시간** 반영 → **최소 필요 기체 수 계산**

---

### 📌 Key Results

- 📍 **입지 정합성**: KDE 기반 수요 밀집도와 MCLP 결과 **85% 이상 일치**  
- 📊 **Coverage Performance**: 전체 격자의 87.49%, 수요 가중치 커버리지 84.92% 달성  
- ✈️ **드론 총 이동 거리 59.03% 감소** → 물류 효율성 향상 정량 입증  

---

### 🧾 Deliverables

- 🗂 공간 클러스터링 기반 입지 분석 결과 리포트  
- 🛰 드론 배송 시뮬레이션 결과 및 시나리오별 최적 기체 수 계산  
- 🧠 정책 제안: 혈액원 입지 재편, 지역 기반 수요 대응 전략 수립  

---

### 💬 Technologies Used  
- `Python`, `Pandas`, `NumPy`  
- `KMeans`, `KDE`, `MCLP`, `PuLP`, `CBC`  
- `Matplotlib`, `Seaborn` (시각화)  

---
