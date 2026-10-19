# 논문 추천 – 2026-10-18

> 이 추천은 자동 선별 결과이며, 반드시 의사의 검토가 필요합니다.

- **연구 날짜**: 2026-10-18 (Asia/Seoul 기준 어제)
- **실제 검색 기간**: 2026-09-19 ~ 2026-10-18 (당일 → 7일 → 30일로 확장; 3편 이상이 될 때까지)
- **검색어**: `chest X-ray` (당일·7일 창에서는 `chest radiograph deep learning`도 사용)

## 코호트 요약 (집계값만)

- 흉부 X선 272건, 5개 기관, 장비 9종, 5개 진료과, 전 건 합성 영상
- 성별: 남 136 / 여 136, 연령 9~87세
- 촬영 자세: PA 184 / AP 88
- 'No Finding' 145건(약 53%), 다중 라벨 50건(약 18%); 이상 소견은 Infiltration, Atelectasis, Nodule, Fibrosis, Effusion 등 소수 건씩

## 축

`기관 간 일반화` · `라벨 구조` · `임상의-AI 협업`

## 선정 논문

### 1. Learning to Defer with Guidance on Real World Medical Data
[arXiv](http://arxiv.org/abs/2609.26384v1) · MICCAI · 축: 임상의-AI 협업, 라벨 구조

- **왜 관련 있는가**: 다수 판독자 흉부 X선 데이터(Collab-CXR, VinDr-CXR, CheXpert)에서 AI 단독·의사 단독·AI 보조 기준선과 비교한 가장 임상 판독 흐름에 가까운 연구입니다.
- **우리 데이터의 근거**: 'No Finding' 53%, 다중 라벨 18%의 혼합 구성.
- **알 수 없는 것**: 영상당 판독 기록이 하나뿐이라 판독자 불일치와 업무량 효과는 확인 불가.

### 2. Anatomy-Structured Hierarchical MIL for Weakly-Supervised Thoracic Disease Detection in Chest X-rays
[arXiv](http://arxiv.org/abs/2609.33520v1) · MICCAI · 축: 기관 간 일반화, 라벨 구조

- **왜 관련 있는가**: 영상 수준 라벨만으로 병변 위치를 추정하는 방법으로, CXR8과 MIMIC-CXR 교차 도메인 평가를 포함합니다(방법론 논문, 임상 판독 연구 없음).
- **우리 데이터의 근거**: CXR8 계열 영상 수준 라벨, 5개 기관·9개 장비.
- **알 수 없는 것**: 병변 위치 정답이 없어 국소화 성능 검증 불가; 소견별 표본이 매우 적음.

### 3. Beyond Explanation: Debugging Medical Imaging Models via Concept Intervention
[arXiv](http://arxiv.org/abs/2610.09031v1) · MICCAI · 축: 기관 간 일반화, 임상의-AI 협업

- **왜 관련 있는가**: 도메인 전문가와 함께 허위 상관 개념을 가려내는 모델 점검 방법입니다(방법론 논문).
- **우리 데이터의 근거**: 기관·장비·촬영 자세(PA/AP)가 섞여 있어 허위 상관 점검 동기가 있음.
- **알 수 없는 것**: 우리 코호트의 실제 허위 상관 존재 여부와 개입의 임상적 효과.

## 제외한 검색 결과

- 이미 추천된 논문(골다공증 선별, 신뢰구간, 파운데이션 모델 연구 품질)
- 우리 데이터와 무관: 신생아 ETT 모델, 척추 라벨링, CT 비전-언어 모델, 의학 교육·디지털 트윈 고찰, 유방 초음파, ICU 사망 예측(EHR 필요), 적대적 공격 탐지, 연합학습 프라이버시, 폐동맥 고혈압 감별 등
- 당일(10-18) 창은 결과 0건, 7일 창은 3건이었으나 모두 부적합

환자 단위 값은 포함하지 않았습니다. 모든 영상은 합성 데이터입니다.
