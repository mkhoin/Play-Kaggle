# Google Analytics Customer Revenue Prediction
- [대회 링크](https://www.kaggle.com/c/google-analytics-customer-revenue-prediction)

### Overview
- 80/20 규칙은 입증되었고, 적은 수의 고객이 대부분 수익을 창출함. 따라서 마케팅 팀은 홍보 전략에 대해 적절한 투자를 유도해야 함
- Google Merchandise Store(Gstore) 고객 데이터 셋을 분석
- GA 데이터를 기반으로 데이터 분석하는 경우 효과적 운영 변경과 마케팅 예산 사용의 향상이 기대됨
- 상금 : \$12,000 / \$8,000, / \$5,000
	- R로 만든 답은 Special 상 존재

### Evaluation
- RMSE
- $$\hat{y}$$ : 고객에 대한 예상 수익, $$y$$ : 실제 수익
- [자연 로그](https://ko.wikipedia.org/wiki/%EC%9E%90%EC%97%B0%EB%A1%9C%EA%B7%B8) 형태로 예측

### 일정
- 2018.11.08 : 참가 기한
- 2018.11.08 : 팀 합병 기한
- 2018.11.15 : 최종 제출 마감일
- 모두 UTC 기준, 대회 주최측이 변경할 수 있음

### Data
- 데이터 셋의 각 행 : 상점을 반복(1회의 액션)
	- 따라서 같은 id가 여러번 행에서 나타날 수 있음
- Train셋에 totals에 transactionRevenue는 예측하려는 수익 정보
- 예측할 것 : 사용자당 모든 거래의 합계(자연 로그)
- File
	- ```training.csv```
	- ```test.csv```
	- ```sampleSubmission.csv```
- Fileds
	- fullvisitorId : 고유 식별자
	- channelGrouping : sotre를 방문할 때 사용된 채널
	- date :  사용자가 상점을 방문한 날짜
	- device : 사용된 장치의 사양
	- geoNetwork : 지리 정보
	- sessionId : 상점 방문에 대한 고유 식별자(세션)
	- socialEngagementType : 참여도 유형, "소셜 참여" 또는 "소셜 참여 없음"
	- totals : 세션 전체의 집계 값
	- trafficSource : 세션이 시작된 트래픽 소스
	- visitId : 세션의 식별자. 사용자에게만 고유. 완전 고유는 fullVisitorId와 VisidId의 조합
	- visitnumber : 사용자 세션 번호. 첫 세션이면 1
	- visitStartTime : 타임 스탬프
- 제거된 필드
	- hits 
	- customDimensions
	- totals

## 캐글 일지
### 2018.09.16
```
- 대회 참여 시작
- 대회 Overview 확인 및 데이터셋 확인
```
