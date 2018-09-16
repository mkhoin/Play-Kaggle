# Play-Kaggle
- [Kaggle](https://www.kaggle.com/)에 참여한 기록을 남기는 Repo입니다


## 참여 대회 정보
- Format 설정한 후, 추가 예정



## Code Memo
- ```df.describe()```시 e+6 이런 식으로 숫자가 나올 경우 : ```pd.set_option('float_format', '{:.3f}'.format)```로 해결
- ```np.logical_and(조건A, B)``` : logical 연산 
- ```%config InlineBackend.figure_format = 'retina'``` : 맥에서 retina 설정. 매번 까먹음
- string formatting에서 속도가 가장 빠른 것은 f'{string}'!
	- 파이콘2018 안주은님 발표 [Pythonic한 코드가 효율적일까?](https://www.slideshare.net/ssuserd5b689/pythonic-110444563#20) 참고
- ```cols_to_drop = [col for col in train.columns if train[col].nunique() == 1]``` : value가 1가지로 구성된 column 찾기