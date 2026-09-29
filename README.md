# ⚾ KBO 정규시즌 최종 순위 예측

7시즌(2018~2024) 기록을 직접 크롤링하고, 팀별 **승수·무승부 수를 포아송 회귀**로 예측해
진행 중인 2025 시즌 성적에 잔여 경기 기대 승무패를 더해 최종 순위를 낸 공모전 프로젝트.

2025 KBO 오픈데이터 활용 공모전 **스마트융합대학장상** · 3인 팀

**프로젝트 상세 → [Notion 포트폴리오](https://zany-meeting-aba.notion.site/f8783f9aaedb82df8483011f0a588f95)**
**발표 보고서 → [Google Drive](https://drive.google.com/drive/folders/1Q3K9YiBtPmVPozQ_bJdL0rC-D6o4YxaY)**

## 핵심 포인트
- 수집: KBO 기록실·Statiz 동적 페이지를 Selenium + BeautifulSoup으로 크롤링
- 변수: OPS·wRC+·FIP·WHIP·팀 WAR·피타고리안 기대승률 등 세이버메트릭스 지표 + 부상·나이 변수
- 모델: 승·무·패는 음수가 없는 카운트 데이터 → 포아송 회귀

## 결과
| 지표 | 값 |
|---|---|
| 순위 정확 적중 | 10팀 중 6팀 (우승 LG · 준우승 한화 · 최하위 키움 포함) |
| 순위 평균 절대 오차 | 0.8계단 |
| 스피어만 순위 상관 | ρ ≈ 0.87 |

한계: 후반기 흐름(연승·연패)과 트레이드를 반영하지 못함 (최대 오차: 롯데 예측 3위 → 실제 7위)

## 파일 구성
| 파일 | 내용 |
|---|---|
| `KBO 데이터 크롤링 제출 코드.ipynb` | Selenium + BeautifulSoup 크롤링 (KBO 기록실·Statiz) |
| `KBO 전처리 및 EDA, 모델 제출 코드.ipynb` | 전처리 → EDA → 포아송 회귀 → 시즌 시뮬레이션 |

## 기술 스택
`Python` `pandas` `scikit-learn` `Selenium` `BeautifulSoup` `seaborn`
