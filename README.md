# Play-Kaggle
- [Kaggle](https://www.kaggle.com/)에 참여한 기록을 남기는 Repo입니다
- Kaggle 관련 자료가 필요하신 분은 [Kaggle-knowhow](https://github.com/zzsza/Kaggle-knowhow) Repo를 참고하면 좋을 것 같습니다

## 참여 대회 정보

|                  Competition                 | Main Algorithms |       Period      |    Rank   |  Prize |
|:--------------------------------------------:|:---------------:|:-----------------:|:---------:|:------:|
|       Santander Product Recommendation       |  Random Forest  |      2016.12      |  600/1784 |        |
|         Expedia Hotel Recommendations        |  Random Forest  |      2017.02      | 1260/1974 |        |
|        Zillow's Home Value Prediction        |  FE + StackNet  | 2017.09 ~ 2017.11 |  81/3799  | Silver |
| Google Analytics Customer Revenue Prediction |                 |      current      |           |        |


## Code Memo
- ```df.describe()```시 e+6 이런 식으로 숫자가 나올 경우 : ```pd.set_option('float_format', '{:.3f}'.format)```로 해결
- ```np.logical_and(조건A, B)``` : logical 연산 
- ```%config InlineBackend.figure_format = 'retina'``` : 맥에서 retina 설정. 매번 까먹음
- string formatting에서 속도가 가장 빠른 것은 f'{string}'!
	- 파이콘2018 안주은님 발표 [Pythonic한 코드가 효율적일까?](https://www.slideshare.net/ssuserd5b689/pythonic-110444563#20) 참고
- ```cols_to_drop = [col for col in train.columns if train[col].nunique() == 1]``` : value가 1개인 column