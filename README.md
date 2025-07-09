# 🚦 Traffic Flow Prediction

This project predicts urban traffic situations using historical vehicle count data. It leverages time-series features like day, time, and traffic volume from multiple vehicle types (cars, bikes, buses, trucks) to analyze and forecast congestion. The insights can assist in traffic control, reduce emissions, and improve overall road efficiency.

## 📁 Dataset Overview
- **Features:** Time, Date, Day of the Week, Car/Bike/Bus/Truck Counts, Total Vehicles
- **Target:** Traffic Situation (encoded categorical label for congestion level)

## 🔍 EDA Highlights
- **Peak hours** observed in morning and evening, with spikes in car & bike volumes.
- **Traffic congestion** increases with truck traffic and lower discount ranges.
- **Consistent traffic volume** across weekdays, but varying by vehicle type.

## 🧠 Model
- **Algorithm:** Random Forest Classifier
- **Accuracy:** Achieved strong classification performance across multiple traffic levels
- **Top Features:** `CarCount`, `BikeCount`, `Time`, `Day of the Week`

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
