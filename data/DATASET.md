### Data Description

`raw_kaggle\train.csv`

- *stock_id* - A unique identifier for the stock. Not all stock IDs exist in every time bucket.
- *date_id* - A unique identifier for the date. Date IDs are sequential & consistent across all stocks.
- *imbalance_size* - The amount unmatched at the current reference price (in USD).
- *imbalance_buy_sell_flag* - An indicator reflecting the direction of auction imbalance.
  1. buy-side imbalance; 1
  2. sell-side imbalance; -1
  3. no imbalance; 0
- *reference_price* - The price at which paired shares are maximized, the imbalance is minimized and the distance from the bid-ask midpoint is minimized, in that order. Can also be thought of as being equal to the near price bounded between the best bid and ask price.
- *matched_size* - The amount that can be matched at the current reference price (in USD).
- *far_price* - The crossing price that will maximize the number of shares matched based on auction interest only. This calculation excludes continuous market orders.
- *near_price* - The crossing price that will maximize the number of shares matched based auction and continuous market orders.
- *bid /ask_price* - Price of the most competitive buy/sell level in the non-auction book.
- *bid /ask_size* - The dollar notional amount on the most competitive buy/sell level in the non-auction book.
- *wap* - The weighted average price in the non-auction book. 
  $$
  \frac{BidPrice * AskSize + AskPrice * BidSize}{BidSize + AskSize}
  $$
- **seconds_in_bucket** - The number of seconds elapsed since the beginning of the day's closing auction, always starting from 0.
- **target** - The 60 second future move in the wap of the stock, less the 60 second future move of the synthetic index. Only provided for the train set.
  1. The synthetic index is a custom weighted index of Nasdaq-listed stocks constructed by Optiver for this competition.
  2. The unit of the target is basis points, which is a common unit of measurement in financial markets. A 1 basis point price move is equivalent to a 0.01% price move.
  3. Where t is the time at the current observation, we can define the target:
     $$
     Target = (\frac{StockWAP_{t+60}}{StockWAP_{t}} -  \frac{IndexWAP_{t+60}}{IndexWAP_{t}}) * 10000
     $$
  
- 

**All size related columns are in USD terms.**

**All price related columns are converted to a price move relative to the stock wap (weighted average price) at the beginning of the auction period.**