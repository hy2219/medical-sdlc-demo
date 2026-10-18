# 분석: 흉부 X선 기반 기회적 골다공증 선별 AI — 코호트 구성 비교

- 이슈: #2 · 논문: https://doi.org/10.1038/s41746-026-03333-7 (npj Digital Medicine, 2026)
- 모든 수치는 `llm.hospital` 마스킹 뷰 집계이며 환자 단위 행은 포함하지 않습니다. 합성 데이터이며 가설 생성 수준입니다.

## 논문이 보고한 것 (초록만, 출처: 위 DOI)
- 개발: CXR–DXA 쌍 46,478건, 환자 26,757명, 2016–2022, ResNet+MAE 사전학습.
- 외부 검증: SNUH 6,391건(AUROC 0.88), HPC 24,132건(0.93), YSMC 122,535건(0.92).
- 시뮬레이션: DXA 약 50% 감소, 골다공증 98–99% 검출.
- 초록에 없음(본문 미확인): 연령·성별·촬영 자세 구성, DXA 세부 기준, 자세별 성능.

## 우리 데이터가 보여주는 것
| 항목 | 값 | 쿼리 |
|---|---|---|
| 검사 건수 / 고유 환자 / 기관 / 합성 | 272 / 153 / 5 / 272 | Q1 |
| 나이 범위 | 9–87 | Q1 |

연령대(건수/환자, 분모 272건·153명; 환자는 여러 구간에 중복 가능):

| 연령대 | 건수 | 환자 |
|---|---|---|
| <18 | 9 | 5 |
| 18–39 | 53 | 35 |
| 40–49 | 48 | 32 |
| 50–64 | 105 | 59 |
| 65+ | 57 | 35 |

| 하위군 | 건수 | 환자 |
|---|---|---|
| 50세 이상 | 162 (59.6%) | 92 |
| 65세 이상 | 57 (21.0%) | 35 |
| 50세 이상 여성 | 98 (36.0%) | 52 |

성별×자세 (건수/환자): F-AP 39/23, F-PA 97/62, M-AP 49/33, M-PA 87/68. 성별 합계 F 136/72, M 136/81. 자세 합계 PA 184/130, AP 88/56.

기관 (건수/환자): INST01 62/53, INST02 56/48, INST03 54/48, INST04 48/41, INST05 52/50.

## 확인 가능 / 미확인 / 불가
| 구분 | 내용 |
|---|---|
| 확인 가능 | 우리 코호트의 연령·성별·자세·기관 구성, 하위군 크기 |
| 미확인 | 논문 초록에 없는 구성·세부 정의(본문 미확인) |
| 계산 불가 | 골다공증 예측 성능·신뢰구간 (DXA/BMD 라벨 없음) |

## 쿼리 (모두 `llm.hospital`)
- Q1: `select count(*), count(distinct patient_key), min(age), max(age), count(distinct institution_code), sum(is_synthetic::int) from llm.hospital`
- Q2: `select <연령구간 case when age<18/<40/<50/<65/else>, count(*), count(distinct patient_key) from llm.hospital group by 1`
- Q3: `select sex, view_position, count(*), count(distinct patient_key) from llm.hospital group by 1,2`
- Q4: `select institution_code, count(*), count(distinct patient_key) from llm.hospital group by 1`
- Q5: `... from llm.hospital where age>=65` / `where age>=50` / `where age>=50 and sex='F'`
- Q6: 성별 및 view_position 단독 group by.

## 추론 (우리 해석)
논문의 성능 주장은 이 데이터로 검증할 수 없고, 이 비교는 외부 검증이 아닙니다. 검증하려면 CXR과 짝지어진 DXA 라벨이 필요합니다.

## Limitations
- DXA/BMD 라벨 없음 → AUROC·CI 미계산.
- 전 건 합성 영상, 272건/153명으로 논문 대비 매우 작음; 하위군은 더 작음.
- 논문 근거는 초록과 `paper.json`에 한정.
- 검사 단위 집계로 환자 내 상관이 있으며, 환자 수는 구간 간 중복됨.
- 임상 사용 전 의사의 검토가 필요합니다.
