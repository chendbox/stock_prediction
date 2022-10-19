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
    
    
4. Hyperparameters tuned
    Constructed lightbgm model related parameters for tuning. Applied baysian optimiztion to tune hyperparameters and evaluted with RMSE score. 
             
            'num_leaves': 187,
            'learning_rate': 0.073,
            'max_depth': 12,
            'min_data_in_leaf': 167,
            'min_sum_hessian_in_leaf': 0.003,
            'bagging_fraction': 0.855,
            'feature_fraction': 0.837,
            'drop_rate': 0.261,
            'random_state': 42    
    
5. Modeling and prediction
    Developed a lightbgm decision tree model and implemented the selected parameters. Fitted the model with featurs, and label datasets. Made the prediction. Rankded the predicted returns. Calcualted the sharpe ration and ploted the feature importance.
    
  
