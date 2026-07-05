# kbo_win_prediction

# ⚾ KBO 승부 예측

포아송 회귀로 KBO 10개 구단의 2025 시즌 최종 순위를 예측한 공모전 프로젝트.
**10팀 중 6팀 순위 정확 적중 · 우승/준우승 예측 성공** (순위상관 ρ ≈ 0.87)

## 파일 구성

| 파일 | 내용 |
| --- | --- |
| `KBO 데이터 크롤링 제출 코드.ipynb` | Selenium + BeautifulSoup 크롤링 (KBO 기록실·Statiz) |
| `KBO 전처리 및 EDA, 모델 제출 코드.ipynb` | 전처리 → EDA → 포아송 회귀 → 시즌 시뮬레이션 |

## 기술 스택

`Python` `pandas` `scikit-learn` `Selenium` `BeautifulSoup` `seaborn`
