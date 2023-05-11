
## Short introduction
Greetings, my name is Sotaro Suzuki and I specialize in machine learning and AI engineering.<br>
For over six years now, I have been working on developing an AI-based program that predicts stock and forex market trends. It is important to note that the current version of the program is still in its beta stage and there is no assurance of consistent profitability. <br> Therefore, I strongly advise that you open a demo account and install the program for testing purposes. Additionally, I am in the process of arranging third-party verification of the program's trading history through platforms such as Forex Factory, MQL4 database, and GoGoJungle.

## Deep Stock
Deep Stock can be simply described as an automated trading program with AI.<br>
What makes it different from ordinary algorithmic trading is that, while ordinary algorithmic trading follows a certain rule (for example, the simplest rules is golden crosses and dead crosses, and a complex one may be Elliott wave or Dow theory), this program automatically collects information, pre-process it, learns it, predict, buys and sells entirely.

### How the program works
Specifically, the procedure is as follows. Please refer to the numbers in the list against the numbers in the figure below.<br>


![FXAI drawio (2)](https://github.com/Sotaro-Suzuki/Deep_Stock/assets/95641926/3d60e5af-36dc-4992-8c35-04771bb25d49)


(1)First, information on past stock prices, foreign exchange rates, commodity futures, economic indicators and SNS (twitter, reddit) is collected and stored as data automatically on a regular basis in the cloud.<br>
(2)Next, the data is automatically trained by AI in the cloud. The key point here is that it does not learn in a predefined pattern, but rather uses ensemble learning, i.e. it tries out different models, quantifies which information has the greatest impact on the time period, and can choose a combination of several optimal models. Image recognition, natural language processing and time series processing are parallelised and all processes are fast enough to fit within one second. This algorithm chooses the one with the best results from among the algorithms adopted from the latest papers and improved independently, and then optimises the initialisation of parameters, layers, weights and biases in it.<br>
(3)In addition to the own deep learning algorithms, it also uses AutoML on Azure and Neural Network Console in Sony for automatic machine learning and also comparison. Automated Machine Learning (AutoML) is a mechanism that automates the time-consuming task of developing machine learning models, which traditionally require individual implementation through programming.<br>
(4)Once the best model is selected, the trading decisions are predicted in real-time during weekday trading hours and the results are sent to the client from the cloud.<br>
(5)The automated trading platform of each brokerage firm automatically trades on the basis of the trading decisions sent to it.
In this way, the AI can be optimised every time according to what information is important to the times, making it possible for the system to continue growing without any modifications.<br>

## Backtesting Result
The following image shows the results of a simulation that has been trading for four months<br>
![4096-64-1e-06-0 001-glorot_normal-LSTM-2 0-0 0-1 0-1 0-30分割](https://user-images.githubusercontent.com/95641926/147685891-28501ed7-1290-4642-857c-627b2848916f.png)


<br>
The blue line is the profit from a long position. In other words, the more it rises steadily, the more profitable it is.<br>
Conversely, the red line is the profit when a short position is taken. In this case, the more it falls to the right, the more profitable it is.<br>
The green line is then the sum of the profit from a long position and short position.<br>
The left-hand scale shows the price of the currency, that is, EUR_USD, while the right-hand scale shows the profit (in US dollars) when trading in one currency. As a result of trading over the four months (2021/08/31~2021/12/29), the total profit has grown to $0.06691, which means that if, for example, the asset amount is $100,000 and all the trades were in 100,000 currencies, the profit would be $6691. However, there are 502 trades and the transaction fee of $0.00005 per trade, so the pure profit would be $4181.<br>
The interest rate for the last four months is therefore 4.18%. Taking into account the maximum drawdown, there is no bankruptcy risk up to 25x leverage, but if the leverage is set to 10x, just in case, the interest rate is 41.0%.<br>

## Forward Testing Result
The following images show the results of the forward test from January 1 to May 17, 2022. <br>
![1024-512-1e-06-0 001-glorot_normal-LSTM-3 0-1-1-1-1-60分割](https://user-images.githubusercontent.com/95641926/168840483-3879ff7a-5538-401e-b5d3-019e7695d0e0.png)

The total profit has risen to 0.07578, which means that if, for example, the asset amount is $100,000 and all the trades were in 100,000 currencies, the profit would be $7578. Then, there are 615 trades and the transaction fee of $0.00005 per trade, so the pure profit is $5248.
The profit ratio for the past 5 months is therefore 5.25%. <br>

## Forward Testing Result (2023)
The paper will be written as a thesis after confirming profitability up to the present time in 2023.

## Installation
This AI currently performs best on Forex EUR/USD, so only EUR/USD is available for automated trading. I am also building a model for bonds, commodities, and crypto asset trading and will upload them additionally as performance improves.<br>
And currently there is one EX4 file uploaded to this Repositorie. So the only platform where trading can be done is on MetaTrader 4 (recommended by OandaJapan). I am planning to develop software for any brokerage platform in the near future.<br>
And since MetaTrader 4 needs to be connected to the internet at all times, it is recommended that the following steps are taken on the virtual environment in the cloud.<br>
The following is a concrete introduction to the system.<br>
(1)First download the 'FXAI.ex4' file in this repositories to a local PC.<br>
(2)Next, launch MetaTrader 4 at your brokerage and add the 'FXAI.ex4' file to the 'Experts' folder on MetaTrader 4.<br>
(3)Next, add the library file 'Mylib.ex4' in the 'Library' folder and the file 'Mylib.mqh' in the 'Include' folder.<br>
(4)Under 'Options', select 'Expert Adviser', check the boxed area as shown in the picture below and add <br>"http://ss-cloud.net"<br> to the url. This will allow you to request a real-time buy/sell decision from the cloud and at the same time trade the actual buy/sell transaction.<br>
(5)Then drag and drop 'FXAI.ex4' from the 'Expert' folder onto the EUR_USD chart.



