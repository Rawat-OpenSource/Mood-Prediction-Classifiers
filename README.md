# Mood Prediction
This project implements two classification approaches to predict states of the next day mood (bad/normal/good) using temporal smartphone sensor data and user patterns. The dataset contains 19 behavioral indicators and insights including screen time, app usage, activity levels, and self-reported arousal/valence. A LSTM network and a Random Forest Classifier is implemented for the classification task.

## Why these models are selected:
### Random Forest:
**Feature Relationships**: Model can capture complex interactions between variables (e.g., screen time × social app usage)  
**Interpretability**: Identifies key output indicators through feature importance

### Long Short-Term Memory (LSTM):
**Temporal Patterns**: Model can capture temporal patterns in the data, significant since mood is influenced by historical behavior patterns (e.g., sustained screen time -> fatigue -> lower mood)  
**Sequence Modeling**:
Implements sequence modelling to processes timestamped data in chronological order to capture:  
- Daily/weekly behavioral cycles   
- Progressive mood transitions  
- Lagged effects (e.g., yesterday's activity → today's mood)  

## Key insights: 
**Dominant Predictor**: Screen time accounted for almost half of the predictive power in Random Forest  
**Temporal Advantage**: LSTM captured weekly behavioral patterns affecting mood transitions  
**Class Performance**: Both models excelled at detecting extreme states ("good" and "bad" mood days) but struggled with cases of "normal" days 

## Technical Implementations:
**Feature Engineering**: 7-day rolling averages for key behavioral indicators  
**Hyperparameter Tuning**:  
- Bayesian optimization for LSTM architecture  
- Grid search for Random Forest parameters  
**Evaluation Metrics**: Accuracy, F1-score, ROC-AUC, and Cohen's Kappa
