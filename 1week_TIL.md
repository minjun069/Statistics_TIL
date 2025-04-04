# 통계학 1주차 정규과제

📌통계학 정규과제는 매주 정해진 분량의 『*데이터 분석가가 반드시 알아야 할 모든 것*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **Statistics_1st_TIL**에 나열된 분량을 읽고 `학습 목표`에 맞게 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 추가자료와 교재를 다시 참고하여 보완하는 것이 좋습니다.

1주차는 `1부. 데이터 기초체력 기르기`를 읽고 새롭게 배운 내용을 정리해주시면 됩니다.


## Statistics_1st_TIL

### 1부. 데이터 기초체력 기르기
### 01. 통계학 이해하기
### 02. 모집단과 표본추출
### 03. 변수와 척도
### 04. 데이터의 기술 통계적 측정
### 05. 확률과 확률변수

## Study Schedule

|주차 | 공부 범위     | 완료 여부 |
|----|----------------|----------|
|1주차| 1부 p.2~56     | ✅      |
|2주차| 1부 p.57~79    | 🍽️      | 
|3주차| 2부 p.82~120   | 🍽️      | 
|4주차| 2부 p.121~202  | 🍽️      | 
|5주차| 2부 p.203~254  | 🍽️      | 
|6주차| 3부 p.300~356  | 🍽️      | 
|7주차| 3부 p.357~615  | 🍽️      | 

<!-- 여기까진 그대로 둬 주세요-->

# 01. 통계학 이해하기

```
✅ 학습 목표 :
* 통계학의 필요성에 대해 인식한다.
* 기술통계와 추론통계의 특성을 구분할 수 있다.
```
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

데이터 분석에서 통계학 기본기가 없다면 분석 결과가 유의미한지, 오류는 없는지, 개선 방법은 무엇인지 알 수 없다.


<통계학 vs 머신러닝>  
-통계학의 주 목적: 해석 [가설 -> 데이터]  
확률을 통해 가설을 검증하고 추정 모델을 통해 데이터를 해석하는 것을 목표로 하기 때문에 모델의 신뢰도와 단순성을 추구한다.

-머신러닝의 주 목적: 예측 [데이터 -> 가설]  
해석용이를 위한 단순성 추구를 버리고 예측에 집중하기 때문에 따라 모형의 복잡성이 높은 경향이 있다. 한편 반대로 보편적인 예측 성능 향상을 위해 주로 과적합 해결에 집중하게 된다.

현대의 머신러닝: 데이터의 학습과 분류, 예측 자체를 학습하는 것. 지속적인 데이터 증가와 변화를 고려한 학습과 예측 프로세스를 설계하는 것을 포함.


<기술 통계와 추론 통계>  
기술 통계 descriptive statistics  
: 주어진 데이터의 특성을 사실에 근거하여 설명하고 묘사하는 것  
-EDA는 기술통계를 포함하지만, 시각화 및 인사이트 도출을 포함하는 더 넓은 개념.

추론 통계 inferential statistics  
: 표본 집단으로부터 모집단의 특성을 추론하는 것  
데이터 과학을 통해 예측이나 분류하는 것 포함.

기술 통계와 추론 통계의 통합적 프로세스  
: 표본의 특성을 분석 -> 특성의 일반화 여부 판단 -> 모집단의 특성으로 추정



# 02. 모집단과 표본추출

```
✅ 학습 목표 :
* 모집단과 표본의 정의와 관계를 설명할 수 있다.
* 편향과 분산의 차이를 설명할 수 있다.
```

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

<전수조사와 표본조사>

빅데이터라 하더라도 전수조사는 아니기 때문에 모집단의 특성을 반영할 수 있도록 표본을 추출하는 노하우가 중요하다.  
예측 및 분류 모델링 단계에서는 적절한 규모의 표본을 추출하여 진행하는 것이 경제적, 시간적으로 유용하다.

통계적으로 변수 하나당 최소 30개의 관측치가 필요하다.  
일반적으로 최소 200개 이상의 표본이 확보되면 분석이 가능하다.

표지 재포획법 marking-and-recapture method  
: 표본 조사를 통해 모집단의 크기를 유추하는 방법  
표식을 남긴 표본의 수 k, 재포획시 발견한 표본의 수 n, 모집단의 크기 N  
k/N =~= n/k


<표본 오차>  
표본 오차 sampling error: 모집단과 표본의 차이 중 자연발생적인 변동  
비표본 오차 non-sampling error: 모집단과 표본의 차이 중 자연발생적인 변동을 제외한 변동  
-비표본 오차의 원인: 편향, 오류(측정 오류, 데이터 처리 오류), 시간적 요인, 응답자의 태도(응답 오류, 무응답 오류) 조사 설계 및 방법론 문제(설문 설계 오류, 프레임 오류) 등


