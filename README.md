# Stock_prediction

## Problem Statement
Stock market becomes more complext nowdays. While most of finance decision was made manually by professionals, technology was ushered in new opportunities for retail investors. Data Scientist make predictions based on machine learning models. In this project, I built a strategy to analyze the jpx stock data with stock indicator algorthims, and used LightGBM model to evaluate stock returns.

## Contents

|files |description|
|datasets| train.csv, stock_list.csv|
|ppt| project summary powerpoint |
notebook | data process, feature engineering, baysian optimiztaion, prediction |
|model |LightGBM |
|Feature |adjusted close price, prediciton, ran, feature_importance |

## WorkFlow

1. Data collection
    used kaggle API, stock key words to download jpx related stock files. Unzipped the data and use train.csv, stock_list.csv for analysis.
2. Feature engineering
    train data shape is (2332531, 12), stock_list data shape is (4417, 16) . Merged two dataset and processed EDA. Conducted feature engineering by adjsuting the close price, and created columns of returns, moving average, exponential moving average, volatility of 9, 12, 26, 50 days.
    
 3. Stock indicator evaluation
    Set Toyota stock as example, analyze the trends with bollinger bands, MACD, relative strenght index, stochastic oscillator. Aso built entyr and exit signal algorthim. 
    
    
4. Hyperparameters tuned
    Constructed lightbgm model related parameters for tuning. Applied baysian optimiztion to tune hyperparameters and evaluted with RMSE score. 
    Parameters included numer of leaves, leaning rates, maximu depth, mininum data in each leaf, mininum sum of hessian in each leaf, bagging fraction rate, feature fraction rate, dropp out rate, and seeds
             
    
5. Modeling and prediction
    Developed a lightbgm decision tree model and implemented the selected parameters. Fitted the model with featurs, and label datasets. Made the prediction. Rankded the predicted returns. Calcualted the sharpe ration and ploted the feature importance.
    
    
    
 ## Results
 1. merged data columns: 'RowId', 'Date', 'SecuritiesCode', 'Open', 'High', 'Low', 'Close', 'Volume', 'AdjustmentFactor', 'ExpectedDividend' 'SupervisionFlag', 'Target', 'Name', 'SectorName' wiht a shape (
 2. All stocks : plot stock returns, close prices, volume. plot eturns in different years. plot all stock close price trends. 
 3. Toyota stock: plot SMA20, bollinger bands, macd, rsi, stochastic oscillator, buy and sell signal. 
 4. Added columns: 9 days return, 12 days return, 26 days return, 50 days return, 9 days moving average, 12 days moving average, 26 days moving average,
    50 days moving average, 9 days exponential moving average, 12 days exponential moving average, 26 days exponential moving average, 50 days exponential                      -   moving average, 9 days volatility, 12 days volatility, 26 days volatility, 50 days volatility

5. Hyperparamters:

            'num_leaves': 187,
            'learning_rate': 0.073,
            'max_depth': 12,
            'min_data_in_leaf': 167,
            'min_sum_hessian_in_leaf': 0.003,
            'bagging_fraction': 0.855,
            'feature_fraction': 0.837,
            'drop_rate': 0.261,
            'random_state': 42      
            
 6. Valid Sharpe: 0.017550976374450456, RMSE: 0.022199137224236744, MAE: 0.015119354307299914
 8. feature importance top 5: 90 days reuturns, 26 days returns, 12 days return, 50 days returns, 50 days volatility 
 
 <img
    src = '/Users/DanDan/Documents/七月在线/MachineLearning/newproject/data/buy.png'
    title = 'buy & sell signal'
    style='display: inline-block; margin:0 auto; max-width: 300px'>
