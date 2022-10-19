# stock_prediction

Problem Statement
Stock market becomes more complext nowdays. While most of finance decision was made manually by professionals, technology was ushered in new opportunities for retail investors. Data Scientist make predictions based on machine learning models. In this project, I built a strategy to analyze the jpx stock data with stock indicator algorthims, and used LightGBM model to evaluate stock returns.

Contents

|files |description|
|datasets| train.csv, stock_list.csv|
|ppt| project summary powerpoint |
notebook | data process, feature engineering, baysian optimiztaion, prediction |
|model |LightGBM |
|Feature |adjusted close price, prediciton, ran, feature_importance |

WorkFlow

1. Data collection
    used kaggle API, stock key words to download jpx related stock files. Unzipped the data and use train.csv, stock_list.csv for analysis.
2. Feature engineering
    train data shape is (2332531, 12), stock_list data shape is (4417, 16) . Merged two dataset and processed EDA. Conducted feature engineering by adjsuting the close price, and created columns of returns, moving average, exponential moving average, volatility of 9, 12, 26, 50 days.
    
 3. Stock indicator evaluation
    Set Toyota stock as example, analyze the trends with bollinger bands, MACD, relative strenght index, stochastic oscillator. Aso built entyr and exit signal algorthim. 
    
    