<편향>  
편향 bias: 비표본 오차의 원인 중 하나  
-표본추출편향 sample selection bias  
-가구편향 household bias: 모집단의 부분 집단 단위로 한번씩만 추출하는 경우 크고 적은 집단이 작고 많은 집단보다 적게 추출되는 현상  
-응답편향 response bias  
-무응답편향 non-response bias

편향은 확률화 등을 통해 최소하거나 없앨 수 있다.


<인지적 편향>  
인지적 편향: 분석가의 성향이나 상황에 따라 발생하는 비논리적 추론 패턴

-확증 편향 confirmation bias  
: 자신이 본래 믿고 있는대로 정보를 선택적으로 받아들이고 임의로 판단하는 편향  
-기준점 편향 anchoring bias  
: 분석가가 가장 처음에 접하는 정보에 지나치게 매몰되는 편향  
-선택 지원 편향 choice-supportive bias  
: 본인이 의사결정을 내리는 순간 그 선택의 긍정적인 부분에 대해 더 많이 생각하고 그 결정에 반대되는 증거를 무시하게 되는 편향  
-분모 편향 denominator bias  
: 분수 전체가 아닌 분자에만 집중하여 현황을 왜곡하여 판단하게 되는 편향  
-생존자 편향 survivorship bias  
: 소수의 성공한 사례를 일반화된 것으로 인식함으로써 나타나는 편향


<머신러닝 모델 측면의 편향과 분산>  
편향: 모델이 갖는 전반적으로 체계적인 오차.  
분산: 데이터 샘플이 변화할 때 모델 예측 성능이 변화하는 정도.  
모델의 복잡도가 상승할수록 편향은 감소하지만 분산은 증가하는 경향을 보임.


<표본 편향을 최소화하는 표본 추출 방법>  
-복원추출 vs 비복원추출  
모집단에 비해 추출하려는 표본의 양이 작으면 복원 추출과 비복원 추출의 차이가 거의 없지만,  
모집단의 크기가 별로 크지 않거나 추출하는 표본이 모집단의 20% 이상인 경우 복원 추출 방식이 편향을 더 줄일 수 있다.


# 03. 변수와 척도
```
✅ 학습 목표 :
* 독립변수, 종속변수의 관계를 파악할 수 있다.
* 척도(변수의 데이터적 속성)의 종류를 설명할 수 있다.
```
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

<변수의 종류>  
독립변수 = 설명변수 = 예측변수 = 조작변수 = 특징  
independent = explanatory = predictor = manipulated = feature

종속변수 = 반응변수 = 출력변수 = 피예측변수 = 측정변수 = 표적변수  
dependent = outcome = predicted = measured = target

통제 변수: 종속변수에 영향을 줄 수 있는 외부 요소를 일정하거나 무작위적으로 배분되도록 통제하는 변수


<변수 관계의 종류>  
의사관계 spurious relationship  
: 변수 간에 상관성은 있으나 그 상관성이 다른 변수에 의해 나타나는 관계

양방향적 인과관계 reciprocal causality  
: 두 변수가 서로 간에 인과적 영향을 미치는 관계

조절 관계 moderating relationship  
: 독립변수와 종속변수 사이의 관계 강도를 변화시키는 변수가 존재하는 관계  
-강화 조절 enhancing moderation, 약화 조절 buffering moderation, 방향 전환 조절 interaction moderation 유형이 존재  

매개관계 mediational relationship  
: 독립변수와 종속변수의 중간에서 매개변수가 개입되어 독립변수의 영향을 종속변수에 전달하는 관계


변수의 척도와 종속변수의 유무에 따라 적절한 분석방법을 선택해야 한다.  
(회귀분석, ANOVA, PCA 등)


# 04. 데이터의 기술 통계적 측정

```
✅ 학습 목표 :
* 산포도의 의미를 설명하고 측정방법을 나열할 수 있다.
* 정규분포의 왜도값과 첨도값이 얼마인지 답할 수 있다.
```

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

<평균의 종류>  
산술평균: 등간척도나 비율척도로 측정된 데이터  
가중평균: 항목 별로 비중이 다른 데이터  
기하평균: 시간에 따라 비율적으로 변화하는 값의 평균  
조화평균: 값이 비율 형태(단위 입력당 산출 ~ 시속, 시간당작업량 등)로 표현되는 경우의 평균  
각 항목의 역수를 평균낸 후 다시 역수를 취하는 방식으로 계산한다.


<산포도>

