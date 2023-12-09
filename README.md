# DATA1030 Project - Trading at Close


## Introduction
- **Problem Statement:**
  - Stock exchanges experience heightened activity and volatility as they near the day's end, especially in the last ten minutes. These critical moments often witness rapid price changes and can significantly influence the day's global economic outlook. The closing price of a stock is often considered its most important price of the day. It's used as a reference point by investors, analysts, and financial media. Since it represents the final consensus of value for the stock on that particular day, many technical and fundamental analysis tools hinge on it.
  - In this project, I would like to utilize machine learning models to predict the closing price movements (indicated by a specifically defined synthetic index) for hundreds of Nasdaq listed stocks.

- **Problem Type:** Regression problem on time-series dataset.
  
- **Data Source:** Competition dataset provided by Optiver on Kaggle.
  
- **Data Collection:** This dataset contains historic data for the daily ten minute closing auction on the NASDAQ stock exchange. The data is collected from the traditional order books and the closing auctions of the stocks by Optiver. The target variable is a synthetic index composed of NASDAQ-listed stocks, which indicates the closing price movement for each single stock. It's noted that the unique stocks and dates are replaced by id to avoid data leakage.

- **Importance:**
  - The prediction model can contribute to combine signals from the auction and the (non-auction) order book, which will help improve the market efficiency and accessibility, especially in the last ten minutes of trading. The ability to consolidate information from both sources is critical for providing the best prices to all market participants. Plus, information from the auction can be used to adjust prices, assess supply and demand dynamics, and identify trading opportunities.
  - The project provides firsthand experience in handling real-world data science problems, mirroring those encountered by traders, quantitative researchers, and engineers.


## File Structure

- `data/`: We stores all raw and preprocessed data files here. `raw_kaggle/train.csv` is the raw data that we will use for EDA, splitting and preprocessing. The raw csv file and processed train-test datasets can also be downloaded [here](https://drive.google.com/drive/folders/1qUySRQF15yYXONtvso2XPZ7sBAsJeuUP?usp=sharing).
- `figures/`: This stores all visualizations for report and presentations.
- `results/`: Trained models and results will be stored here.
- `report/`: Presentations and reports for pipeline, methodology, and model results.
- `src/`: All the notebooks and codes for the machine learning pipeline will be stored here.

## Dependencies
- python version: `3.10.12`
- package versions:
```
requirements = {'numpy': "1.24.3", 'matplotlib': "3.7.3",'sklearn': "1.2.2", 'mlxtend': "0.23.0",
'pandas': "2.0.3",'xgboost': "2.0.1", 'shap': "0.43.0", 'seaborn': "0.12.2",}
```




