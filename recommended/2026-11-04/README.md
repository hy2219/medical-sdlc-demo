# 2026-11-04 논문 추천

- 연구 날짜: 2026-11-04 (한국 기준 어제)
- 검색 창: 1일 → 7일 → 30일 (2026-10-05 ~ 2026-11-04)로 확대. 1일 창은 결과 없음, 7일 창은 무관하거나 기존 추천과 중복, 30일 창에서 2편만 기준을 충족했습니다. 3편 미만이지만 기준을 낮추지 않았습니다.
- 검색어: `chest X-ray AI` (초기 탐색에 `chest radiograph deep learning` 사용)
- 참고: 일부 저널 조회가 HTTP 429(요청 제한)로 누락되었을 수 있습니다.

## 코호트 요약 (집단 수준)

272건(환자 153명), 연령 9–87세(평균 약 51.5세), 여성 136건·남성 136건, PA 184건·AP 88건. 기관 코드 5개, 장비 9종, 촬영 2010–2021년. No Finding 145건, 그 외 Infiltration·Atelectasis가 많고 Nodule·Pneumothorax 등은 희소. 전 건 합성(is_synthetic) 영상.

## 축
- 분포 변화 모니터링 / 기관 간 일반화
- 합성 데이터

## 1. Scalable drift monitoring in medical imaging AI
[링크](https://doi.org/10.1038/s41746-026-03301-1) · npj Digital Medicine
- 관련성: 기관 5개·장비 9종·11년에 걸친 이질성이 있어 분포 변화 점검 대상으로 적합.
- 한계: 합성 영상·소규모·성능 라벨 없음으로 성능 연계는 확인 불가.

## 2. A generalist model for diverse text-guided medical image synthesis
[링크](https://doi.org/10.1038/s41746-026-03381-z) · npj Digital Medicine
- 관련성: 희소 소견(Nodule 7, Pneumothorax 5 등)을 합성 영상으로 보강하는 접근과 연결.
- 한계: 흉부 X선 임상 판독 결과 없음. 방법론 중심 논문.

> 모든 추천은 의사의 검토가 필요합니다. 환자 단위 값은 포함하지 않았습니다.
