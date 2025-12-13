# 🚦 Traffic Flow Prediction

This project predicts urban traffic situations using historical vehicle count data. It leverages time-series features like day, time, and traffic volume from multiple vehicle types (cars, bikes, buses, trucks) to analyze and forecast congestion. The insights can assist in traffic control, reduce emissions, and improve overall road efficiency.

## 📁 Dataset Overview
- **Features:** Time, Date, Day of the Week, Car/Bike/Bus/Truck Counts, Total Vehicles
- **Target:** Traffic Situation (encoded categorical label for congestion level)

## Data Dictionary

The dataset contains traffic flow records, including:
```
Time: Timestamp of the observation
Date: Date of the observation
Day of the week: Day corresponding to the observation
CarCount: Number of cars counted at the observation point
BikeCount: Number of bikes counted
BusCount: Number of buses counted
TruckCount: Number of trucks counted
Total: Total number of vehicles at the timestamp
Traffic Situation: The categorized traffic condition (e.g., congestion levels)
```
## Data Preprocessing
```
Steps:
Time & Date Formatting: The Time and Date columns were converted to appropriate formats (datetime). New features, such as Hour, Month, and Day, were extracted to capture temporal patterns.
Handling Categorical Data: The Day of the week and Traffic Situation were label encoded into numerical values for model compatibility.
Missing Values: Missing values in the dataset were replaced with median values of the respective columns.
```
## 🔍 EDA Highlights
- **Peak hours** observed in morning and evening, with spikes in car & bike volumes.
- **Traffic congestion** increases with truck traffic and lower discount ranges.
- **Consistent traffic volume** across weekdays, but varying by vehicle type.

## 🧠 Model
- **Algorithm:** Random Forest Classifier
- **Accuracy:** Achieved strong classification performance across multiple traffic levels
- **Top Features:** `CarCount`, `BikeCount`, `Time`, `Day of the Week`

## Model Building and Evaluation
Model: Random Forest Classifier
A Random Forest Classifier was trained to predict traffic situations based on the available features. The model performed well in predicting high-traffic periods, offering valuable insights for traffic management.

Evaluation Metrics:
Confusion Matrix: Used to analyze prediction errors and true positives.
Classification Report: Provided precision, recall, and F1-score for each traffic situation category.
Accuracy: The model achieved a satisfactory accuracy in classifying traffic situations.

Feature Importance
The most significant features affecting traffic flow prediction were:
1) CarCount
2) BikeCount
3) Day of the week
4) Hour of the day These features played a critical role in predicting the traffic situation.

Graphical Insights
Several visualizations were generated to enhance understanding:

Traffic volume over time: Cars and bikes dominate during peak hours, while trucks remain steady.
Day-wise Traffic Spread: Different vehicle types exhibit unique spread patterns across the week, though total traffic volume remains fairly stable.
Pairwise Correlation: Positive correlation between CarCount and BikeCount, and a negative correlation between TruckCount and Traffic Situation, indicating heavier truck traffic during congested conditions.

## How to Run
```
python enhanced_code.py
```

## 📊 Visualizations
- Line plots of vehicle flow over time
- Heatmap of feature correlations
- Pairplots and boxplots revealing time vs traffic level distribution
- Feature importance bar plot

## 🎯 Conclusion
This model offers a foundation for smart city traffic control systems, enabling:
- Congestion forecasting
- Efficient route planning
- Sustainable urban mobility through emission and fuel reduction

Moreover, this project emphasizes the broader implications for sustainable urban mobility, suggesting ways to enhance traffic management systems and reduce vehicular emissions. Accurate traffic predictions can lead to more efficient road networks, supporting economic productivity by reducing time spent in traffic and improving overall transportation systems.
