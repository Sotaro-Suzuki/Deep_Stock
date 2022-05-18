This repository is temporarily open to the public now due to job hunting. (05/17/2022)<br>

## Short introduction
Hello. I am Sotaro Suzuki, a machine learning and AI engineer.<br>
I have been developing an "Stock and forex prediction AI" more than three years since its conception.<br>
The current program is a beta version and there is no guarantee that it will be profitable, so it is not distributed yet.
However, I am planning to verify the trading history by third parties, such as Forex Factory, MQL4 databse and GoGoJungle.<br>

## Deep Stock
This fx can be simply described as an automated trading program with AI.<br>
What makes it different from ordinary algorithmic trading is that, while ordinary algorithmic trading follows set rules (for example, the simplest rules are golden crosses and dead crosses), this program is automatically collects information, learns, decides, and buys and sells.

### how the program works
Specifically, the procedure is as follows. Please refer to the numbers in the list against the numbers in the figure below.<br><br>
<img src="https://user-images.githubusercontent.com/95641926/168771698-6a3ec352-7f8d-4130-a73a-c5b4b5e0e519.png" width="500">

(1)First, information on past stock prices, foreign exchange rates, commodity futures, economic indicators and SNS (twitter, reddit) is collected and stored as data automatically on a regular basis in the cloud.<br>
(2)Next, the data is automatically trained by AI in the cloud. The key point here is that it does not learn in a predefined pattern, but rather uses ensemble learning, i.e. it tries out different models, quantifies which information has the greatest impact on the time period, and can choose a combination of several optimal models. Natural language processing and time series processing are parallelised and all processes are fast enough to fit within one second. This algorithm does not use simple and old ones such as SVM, MLP, RNN, CNN. LSTM, GRU, BiLSTM, etc., but chooses the one with the best results from among the algorithms adopted from the latest papers and improved independently, and then optimises the initialisation of parameters, layers, weights and biases in it.<br>
(3)Once the best model is selected, the trading decisions are predicted in real-time during weekday trading hours and the results are sent to the client from the cloud.<br>
(4)The automated trading platform of each brokerage firm automatically trades on the basis of the trading decisions sent to it.
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

## Installation
This AI currently performs best on Forex EUR/USD, so only EUR/USD is available for automated trading. I am also testing AI for bonds, commodities, and crypto asset trading and will upload additional AI as performance improves.<br>
And currently there is one EX4 file uploaded to this Repositorie. So the only platform where trading can be done is on MetaTrader 4 (recommended by OandaJapan). I am planning to develop software for any brokerage platform in the near future.<br>
And since MetaTrader 4 needs to be connected to the internet at all times, it is recommended that the following steps are taken on the virtual environment in the cloud.<br>
The following is a concrete introduction to the system.<br>
(1)First download the 'FXAI.ex4' file in this repositories to a local PC.<br>
(2)Next, launch MetaTrader 4 at your brokerage and add the 'FXAI.ex4' file to the 'Experts' folder on MetaTrader 4.<br>
(3)Next, add the library file 'Mylib.ex4' in the 'Library' folder and the file 'Mylib.mqh' in the 'Include' folder.<br>
(4)Under 'Options', select 'Expert Adviser', check the boxed area as shown in the picture below and add <br>"http://ss-cloud.net"<br> to the url. This will allow you to request a real-time buy/sell decision from the cloud and at the same time trade the actual buy/sell transaction.<br>
(5)When dragging and dropping 'FXAI.ex4' from the 'Expert' folder onto the EUR_USD 15-minute chart, the following window will appear. Here there are fields for entering your name and date of birth as external variables, so please insert your full name in alphabets, e.g.　JohnSmith. Enter the date of birth without any spaces, e.g. 20010101. The name and date of birth are matched in the cloud and the trading decision is sent to an MQL4 file, which can then be traded on MT4.<br>
<img width="330" alt="スクリーンショット 2021-12-15 0 12 00" src="https://user-images.githubusercontent.com/95641926/146094305-e216becb-5ce6-4816-9490-f8d798b7c02f.png"><br>



