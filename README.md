# Predicting the Remaining Useful Life (RUL) of NASA Turbo Engines Using Machine Learning

## Project Overview
This project focuses on predicting the Remaining Useful Life (RUL) of NASA turbo engines using advanced machine learning techniques. By leveraging historical engine performance data, the project aims to provide actionable insights for proactive maintenance, enhancing safety, reducing operational costs, and minimizing downtime.

## Motivation
The gradual degradation of engine components in aviation presents significant challenges, including the risk of mission-critical disruptions and catastrophic failures. Current maintenance practices rely on periodic inspections, which are both costly and insufficient to prevent unexpected failures. This project addresses these challenges by building data-driven predictive models to estimate RUL accurately.

## Features
- Comprehensive data preprocessing, including cleaning, feature engineering, and exploratory analysis.
- Multi-phase methodology combining classification and regression approaches.
- Predictive modeling with Random Forest for classification and Convolutional Neural Networks (CNNs) for regression.
- Statistical and graphical evaluation for performance benchmarking.

---

## Methodology

The project methodology was divided into two phases: classification and regression.

### Phase 1: Classification Task
To simplify the problem initially, the engine's health condition was categorized into three discrete labels based on the Life Ratio (LR):

LR = (Current Cycle) / (End of Life (EOL) Cycle)

- **Good Condition (Label 0)**: \( LR <= 0.6 \)
- **Moderate Condition (Label 1)**: \( 0.6 < LR <= 0.8 \)
- **Warning Condition (Label 2)**: \( LR > 0.8 \)

#### Classification Model
- **Algorithm**: Random Forest Classifier
- **Features**: Selected using correlation analysis and domain knowledge.
- **Training Process**: 
  - Data split into 70% training and 30% validation.
  - Hyperparameter tuning, including the number of trees, maximum depth, and minimum samples per leaf.
- **Evaluation Metrics**: Accuracy, precision, recall, and confusion matrix analysis.

#### Results (Classification)
- Overall accuracy: **89.58%**
- Label-wise performance:
  - Good Condition: **94% accuracy**
  - Moderate Condition: **76% accuracy**
  - Warning Condition: **88% accuracy**

---

### Phase 2: Regression Task
To address the continuous nature of RUL prediction, a CNN model was implemented.

#### CNN Architecture
- **Input Layer**: Accepts 2D time-series data of shape (32 × 13 × 1).
- **Convolutional Layers**:
  - Layer 1: 64 filters, kernel size 3, ReLU activation.
  - Layer 2: 32 filters, kernel size 3, ReLU activation.
- **Flatten Layer**: Converts the output into a 1D vector.
- **Fully Connected Layer**: Single neuron for RUL prediction using linear regression.

#### Training and Evaluation
- **Loss Function**: Mean Squared Error (MSE).
- **Optimizer**: Adam optimizer for efficient gradient updates.
- **Training Process**: Trained over 15 epochs per engine on data from 100 engines.
- **Evaluation Metrics**:
  - Root Mean Squared Error (RMSE).
  - Statistical analyses, including mean RMSE, standard deviation, and error distribution visualization.

#### Results (Regression)
- Average RMSE across all engines: **6.19 cycles**.
- Engine-specific performance:
  - Example: For Engine 1, the CNN achieved an RMSE of **3.88**, with predicted and actual RUL values closely following the same trend.

---

## Dataset
The dataset contains time-series data with:
- **Engine ID**: Unique identifier for each engine.
- **Time in Cycles**: Operational cycle number.
- **Operational Settings**: Three variables representing different engine conditions.
- **Sensor Measurements**: Readings from 21 sensors monitoring engine performance.

### Data Preprocessing
- **Data Cleaning**: Ensured data quality by removing duplicates and checking for missing values.
- **Feature Engineering**:
  - Derived features such as mean, standard deviation, and skewness for each sensor.
  - Retained only features with a correlation coefficient of \( \geq 0.5 \) with the target variable (RUL).
- **Exploratory Data Analysis (EDA)**:
  - Generated descriptive statistics for sensor data.
  - Visualized feature relationships using correlation heatmaps.
  - Removed constant-value features and handled outliers.

---

## Results Summary
### Classification (Random Forest)
- **Confusion Matrix**: 
  - Good Condition: 94% accurate.
  - Moderate Condition: 76% accurate.
  - Warning Condition: 88% accurate.
- **Strengths**: Provided quick actionable insights for engine health categorization.
- **Limitations**: Lacked granularity for precise maintenance scheduling.

### Regression (CNN)
- **Average RMSE**: 6.19 cycles across all engines.
- **Performance Insights**:
  - The CNN effectively captured temporal degradation patterns.
  - Granular RUL predictions enabled detailed maintenance planning.
- **Visualization**: Plots confirmed close alignment between predicted and actual RUL values for multiple engines.

---

## Challenges
- **Sensor Noise**: Required extensive data cleaning and EDA to mitigate noise and variability.
- **Feature Selection**: Balancing the number of features to avoid overfitting while retaining significant predictors.

## Future Directions
- **Model Enhancements**: Explore advanced architectures like Long Short-Term Memory (LSTM) networks.
- **Cost Analysis**: Integrate real-world constraints to refine the practical applicability of the models.
- **Extended Validation**: Test models on new datasets for further generalizability.

---

## Contributors
- **Ashish Bargoti** ([ashish22114@iiitd.ac.in](mailto:ashish22114@iiitd.ac.in))
- **Prajil Bhagat** ([prajil22359@iiitd.ac.in](mailto:prajil22359@iiitd.ac.in))
- **Wasif Ali** ([wasif22583@iiitd.ac.in](mailto:wasif22583@iiitd.ac.in))
- **Subham Maurya** ([subham22510@iiid.ac.in](mailto:subham22510@iiid.ac.in))

---

## Repository
The source code and supporting files for this project are available on [GitHub](https://github.com/Subham-Maurya/TurboEngine-RUL-Estimation).

## License
This project is open-source and available under the [License](LICENSE).
