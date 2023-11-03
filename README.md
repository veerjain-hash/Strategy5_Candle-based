# Strategy5_Candle-based
Logic of the strategy:
This is an option buying strategy which catches big moves on the indices options through price action. All the working will be done on ATM PE & CE options.

Instrument:NIFTYBANK
RSI:14
Timeframe:15m
Capital required:15k inr
Segment:Options
Expiry: Weekly

Rules brief: When RSI 14 crosses 60 mark, that candle becomes the triggered candle.When the high of triggered candle is broke we take our entry. Trailing Stoploss will be the low of previous candle and Target will be == (Triggered candle's high - entry candle's low) *5.

Set1
Conditions:
1.Time>=1030
2.When RSI 14 of the current candle is above 60, and previous candle is below 60. (This ensures our crossover).
Disclaimer: The conditions are to be seen in ATM PE/CE options chart.

Position:
Buy,NIFTYBANK,ATM,PE/CE,Weekly,lot=1

Runtime variable: high_candle == High of the candle
(This entry is for our triggered candle so we can capture the high of the candle in a runtime variable.)

Exit
Time > 15 minutes of entry.

Runtime Variable on Exit of set 1: Here, we pass a variable "set1_exit == 1".

Set2 
1.RSI >= 60
2.variable - set1_exit == 1 (ensures our triggered candle trade has been exited)
3.LTP > variable - high_candle

Position:
Buy,NIFTYBANK,Previously traded strike,PE/CE,Weekly,lot=1


Make 4 sets for CE/PE. I have uploaded the chart for better visualization.


Disclaimer :  I am not a SEBI registered investment or financial advisor. Don't deploy our strategies purely based on past performance only. We are not responsible for your profit or loss. Although this strategy is fully automated, you are advised to keep a track on your account to monitor any deviations or errors. As option selling involves market risks, Please consult your financial advisor before investing.


Disclaimer: This is a algorithmic strategy which is also my personal project which is coded on tradetron, for codes ping me up.
