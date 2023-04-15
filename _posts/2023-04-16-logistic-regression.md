<a class="anchor" id="zero"></a>
# **Logistic Regression Classifier Tutorial with Python**

# 로지스틱 회귀 분류기 __ 김정연

<a class="anchor" id="zero-one"></a>
# **목차**

1.	[로지스틱 회귀 소개](#one)
2.	[로지스틱 회귀 직관](#two)
3.	[로지스틱 회귀 분석의 가정](#three)
4.	[로지스틱 회귀 분석 유형](#four)
5.	[Import libraries](#five)
6.	[Import dataset](#six)
7.	[데이터 분석 탐색하기](#seven)
8.	[feature vector, 목표 변수 선언하기](#eight)
9.	[training, test set 으로 분리하기](#nine)
10.	[Feature engineering](#ten)
11.	[Feature scaling](#eleven)
12.	[모델 학습](#twelve)
13.	[예측결과](#thirteen)
14.	[정확도 점수 확인하기](#fourteen)
15.	[혼동 행렬Confusion matrix](#fifteen)
16.	[Classification metrices](#sixteen)
17.	[임계값 레벨 조정](#seventeen)
18.	[ROC - AUC](#eighteen)
19.	[k-Fold Cross Validation](#nineteen)
20.	[Hyperparameter optimization using GridSearch CV](#twenty)
21.	[결과와 결론](#twenty-one)
22. [참조](#twenty-two)


# **1. 로지스틱 회귀 분석의 가정** <a class="anchor" id="one"></a>

[목차로 돌아가기](#zero-one)

로지스틱 회귀분석은 주어진 독립 변수의 선형 조합을 이용하여 종속 변수를 예측하는 통계 기법 중 하나입니다. 주로 **이진 분류(binary classification)** 문제에 사용되며, 예측값이 이산적인(discrete) 형태를 가집니다.
