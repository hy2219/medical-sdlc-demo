# 논문 추천 – 2026-10-26

> 이 추천은 자동 선별 결과이며, 반드시 의사의 검토가 필요합니다.

- **연구 날짜**: 2026-10-26 (Asia/Seoul 기준 어제)
- **실제 검색 기간**: 2026-09-27 ~ 2026-10-26 (당일 0건 → 7일 4건(신규 적합 2편) → 30일 15건으로 확장)
- **검색어**: `chest radiograph`

## 코호트 요약 (집계값만)

- 흉부 X선 272건, 5개 기관, 전 건 합성 영상
- 성별: 남 136 / 여 136, 연령 9~87세
- 촬영 자세: PA 184 / AP 88
- 'No Finding' 145건(약 53%); 나머지는 Infiltration, Atelectasis, Effusion, Nodule 등 다중 라벨 소견

## 축

`판독자-AI 상호작용` · `기관 간 일반화`

## 선정 논문

### 1. From dusk till dawn? — Night shift-induced fatigue, diagnostic performance, and AI assistance in chest radiography
[OpenAlex](https://doi.org/10.1007/s00330-026-12969-8) · European Radiology · 축: 판독자-AI 상호작용

- **왜 관련 있는가**: 전공의 10명의 전향적 판독자 연구로, 피로군에서 κ가 0.71→0.61로 감소했고 AI 보조는 유의한 개선이 없었습니다. 임상의가 바로 활용할 수 있는 안전성 결과입니다.
- **우리 데이터의 근거**: 272건, 'No Finding' 약 53%와 다양한 이상 소견 구성이 판독 세트 설계에 활용 가능합니다.
- **알 수 없는 것**: 판독자·시간·시선 정보가 없어 피로나 AI 효과를 확인할 수 없습니다.

### 2. Human oversight of erroneous clinical AI and decision support: a systematic review and meta-analysis
[OpenAlex](https://doi.org/10.1038/s41746-026-03408-5) · npj Digital Medicine · 축: 판독자-AI 상호작용

- **왜 관련 있는가**: 오류 AI 조언에 대한 임상의 정답률이 올바른 조언일 때보다 크게 낮았습니다(통합 OR 10.19, 95% CI 7.43–13.98).
- **우리 데이터의 근거**: 정상/이상, 단일/다중 라벨, AP/PA 혼재 구성이 오류 감지 평가 세트 설계의 재료가 됩니다.
- **알 수 없는 것**: 흉부 X선 특화 결과가 아니며, 우리 데이터에는 AI 출력·판독자 반응이 없습니다.

### 3. An open vision-language model for diverse medical applications (MedGemma)
[OpenAlex](https://doi.org/10.1038/s41591-026-04626-w) · Nature Medicine · 축: 기관 간 일반화

- **왜 관련 있는가**: 분포 외 흉부 X선 소견 분류에서 기본 모델 대비 15.5~18.1% 향상을 보고했습니다. 임상 판독 결과는 없는 방법론 논문이라 우선순위는 낮습니다.
- **우리 데이터의 근거**: 5개 기관, 272건, 다중 라벨 소견 구성의 소규모 외부 점검에 적합합니다.
- **알 수 없는 것**: 희귀 소견 표본이 한 자릿수라 소견별 성능 검증이 어렵고, 임상 판독자 비교가 없습니다.

## 제외

- 이미 추천됨: 신생아 기흉 자동화 편향, 신생아 연속학습, 골다공증 선별, 성능 불확실성 신뢰구간, LV 기능부전 선별
- 관련성 낮음: MDR-TB 치료 결과 예측(결핵 코호트 정보 없음), 텍스트 유도 영상 합성, ICU 폐렴(영상 없음), VERIDAH(척추 라벨링), 임상예측모델 코드 공유 리뷰, CT 비전-언어 모델, 디지털 트윈 의학교육

## 참고

보고된 결과는 모두 논문 저자의 주장이며, 임상 적용 전 의사의 검토가 필요합니다.
