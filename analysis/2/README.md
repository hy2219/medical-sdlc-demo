# 분석: 흉부 X선 기반 기회적 골다공증 선별 AI — 코호트 구성 비교

- 이슈: #2 · 논문: [npj Digital Medicine 논문 초록](https://doi.org/10.1038/s41746-026-03333-7)
- 논문 근거는 DOI의 초록과 [`paper.json`](../../recommended/2026-10-17/ai-osteoporosis-screening-chest-radiographs/paper.json)뿐이며, 본문은 확인하지 않았습니다.
- 우리 수치는 `llm.hospital` 마스킹 뷰의 집계입니다. 합성 데이터이며, 결과는 가설 생성 수준의 코호트 구성 비교입니다.

## 결론

**판정: 불충분.** 논문 초록의 모델 성능을 우리 데이터에서 재현할 수 없습니다. 우리 코호트에 짝지어진 DXA/BMD 기준 라벨이 없어 골다공증 또는 감소된 골밀도 예측 성능과 신뢰구간을 계산하지 않았습니다. 아래는 외부 검증이 아닌 코호트 구성 비교입니다.

## 논문 초록과 우리 코호트 비교

| 항목 | 논문 초록 ([출처](https://doi.org/10.1038/s41746-026-03333-7)) | 우리 코호트 (`llm.hospital`) | 확인 상태와 의미 |
|---|---|---|---|
| 규모 | 개발: CXR–DXA 검사 46,478건, 환자 26,757명(2016–2022). 외부 코호트: SNUH 6,391건, HPC 24,132건, YSMC 122,535건. | 흉부 X선 272건, 고유 환자 153명, 5개 기관. 전부 합성(272/272). | 두 표본 규모는 확인 가능하지만 우리 코호트는 훨씬 작고 합성입니다. 우리 수치: Q1. |
| 영상 종류 | 흉부 X선(CXR)과 DXA 검사 쌍으로 개발; 외부 검증도 세 코호트에서 시행했다고 보고. | 흉부 X선 272건. 짝지어진 DXA/BMD 결과 없음. | 우리 영상과 합성 여부는 Q1로 확인. 기준 라벨 부재로 성능 검증 불가. |
| 촬영 자세 | 초록에 미보고(본문 미확인). | PA 184/272건(67.6%), AP 88/272건(32.4%). | 우리 분포만 확인 가능(Q6); 논문과 자세 구성 비교는 불가. |
| 연령·성별 | 초록에 미보고(본문 미확인). | 나이 9–87세. F 136/272건(72명), M 136/272건(81명). | 우리 분포는 Q1·Q6으로 확인 가능; 논문 연령·성별과 비교 불가. |
| 기관 | 개발 자료는 3차 의뢰 병원. 외부 검증은 SNUH, HPC, YSMC(각 건수는 규모 행 참조). | INST01–INST05, 각각 62, 56, 54, 48, 52건(총 272건). | 두 연구의 기관 구성이 다르며, 기관 간 성능 비교를 뜻하지 않음(Q4). |
| 골다공증/BMD 기준 라벨 | CXR–DXA 쌍을 사용했고 골다공증 및 감소된 BMD 예측을 보고. 초록에 세부 DXA 기준은 미보고(본문 미확인). | DXA/BMD 기준 라벨 없음. | 우리 코호트의 성능과 신뢰구간 계산 불가. |

## 우리 코호트 집계

모든 건수 분모는 272건, 전체 고유 환자 분모는 153명입니다. 하위군의 고유 환자 수는 해당 하위군에서 한 번 이상 촬영된 환자 수이며, 검사 시점에 따라 연령 구간 간 중복될 수 있습니다.

### 연령대 (Q2)

| 연령대 | 검사 건수 | 환자 수 |
|---|---:|---:|
| <18 | 9 | 5 |
| 18–39 | 53 | 35 |
| 40–49 | 48 | 32 |
| 50–64 | 105 | 59 |
| 65+ | 57 | 35 |

### 보조 하위군 (Q5)

| 하위군 | 검사 건수 (전체 272건 대비) | 환자 수 |
|---|---:|---:|
| 50세 이상 | 162 (59.6%) | 92 |
| 65세 이상 | 57 (21.0%) | 35 |
| 50세 이상 여성 | 98 (36.0%) | 52 |

### 성별·촬영 자세 및 기관 (성별·자세: Q6, 기관: Q4)

| 구분 | 검사 건수 (전체 272건 대비) | 환자 수 (전체 153명 대비) |
|---|---:|---:|
| F | 136 (50.0%) | 72 |
| M | 136 (50.0%) | 81 |
| PA | 184 (67.6%) | 130 |
| AP | 88 (32.4%) | 56 |

| 기관 | 검사 건수 (전체 272건 대비) | 환자 수 |
|---|---:|---:|
| INST01 | 62 (22.8%) | 53 |
| INST02 | 56 (20.6%) | 48 |
| INST03 | 54 (19.9%) | 48 |
| INST04 | 48 (17.6%) | 41 |
| INST05 | 52 (19.1%) | 50 |

성별 구분은 상호 배타적이지만 연령대·촬영 자세·기관별 고유 환자 수는 환자의 여러 검사로 범주 간 중복될 수 있습니다. 성별과 자세를 교차한 Q3는 교차 집계의 근거이며, 아래 표와 차트는 각각의 단독 분포를 나타냅니다.

## 확인 가능 / 미확인 / 계산 불가

| 상태 | 내용 |
|---|---|
| 확인 가능 | 우리 코호트의 연령·성별·자세·기관 구성과 하위군 크기(Q1–Q6) |
| 미확인 | 논문 초록에 없는 연령·성별·자세 구성 및 세부 DXA 기준(본문 미확인) |
| 계산 불가 | DXA/BMD 라벨 부재로 우리 코호트의 골다공증·감소된 BMD 예측 성능 및 신뢰구간 |

## 쿼리 및 집계 근거

아래 SQL은 모두 `llm.hospital` 마스킹 뷰에서 실행할 수 있습니다. `COUNT(DISTINCT patient_key)`는 각 집계 범위에서 한 번 이상 검사한 고유 환자 수를 셉니다. Q1–Q6는 위 표와 `analysis.json`의 우리 코호트 수치 근거입니다.

### Q1 — 전체 규모, 나이 범위, 기관 수, 합성 영상 수

```sql
SELECT
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients,
    MIN(age) AS min_age,
    MAX(age) AS max_age,
    COUNT(DISTINCT institution_code) AS institutions,
    SUM(is_synthetic::int) AS synthetic_examinations
FROM llm.hospital;
```

### Q2 — 연령대별 검사 건수와 고유 환자 수

```sql
WITH age_bands AS (
    SELECT
        CASE
            WHEN age < 18 THEN '<18'
            WHEN age < 40 THEN '18–39'
            WHEN age < 50 THEN '40–49'
            WHEN age < 65 THEN '50–64'
            ELSE '65+'
        END AS age_band,
        CASE
            WHEN age < 18 THEN 1
            WHEN age < 40 THEN 2
            WHEN age < 50 THEN 3
            WHEN age < 65 THEN 4
            ELSE 5
        END AS sort_order,
        patient_key
    FROM llm.hospital
)
SELECT
    age_band,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM age_bands
GROUP BY age_band, sort_order
ORDER BY sort_order;
```

### Q3 — 성별 × 촬영 자세 교차 집계

```sql
SELECT
    sex,
    view_position,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
GROUP BY sex, view_position
ORDER BY sex, view_position;
```

### Q4 — 기관별 검사 건수와 고유 환자 수

```sql
SELECT
    institution_code,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
GROUP BY institution_code
ORDER BY institution_code;
```

### Q5 — 보조 하위군별 검사 건수와 고유 환자 수

```sql
SELECT
    'age >= 50' AS subgroup,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
WHERE age >= 50
UNION ALL
SELECT
    'age >= 65' AS subgroup,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
WHERE age >= 65
UNION ALL
SELECT
    'age >= 50 and sex = F' AS subgroup,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
WHERE age >= 50 AND sex = 'F';
```

### Q6 — 성별 및 촬영 자세 각각의 분포

```sql
SELECT
    sex,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
GROUP BY sex
ORDER BY sex;
```

```sql
SELECT
    view_position,
    COUNT(*) AS examinations,
    COUNT(DISTINCT patient_key) AS patients
FROM llm.hospital
GROUP BY view_position
ORDER BY view_position;
```

## 논문 초록의 결과 — 우리 코호트 결과와 구분

초록은 개발에 CXR–DXA 검사 46,478건(환자 26,757명, 2016–2022)을 사용했고, SNUH 외부 코호트에서 골다공증 및 감소된 BMD 모두 AUROC 0.88(95% CI 0.87–0.89)을 보고했습니다. 골다공증 탐지 AUROC는 HPC에서 0.93(95% CI 0.92–0.93), YSMC에서 0.92(95% CI 0.92–0.92)였습니다. 이는 **논문 초록의 결과**이며 우리 코호트에서 얻은 성능이 아닙니다.

초록의 시뮬레이션에서는 DXA 이용을 약 50% 줄이면서 골다공증 사례의 98–99%, **감소된 BMD 사례의 80–90% 탐지 유지**를 보고했습니다([동일 초록 출처](https://doi.org/10.1038/s41746-026-03333-7)). 이 시뮬레이션 수치도 논문 결과이며, 우리 코호트에서는 DXA/BMD 라벨이 없어 해당 탐지율을 측정하거나 검증하지 않았습니다.

## 추론

이 분석으로 확인할 수 있는 것은 우리 합성 코호트의 구성뿐입니다. 기관과 촬영 자세가 다양하다는 이유만으로 외부 검증이나 일반화 성능을 주장할 수 없습니다. 성능 평가를 검토하려면 CXR과 짝지어진 DXA/BMD 기준 라벨이 필요합니다.

## Limitations

- DXA/BMD 라벨 없음 → 우리 코호트의 AUROC·신뢰구간 미계산.
- 전 건 합성 영상(272/272); 272건/153명으로 논문보다 훨씬 작고, 하위군은 더 작습니다.
- 논문 근거는 초록과 `paper.json`에 한정하며 본문은 확인하지 않았습니다.
- 검사 단위 집계이며 환자 내 상관이 있습니다. 연령·자세·기관별 고유 환자 수는 각 범주 간 중복될 수 있습니다.
- 본 결과는 가설 생성 수준의 코호트 구성 비교이며 외부 검증이 아닙니다. 임상 사용 전 의사의 검토가 필요합니다.
