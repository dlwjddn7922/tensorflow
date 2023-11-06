# KOELECTRA를 활용한 네이버 영화 리뷰 분석
<img src = https://github.com/dlwjddn7922/tensorflow/assets/79899654/b95adf43-793e-4549-8c43-01bf5ed5428f width="2000" height="500">**출처:** 이미지출처 naver 영화이미지

# 1. 개요
이번 프로젝트에서는 한국어 자연어 처리 모델인 KOELECTRA를 활용하여 네이버 영 리뷰의 긍부정 예측을 하고자 한다.

## 1.1 문제 정의
네이버 영화 리뷰는 영화의 정보의 파악에 있어 가장 보편적으로 활용되는 정보의 창구이다.
 - 영화 리뷰와 영화 흥행의 상관관계를 나타내는 참고자료를 통해 영화 리뷰의 가치를 언급
 - 프로젝트로 해당 과업을 해결할 때 기대할 수 있는 장점, 활용 가능성 등을 언급
 - 필요에 따라서는 적절한 그림을 그려 표현(ppt 등)


## 1.2 데이터 및 모델 개요
데이터는 네이버에서 제공하는 영화 리뷰와 영화리뷰데이터를(https://github.com/e9t/nsmc) 활용하여, 총 20만 건의 데이터에 대해서 사전 학습 언어 모델의 재학습(fine-tuning)을 수행한다. 

| 입력       |모델|출력|
|----------|---|---|
| 영화 리뷰 문장 |KOELECTRA small[3]|부정(0), 긍정(1)|<br>

|id|document|label|
|--|--------|-----|
|6270596|굳 ㅋ|1|
|9274899|GDNTOPCLASSINTHECLUB|0|
|8544678|뭐야 이 평점들은.... 나쁘진 않지만 10점 짜리는 더더욱 아니잖아|0|
|6825595|지루하지는 않은데 완전 막장임... 돈주고 보기에는....|0|
|6723715|3D만 아니었어도 별 다섯 개 줬을텐데.. 왜 3D로 나와서 제 심기를 불편하게 하죠??|0|
|7898805|음악이 주가 된, 최고의 음악영화|1|
|6315043|진정한 쓰레기|0|
|6097171|마치 미국애니에서 튀어나온듯한 창의력없는 로봇디자인부터가,고개를 젖게한다|0|


영화 리뷰 문장은 전처리를 통해서 가공한다. 대표적인 전처리로는 결측치와 중복값을 제거하고, 띄어쓰기로 구분이 되지 않는 리뷰 역시 제거한다.

# 2. 데이터
## 2.1 데이터 소스
#### 원시데이터

|num|id|document|label|
|---|--|--------|-----|
|1|6270596|굳 ㅋ|1|
|2|9274899|GDNTOPCLASSINTHECLUB|0|
|3|8544678|뭐야 이 평점들은.... 나쁘진 않지만 10점 짜리는 더더욱 아니잖아|0|
|4|6825595|지루하지는 않은데 완전 막장임... 돈주고 보기에는....|0|
|5|6723715|3D만 아니었어도 별 다섯 개 줬을텐데.. 왜 3D로 나와서 제 심기를 불편하게 하죠??|0|
|6|7898805|음악이 주가 된, 최고의 음악영화|1|
|...|...|...|...|
|146178|5567676|정말 너무 재밌음 ㅋ|1|
|146179|4608761|오랜만에 평점 로긴했네ㅋㅋ 킹왕짱 쌈뽕한 영화를 만났습니다 강렬하게 육쾌함|1|
|146180|5308387|의지 박약들이나 하는거다 탈영은 일단 주인공 김대희 닮았고 이등병 찐따 OOOO|0|
|146181|9072549|그림도 좋고 완성도도 높았지만... 보는 내내 불안하게 만든다|0|
|146182|5802125|절대 봐서는 안 될 영화.. 재미도 없고 기분만 잡치고.. 한 세트장에서 다 해먹네|0|
|146183|6070594|마무리는 또 왜이래|0|


## 2.2 탐색적 데이터 분석
#### 데이터 분포

```
print('총 샘플의 수 :',len(train_data))
```
총 샘플의 수 : 146183
```
train_data['label'].value_counts().plot(kind = 'bar')
```
<img src=https://github.com/dlwjddn7922/tensorflow/assets/79899654/a5bb63d7-c143-430b-9d82-246adcb141be>

print(train_data.groupby('label').size().reset_index(name = 'count'))
```
   label  count
0      0  73342
1      1  72841
```

## 2.3 데이터 전처리
#### 결측치 제거
```
train_data.loc[train_data.document.isnull()]
```
<img src=https://github.com/dlwjddn7922/tensorflow/assets/79899654/dd6f594c-d1b5-4e38-a7e3-10bff62d884c>

train_data = train_data.dropna(how = 'any') # Null 값이 존재하는 행 제거
print(train_data.isnull().values.any()) # Null 값이 존재하는지 확인
```
False
```

-Null 값을 가진 샘플이 제거되었습니다. 다시 샘플의 개수를 출력하여 1개의 샘플이 제거되었는지 확인해봅시다.

```
print(len(train_data))
```
146182

#### 한글과 공백제외하고 모두 제거




# 3. 재학습 결과
## 3.1 개발 환경
 - pycharm, python, torch, pandas, ...
 - 
## 3.2 KOELECTRA fine-tuning
## 3.3 학습 결과 그래프

# 4. 배운점