평균편차가 미분이 되지 않는 이유: 절댓값 함수는 미분 불가능한 구간이 존재하기 때문

변동 계수 coefficient of variation CV  
: 표준편차를 산술평균으로 나누어 준 값.  
평균이 다른 두 자료의 표준편차를 표준화함으로써 산포도를 비교할 수 있다.


<왜도와 첨도 측정 방법>  
왜도 측정 방법  
-피어슨 비대칭 계수 Pearson's skewness coefficients  
: 왜도에 따라 평균과 중앙값 또는 최빈값 과의 거리가 달라지는 원리 사용

첨도 측정 공식  
sum(x-x_bar)^4 / ( n/S^2 -3 )  
기준인 정규분포의 첨도가 0으로, 음의 방향으로 커질수록 분포가 넓어지고, 양의 방향으로 커질수록 뾰족한 형태의 분포


<표준편차의 경험법칙>  
표준편차의 경험법칙 empirical rule  
: 표본의 크기가 100이상일 경우 분포가 정규분포에 가까워짐에 따라 나타나는 법칙.  
-표본의 크기가 30~100사이에는 +-2 표준편차가 보다 정확하다.  
-표본의 크기가 30미만인 경우에는 유의미한 범위를 측정할 수 없다.

만약 데이터가 정규분포가 아니거나 분포를 모를 경우에는 Chebyshev's theorem 을 적용할 수 있다.

Chebyshev's theorem  
: 정확한 분포를 모를 때 보수적인 확률 예측을 위한 분산 기반 정리.  
-평균에서 2표준편차 이내에 최소 75% 이상의 데이터가 분포  
-평균에서 3표준편차 이내에 최소 88.89% 이상의 데이터가 분포


# 05. 확률과 확률변수

```
✅ 학습 목표 :
* 확률변수의 개념과 종류를 설명할 수 있다.
* 심슨의 역설을 설명하고, 발생 원인을 식별하며, 이를 해결하기 위한 방안을 도출할 수 있다.
```

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

비조건확률 unconditional probability (= 한계 확률 marginal probability)  
: 아무 조건이 없는 상황에서 사건이 일어날 확률  
-다른 차원의 조건들이 교차하는 상황에서, 한 차원의 조건만 따지는 경우


분할: 사건들을 모두 합했을 때 전체 사건들을 포괄하되, 중복이 일어나지 않는 사건들의 집합  
= MECE Mutually exclusive, collectively exhausitive


베이지안 이론: 사건 발생 전에 이미 가지고 있는 사전확률 p(A)와 우도 확률 p(B|A)를 안다면 사후확률 p(A|B)를 계산할 수 있다.


심슨의 역설 Simpson's Paradox  
: 부분에서 나타나는 경향과 전체에서 나타나는 경향이 반대로 바뀌는 통계적 역설.

<br>
<br>

# 확인 문제

## 문제 1.

> **🧚Q. 한 대형 병원이 두 명의 외과 의사(A와 B)의 수술 성공률을 비교하려고 한다. 과거 1년간의 데이터를 보면, A 의사의 전체 수술 성공률은 80%, B 의사의 전체 수술 성공률은 90%였다. 이 데이터를 본 병원 경영진은 A 의사의 실력이 B 의사보다 별로라고 판단하여 A 의사의 수술 기회를 줄이는 방향으로 정책을 조정하려 한다.
그러나 일부 의료진은 이 결론에 의문을 제기했다.
그들은 "단순한 전체 성공률이 아니라 더 세부적인 데이터를 분석해야 한다"고 주장했다.**

> **-A 의사의 실력이 실제로 B 의사보다 별로라고 결론짓는 것이 타당한가?   
-그렇지 않다면, 추가로 확인해야 할 정보는 무엇인가?**

<!--심슨의 역설을 이해하였는지 확인하기 위한 문제입니다-->

<!--학습한 개념을 활용하여 자유롭게 설명해 보세요. 구체적인 예시를 들어 설명하면 더욱 좋습니다.-->

```
수술의 종류 별로 파악할 필요가 있다. 예를 들어, A가 성공률이 낮은 편에 속하는 수술을 한 횟수가 더 많았기 때문에 전체 수술 성공률이 낮아졌을 수 있다. 따라서 수술 종류에 따른 수술 성공률을 각기 비교하는 것이 합리적이다.

한편 두 의사 개인 별 전체 수술 횟수 역시 중요하다. 만약 A의 수술 횟수가 100회이고 B의 수술이 10회라면, 표본이 작은 쪽은 성공률의 신뢰도를 통계학적으로 보장할 수 없다.
```

### 🎉 수고하셨습니다.
