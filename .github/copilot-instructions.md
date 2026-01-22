# GitHub Copilot Instructions for Traffic Flow Prediction

## Project Overview
This is a **Machine Learning project** for predicting urban traffic situations using historical vehicle count data. The project analyzes time-series features to forecast congestion levels and provide insights for smart traffic management.

## Tech Stack
- **Language**: Python 3.8+
- **Core Libraries**: pandas, numpy, scikit-learn
- **Visualization**: matplotlib, seaborn
- **Environment**: Jupyter Notebook
- **ML Algorithm**: Random Forest Classifier

## Project Structure
```
TrafficFlowPrediction/
├── code.py                           # Main Python script
├── Traffic_flow_prediction.ipynb     # Jupyter notebook with full analysis
├── TrafficDataset.csv                # Traffic dataset
├── requirement.txt                   # Python dependencies
├── README.md                         # Project documentation
└── description.md                    # Detailed project description
```
## Code Style and Standards
### Python Style
- Follow PEP 8 guidelines for Python code
- Use meaningful variable names (e.g., `df` for dataframes, descriptive names for features)
- Include comments for complex logic and data transformations
- Use type hints when adding new functions

### Data Processing Conventions
- Use pandas for data manipulation
- Convert time features to minutes since midnight
- Use LabelEncoder from scikit-learn for categorical encoding
- Apply StandardScaler for feature scaling before model training

### Visualization Guidelines
- Use seaborn and matplotlib for all visualizations
- Set figure sizes appropriately (typically 10x6 or 12x6)
- Always include titles, labels, and legends
- Use consistent color schemes across visualizations

## Dataset Information

### Features
- **Time**: Timestamp (HH:MM:SS AM/PM) - converted to minutes
- **Date**: Date (DD-MM-YYYY) - converted to days since reference
- **Day of the week**: Categorical day (label encoded)
- **CarCount**: Number of cars
- **BikeCount**: Number of bikes  
- **BusCount**: Number of buses
- **TruckCount**: Number of trucks
- **Total**: Total vehicle count
- **Traffic Situation**: Target variable (multi-class, label encoded)

### Data Preprocessing Pipeline
1. Convert Time to minutes since midnight
2. Convert Date to days since reference date (2023-10-09)
3. Label encode categorical features ('Day of the week', 'Traffic Situation')
4. Handle missing values (if any)
5. Scale features using StandardScaler

## Machine Learning Model

### Model: Random Forest Classifier
- **n_estimators**: 100 trees
- **random_state**: 42 (for reproducibility)
- **Features**: Time, Day of the week, CarCount, BikeCount, BusCount, TruckCount, Date
- **Target**: Traffic Situation

### Model Evaluation
- Use train_test_split with test_size=0.2
- Evaluate with: confusion_matrix, classification_report, accuracy_score
- Analyze feature importance

## Development Guidelines

### Adding New Features
1. Extract features consistently with existing pipeline
2. Ensure proper encoding for categorical variables
3. Scale numerical features appropriately
4. Update feature list in model training

### Modifying Visualizations
1. Maintain consistent styling with existing plots
2. Always include proper titles and labels
3. Use appropriate color palettes
4. Ensure plots are readable at standard sizes

### Working with the Dataset
- The reference date for date conversion is 2023-10-09
- Time is stored as minutes since midnight (0-1439)
- All categorical features are label encoded
- Missing values should be handled before model training

## Testing and Validation
- Always split data into training and testing sets
- Use consistent random_state=42 for reproducibility
- Validate model performance with confusion matrix and classification report
- Check feature importance to understand model behavior

## Common Tasks

### Running the Code
```bash
# Run Python script
python code.py

# Run Jupyter notebook
jupyter notebook Traffic_flow_prediction.ipynb
```

### Installing Dependencies
```bash
pip install -r requirement.txt
```

### Key Libraries Import Pattern
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import confusion_matrix, classification_report, accuracy_score
```

## Best Practices

### When Suggesting Code Changes
1. Maintain consistency with existing code style
2. Preserve the data preprocessing pipeline
3. Keep visualizations informative and clear
4. Ensure reproducibility (use random_state)
5. Add comments for complex transformations

### When Adding New Models
1. Follow the existing train-test split approach
2. Apply same preprocessing steps
3. Use consistent evaluation metrics
4. Compare with Random Forest baseline
5. Document model parameters

### When Debugging
1. Check data types after transformations
2. Verify no missing values before training
3. Confirm feature scaling is applied
4. Validate label encoding consistency
5. Check for data leakage

## Domain Knowledge

### Traffic Patterns
- **Peak Hours**: Morning (7-9 AM) and evening (5-7 PM)
- **Vehicle Hierarchy**: Cars > Bikes > Buses > Trucks (by count)
- **Congestion Factors**: CarCount and BikeCount are most influential
- **Weekly Patterns**: Consistent weekday traffic with slight variations

### Important Correlations
- Strong positive: CarCount ↔ BikeCount
- Negative: TruckCount ↔ Traffic Situation
- Time-based: Hour of day significantly impacts traffic situation

## Notes for AI Assistants
- This is a classification problem, not regression
- Target variable is categorical (Traffic Situation)
- Feature engineering focuses on temporal patterns
- Model interpretability is important (hence Random Forest)
- Visualizations are key for understanding traffic patterns
- Always maintain data integrity through preprocessing pipeline
