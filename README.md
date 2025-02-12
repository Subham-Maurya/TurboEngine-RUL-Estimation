# Turbo Engine Remaining Useful Life (RUL) Prediction

## Overview
This project aims to predict the **Remaining Useful Life (RUL)** of NASA's turbofan engines using various **machine learning models**. The objective is to improve **predictive maintenance** strategies by providing **early failure warnings**, reducing the risk of in-flight engine failures.

## Features
- **Preprocessing and Exploratory Data Analysis (EDA)**: Cleaning and analyzing NASA's engine dataset.
- **Machine Learning Models**:
  - **Decision Tree** and **Random Forest**
  - Convolutional Neural Networks (**CNN**)
- **Historical Data Utilization**: Leveraging time-series sensor data to estimate engine wear.
- **Dataset**: C-MAPSS (Commercial Modular Aero-Propulsion System Simulation) provided by NASA.

## Project Structure
```
TurboEngine-RUL-Estimation/
│── Report.pdf                       # Detailed project report
│── Preprocessing-and-EDA.ipynb      # Data preprocessing and exploratory analysis
│── Decision tree and Random Forest Model.ipynb # Decision Tree & Random Forest models
│── CNN Model.ipynb                  # CNN implementation for RUL estimation
│── CMaps/                           # NASA dataset files
│   ├── train_FD001.txt
│   ├── test_FD001.txt
│   ├── RUL_FD001.txt
│   ├── ... (more datasets)
│── LICENSE                          # License file
│── README.md                        # This file
```

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/TurboEngine-RUL-Estimation.git
   cd TurboEngine-RUL-Estimation
   ```

## Usage
- Open and run **Preprocessing-and-EDA.ipynb** to clean and prepare the dataset.
- Train models using:
  - **Decision tree and Random Forest Model.ipynb** for traditional ML approaches.
  - **CNN Model.ipynb** for deep learning-based RUL estimation.

## Dataset
The dataset used is **NASA's C-MAPSS dataset**, containing sensor data from multiple engine units. It is located in the **CMaps/** directory.

## Results
- Decision Tree and Random Forest models provide **interpretable results** with reasonable accuracy.
- The CNN model demonstrated **higher accuracy** compared to traditional ML models.
- Early detection of engine wear enables **proactive maintenance** and cost savings.

## License
This project is licensed under the GNU License - see the LICENSE file for details.

## Contributors
- Subham Maurya (subham22510@iiitd.ac.in)
- Wasif Ali (wasif22583@iiitd.ac.in)
- Ashish Bargoti (ashish22114@iiitd.ac.in)
- Prajil Bhagat (prajil22359@iiitd.ac.in)

## Acknowledgment
This project is based on NASA's **C-MAPSS dataset** for turbofan engine degradation modeling.

## Contact
For any queries, reach out to the contributors via their provided email addresses.

