# 🚌 서울시 유동인구 및 버스 노선 데이터 분석 (Big Data EDA)

서울시의 1.6GB에 달하는 월별 유동인구 이동 데이터와 버스 정류장 승하차 승객 데이터를 병합 정제하고, 통계 분석(피어슨 상관관계) 및 지리 시각화를 통해 자치구별 대중교통 인프라의 공급 불균형 지대를 도출한 빅데이터 분석 프로젝트입니다.

본 프로젝트는 **AI+X 기초 1차 프로젝트**로 수행되었습니다.

---

## 📂 프로젝트 구조

* **[Untitled.ipynb](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/두 번째/Untitled.ipynb)**: 대용량 데이터 로드 및 청크 병합, 상관분석 시각화 통합 노트북
* **[correlation_bus_stop_vs_population.png](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/두 번째/correlation_bus_stop_vs_population.png)**: 자치구별 버스 정류소 수 대비 유동인구의 상관 분석 산점도
* **[floating_population_vs_bus_stops_with_labels.png](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/두 번째/floating_population_vs_bus_stops_with_labels.png)**: 자치구별 매핑 라벨 포함 분포 차트
* **[df_seoul_people.csv](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/두 번째/df_seoul_people.csv)** / **[SEOUL_BUS_STOP.csv](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/두 번째/SEOUL_BUS_STOP.csv)**: 행정동/정류소별 정형 매핑 테이블

---

## ✨ 분석 프로세스 및 의의

1. **대용량 시계열 데이터 가공 (1.6GB+)**
   * 단일 기가바이트 파일(`seoul_moving_month_4.csv`)을 효율적으로 연산하기 위해 판다스 데이터 타입을 다운캐스팅(Float64 $\to$ Float32 등)하고 청크(Chunk) 단위 메모리 로드 기법 적용.
2. **인프라 매핑 및 피어슨 상관분석**
   * 행정 구역 코드(행정동 단위) 기준으로 승하차 통계와 인구 이동량 매핑.
   * 버스 정류장 수와 실제 유동인구 밀도 간의 상관도(Pearson r) 분석을 수행하여 대중교통 인프라의 과소/과대 공급 자치구 정밀 식별.
3. **인프라 최적화 의사결정 지원**
   * 상업 밀집 구역 및 주거 외곽 지대의 이동량 패턴 대비 배차 편향성을 파악하여 데이터에 기반한 노선 보정 제안 수립.

---

## 🛠️ 기술 스택

* **Language**: `Python`
* **Data Engineering**: `Pandas (Chunking & Optimization)`, `Numpy`
* **Visualization & Statistics**: `Seaborn`, `Matplotlib`, `SciPy (Correlation stats)`
