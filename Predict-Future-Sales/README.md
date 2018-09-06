## Predict Future Sales
- [대회 링크](https://www.kaggle.com/c/competitive-data-science-predict-future-sales/)

### Overview
- Coursera의 ["How to win a data science competition"](https://www.coursera.org/learn/competitive-data-science/home/welcome) 강의 최종 프로젝트 대회
- 러시아의 큰 소프트웨어인 1C company의 일일 판매 데이터로 구성된 시계열 데이터
- 다음 달 총 판매량을 예측하는 Task


### Evaluation
- RMSE, Root mean square error
- Submittion File

	```
	ID,item_cnt_month
	0,0.5
	1,0.5
	2,0.5
	3,0.5
	```
	
### Data
- Daily historical sale data
- Task : forcast the total amount of products sold in every shop for the test set	
- File 
	- ```sales_train.csv``` : 2013년 1월 ~ 2015년 10월의 Daily 데이터
	- ```test.csv``` 
	- ```sample_submission.csv``` 
	- ```items.csv``` : items/products의 정보
	- ```item_categories.csv``` : item 카테고리의 정보
	- ```shops.csv``` : shops의 정보
- Fields
	- ID
	- shop\_id
	- item\_id
	- item\_category\_id
	- item\_cnt\_day
	- item\_price
	- date : dd/mm/yyyy
	- date\_block\_num : January 2013 is 0, February 2013 is 1,..., October 2015 is 33
	- item_name
	- shop_name
	- item_category\_name


## 캐글 일지
### 2018.09.05
```
- 대회 참여 시작
- 대회 Overview 확인 및 데이터셋 확인 	
- 기본 데이터 탐색, 시각화 아이디어 추가
- 시각화 아이디어
    - 월별 판매 total
    - 월별 판매 unique
    - 주별 판매 total
    - 주별 판매 unique
    - 시간의 흐름에 따른
        - 아이템별 판매 total
        - 아이템별 판매 unique
        - shop별 판매 total
        - shop별 판매 unique
    - 카테고리별 판매 개수
        - 특정 카테고리가 날짜에 반응하는가?
        - 우리의 문제는 11월 예상이므로 13, 14년 10월의 특징이 있는지 check
    - 러시아에 블랙프라이데이 같은 날이 있는가?
    - 러시아 공휴일에 따라 다른가?
    - 평일/주말에 따라 다른가?
```

### 2018.09.06
```
- 주별 판매량 그래프
- Shop별 일일 판매량 그래프
- 아이템 카테고리별 일일 판매량 그래프 
```    