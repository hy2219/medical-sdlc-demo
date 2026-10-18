# 논문 추천 – 2026-10-17

> 이 추천은 자동 선별 결과이며, 반드시 의사의 검토가 필요합니다.

- **연구 날짜**: 2026-10-17 (Asia/Seoul 기준 어제)
- **실제 검색 기간**: 2026-09-18 ~ 2026-10-17 (당일 → 7일 → 30일로 확장; 3편 이상이 될 때까지)
- **검색어**: `chest radiograph deep learning`

## 코호트 요약 (집계값만)

- 흉부 X선 272건, 환자 153명, 5개 기관, 장비 9종, 전 건 합성 영상
- 성별: 남 136 / 여 136, 연령 9~87세
- 촬영 자세: PA 184 / AP 88
- 'No Finding' 145건(약 53%); 이상 소견은 Infiltration, Atelectasis, Nodule, Fibrosis, Effusion 등 소수 건씩

## 선정 논문

### 1. Artificial intelligence for opportunistic osteoporosis screening on chest radiographs
[링크](https://doi.org/10.1038/s41746-026-03333-7) · npj Digital Medicine

- **왜 관련 있는가**: 흉부 X선 기반 AI를 세 개 외부 코호트에서 검증한 임상 연구(AUROC 0.88~0.93)로, 가장 임상적으로 실행 가능합니다.
- **우리 데이터의 근거**: 5개 기관, PA/AP 혼재, 넓은 연령대.
- **알 수 없는 것**: 골밀도(DXA) 기준 표준이 없고 영상이 합성이므로 골다공증 예측은 검증 불가.

### 2. Performance uncertainty in medical image analysis: A large-scale investigation of confidence intervals
[링크](https://doi.org/10.1016/j.media.2026.104349) · Medical Image Analysis

- **왜 관련 있는가**: 소견별 표본이 작은 우리 코호트에서 성능 지표의 CI를 해석하는 기준을 제공합니다(방법론 논문).
- **우리 데이터의 근거**: 272건 중 이상 소견 라벨은 건수가 매우 적음(예: Nodule 7건).
- **알 수 없는 것**: 특정 질환에 대한 임상적 결과는 다루지 않음.

### 3. Physician involvement and research quality in chest X-ray foundation models
[링크](https://doi.org/10.1038/s41746-026-03205-0) · npj Digital Medicine

- **왜 관련 있는가**: 흉부 X선 파운데이션 모델의 보고 품질과 공정성 논의 현황을 정리한 고찰입니다.
- **우리 데이터의 근거**: 성별 균형, 넓은 연령대, 다기관·다자세 구성이 하위군 점검에 활용 가능.
- **알 수 없는 것**: 모델 성능 자체는 검증하지 못함.

## 제외한 검색 결과

VERIDAH(척추 라벨링), 신생아 기관내관 연속학습, 코드 공유 리뷰, CT 비전-언어 모델, 디지털 트윈 교육, 유방 초음파 출처 위험, 광자계수 CT 폐 파라미터는 흉부 X선 코호트와 직접 맞물리지 않아 제외했습니다.
