# KOELECTRA를 활용한 네이버 영화 리뷰 분석
<img src = https://www.google.com/imgres?imgurl=https%3A%2F%2Fssl.pstatic.net%2Fstatic%2Fm%2Fmovie%2Ficons%2Fnaver_movie_favicon.ico&tbnid=i5qDlBnu7LD8UM&vet=12ahUKEwi_1K6Qyq6CAxXFfXAKHU2SAXAQMygEegQIARBR..i&imgrefurl=https%3A%2F%2Fm.photoviewer.naver.com%2Fmovie%3FlistUrl%3Dhttp%253A%252F%252Fm.movie.naver.com%252Fm%252Fcategory%252Fmovie%252FCurrentMovie.nhn%26type%3Dmovie%26movieCode%3D35175%26imgId%3D2620979&docid=i5zycUY93KrieM&w=256&h=256&q=%EB%84%A4%EC%9D%B4%EB%B2%84%EC%98%81%ED%99%94&ved=2ahUKEwi_1K6Qyq6CAxXFfXAKHU2SAXAQMygEegQIARBR width="2000" height="500">**출처:** 이미지출처 bing 이미지 ai

# 1. 개요
이번 프로젝트에서는 한국어 자연어 처리 모델인 KOELECTRA를 활용하여 네이버 영 리뷰의 긍부정 예측을 하고자 한다.

## 1.1 문제 정의
네이버 영화 리뷰는 영화의 정보의 파악에 있어 가장 보편적으로 활용되는 정보의 창구이다.
 - 영화 리뷰와 영화의 순위의 상관관계를 나타내는 참고자료를 통해 맛집 리뷰의 가치를 언급
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

## 2.2 탐색적 데이터 분석

## 2.3 데이터 전처리
- 입력 데이터의 전처리 과정
- 학습에 활용할 데이터의 양
- 학습과 검증 데이터셋 분리
- 학습 데이터의 구성

# 3. 재학습 결과
## 3.1 개발 환경
 - pycharm, python, torch, pandas, ...
 - 
## 3.2 KOELECTRA fine-tuning
## 3.3 학습 결과 그래프

# 4. 배운점
