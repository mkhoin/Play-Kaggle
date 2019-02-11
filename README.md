# Play-Kaggle
- [Kaggle](https://www.kaggle.com/)에 참여한 기록을 남기는 Repo입니다
- Kaggle 관련 자료가 필요하신 분은 [Kaggle-knowhow](https://github.com/zzsza/Kaggle-knowhow) Repo를 참고하면 좋을 것 같습니다

## 참여 대회 정보

|                  Competition                 | Main Algorithms |       Period      |    Rank   |  Prize |
|:--------------------------------------------:|:---------------:|:-----------------:|:---------:|:------:|
|       [Santander Product Recommendation](https://github.com/zzsza/Kaggle_Santander-Product-Recommendation/tree/5480e0adc160e9dfdea522ea1557b2e184b7e686)       |  Random Forest  |      2016.12      |  600/1784 |        |
|         [Expedia Hotel Recommendations](https://github.com/zzsza/Kaggle_Expedia-hotel-recommendations/tree/bb45080c7362ad8d3ba4b21d689b4f638e236aa0)        |  Random Forest  |      2017.02      | 1260/1974 |        |
|        Zillow's Home Value Prediction        |  FE + StackNet  | 2017.09 ~ 2017.11 |  81/3799  | Silver |
| [Elo Merchant Category Recommendation](https://github.com/zzsza/Play-Kaggle/tree/master/Elo-Merchant-Category-Recommendation) |                 |      Current      |           |        |

## Code Memo
- ```df.describe()```시 e+6 이런 식으로 숫자가 나올 경우 : ```pd.set_option('float_format', '{:.3f}'.format)```로 해결
- ```np.logical_and(조건A, B)``` : logical 연산 
- ```%config InlineBackend.figure_format = 'retina'``` : 맥에서 retina 설정. 매번 까먹음
- string formatting에서 속도가 가장 빠른 것은 f'{string}'!
	- 파이콘2018 안주은님 발표 [Pythonic한 코드가 효율적일까?](https://www.slideshare.net/ssuserd5b689/pythonic-110444563#20) 참고
- ```cols_to_drop = [col for col in train.columns if train[col].nunique() == 1]``` : value가 1개인 column
- ```pd.Series.nunique()``` : Series의 unique의 개수(n) return(Default : NA 제외)
- ```A.intersection(*other_sets)``` : A(set)와 other sets의 교집합
- ```pd.options.display.max_columns = 999``` : max_columns 조절
- ```pd.cut(카테고리화할 숫자 데이터, bins)``` : 데이터를 여러 구간으로 구분할 경우 사용, return 카테고리
- ```plt.scatter```, ```sns.distplot```, ```sns.violinplot```
- lightgbm dataset : ```lgb.Dataset(train_feature, label=label, categorical_feature=categorical_feature)```
- pandas도 chain 방식을 지원함. pandas 1.0 이후부턴 이렇게 사용하는게 늘어날 듯

    ```
    (pandas.read_csv('data/titanic.csv.gz')
       .query('Age < Age.quantile(.99)')
       .assign(Sex=lambda df: df['Sex'].replace({'female': 1, 'male': 0}),
               Age=lambda df: pandas.cut(df['Age'].fillna(df.Age.median()),
                                         bins=[df.Age.min(), 18, 40, df.Age.max()],
                                         labels=['Underage', 'Young', 'Experienced']))
       .pivot_table(values='Sex', columns='Pclass', index='Age', aggfunc='mean')
       .rename_axis('', axis='columns')
       .rename('Class {}'.format, axis='columns')
       .style.format('{:.2%}'))
    ```
- `df.loc[(조건), 'Target')] = 5` 특정 조건을 만족하는 경우에 값 할당하고 싶을 경우