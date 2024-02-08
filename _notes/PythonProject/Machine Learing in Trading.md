
## 신호 생성에 사용할 수 있다.
수익률,부호를 예측한다. 자산에 대한 매수 매도신호를 낼 수 있다. 
위험관리에도 사용합니다. 예측을 통해 포지션 크기, 스탑로스, 클러스터와 같은 데이터 내에서 패턴관계와 구조를 발견한다. 

## 1. [[Unsupervised Learning Trading Strategy]]

[[트레이딩]]에 [[머신러닝]]을 적용시키자

## Challenges to applying ML in trading.
### Reflexivity feedback loop
그러니까, 매주 금요일에 주식이 오르는것을 확인했고, 그렇게 목요일에 사고 금요일에 사는 전략을 채택했다. 그런데, 모든 사람들이 그렇게 하니까, 목요일에 많이 사다보니 금요일에 많이 오르는게 당연하다. 이것이 Reflexivity feedback loop 이다.  
## Overfitting
모델이 데이터를 너무 잘 학습하여 테스트 데이터에서 실패한다. 
## generalization
모델이 실제 데이터와 동일하게 수행되지는 않는다.


## nonstationarity



어려운 2가지 
1. 수익을 예측하고 가격을 예측하는것이 어렵다.
2. 수익 실현, 자산의 방향 예측 하는것이 어렵다.
3. 변동성이 높은 자산의 변동을 예측하기 (Volatility/  Volatile 변덕스러운)


계획 
1. Collect and prepare the data
2. Develop a hypothesis for a strategy
3. coding the model
4. Backtest the strategy

s&p500 다 다운하고
월별로 집계해서 매월 유동성 상위 50만 가져오고 월별 수익률 계산
다운로드
유사한 자산으로 클러스터로 그룹화한다.


## 2. Twitter Sentiment Investing Startegy

Nasddq 100 and Sentiment 
ex) 긍정적인 평가를 내리면 , 좋게 

1. Load Nasdaq stocks twitter sentiment data.,
2. Calculate a quantitative feature of the engament ratio in Twitter of each stock.
3. Every month rank all stocks and construct and equal - weight protfolio.
4. Compare it against Nasdaq performance


## 3. Intraday Strategy Using CARCH Model

변동성 예측이 일중 전략에 어떻게 작동하는지 보여준다.

1. 단일 자산으로 시뮬레이터된 일일 데이터와 5분데이터를 로드하고.
2. 롤링 윈도우에 적합한 함수를 정의 한다. 전 자산의 변동성을 예측하여 프리미엄을 계산한다.
3. 일일 데이터 일중 데이터를 병합하고 일 중 기술지표를 계산해서 일중 신호를 형성한다.
4. 두개 의 신호로 포지션 진입을 생성하고, 