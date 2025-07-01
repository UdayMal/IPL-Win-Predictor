-- **IPL Win Prediction System** -- 

This project predicts the win probability of a team during an IPL (Indian Premier League) match based on real-time match statistics using machine learning. It uses historical match data to train a predictive model that estimates whether the batting team will win the match, considering multiple factors like current score, remaining balls, wickets, and run rate.

- **Problem Statement**
  
In a T20 cricket match, predicting the outcome while the game is live is a challenging task due to rapidly changing scenarios. This system attempts to solve that by analyzing the second innings of past IPL matches and predicting the likelihood of a win for the batting team based on current match context.

- **Dataset**
  
  i. matches.csv – Contains match-level information such as teams, venue, and winners.
        
  ii. deliveries.csv – Contains ball-by-ball data for each match.
        
  These datasets are publicly available from Kaggle IPL Dataset.

- **Technologies & Libraries Used**
    Python
    
    Pandas, NumPy – Data manipulation
    
    Scikit-learn – Machine learning modeling (Logistic Regression)
    
    OneHotEncoder, ColumnTransformer, Pipeline – Feature transformation
    
    Train/Test Split – Model validation  

🔄** Workflow**
1. Data Cleaning and Preprocessing

    Combined matches and deliveries datasets
    
    Filtered out rain-affected matches (DL method applied)
    
    Standardized team names (e.g., 'Delhi Daredevils' → 'Delhi Capitals')
    
    Considered only 8 consistent teams
    
    Focused only on the second innings of the match

2. Feature Engineering

    Calculated current_score, runs_left, balls_left
    
    Computed wickets_left, current run rate (crr), and required run rate (rrr)
    
    Labeled the result as 1 (win) or 0 (loss) for the batting team

3. Model Building

    Encoded categorical columns using OneHotEncoding
    
    Built a pipeline combining encoding and Logistic Regression
    
    Trained on 80% of the data and tested on 20%

4. Model Evaluation

    Achieved ~80.8% accuracy on the test dataset
    
    Predicted win probabilities using .predict_proba()

