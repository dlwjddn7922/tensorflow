# KOELECTRA를 활용한 네이버 영화 리뷰 분석

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
| 영화 리뷰 문장 |KOELECTRA small[3]|부정(0), 긍정(1)|

영 리뷰 문장은 전처리를 통해서 가공한다. 대표적인 전처리로는 결측치와 중복값을 제거하고, 띄어쓰기로 구분이 되지 않는 리뷰 역시 제거한다.

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
