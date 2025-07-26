# Hourly Energy Consumption Forecasting

## Project Overview

This project demonstrates an end-to-end data science workflow for forecasting hourly electricity demand using a time-series dataset from American Electric Power (AEP). The goal is to build a predictive model that can accurately forecast future energy load, which is a critical task for smart grid load-balancing and efficient energy distribution.

The script follows a structured, multi-phase approach:
1.  **Data Cleaning and Validation:** Ingests the raw data, corrects data types, handles potential missing values, and sorts the time series to ensure chronological integrity.
2.  **Exploratory Data Analysis (EDA):** Visualizes the data to uncover key patterns, including long-term trends, annual seasonality (summer/winter peaks), and daily circadian rhythms.
3.  **Feature Engineering:** Creates a rich set of features for the machine learning model, including calendar-based features (hour, day of week, month) and time-series features (lags and rolling window statistics).
4.  **Modeling and Evaluation:** Implements a hybrid Random Forest model that leverages the engineered features. The model is trained on all historical data up to 2018 and evaluated on unseen data from 2018, simulating a real-world forecasting scenario. Its performance is benchmarked against a seasonal naive model to quantify its accuracy improvement.

---

## Dataset

The project uses the **AEP Hourly Energy Consumption** dataset, which is publicly available on Kaggle. It contains over a decade of hourly energy load data from 2004 to 2018.

-   **Source:** [PJM Hourly Energy Consumption on Kaggle](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption/data)
-   **File needed:** `AEP_hourly.csv`

---

## Getting Started

### Prerequisites

This project requires Python 3 and the libraries listed in the `requirements.txt` file.

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/energy-consumption-forecasting.git](https://github.com/your-username/energy-consumption-forecasting.git)
    cd energy-consumption-forecasting
    ```

2.  **Set up a virtual environment (recommended):**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required packages:**
    ```bash
    pip install -r requirements.txt
    ```

### How to Run the Script

1.  **Download the dataset:** Place the `AEP_hourly.csv` file in the root directory of the project.

2.  **Execute the Python script:** Run the main script from your terminal. The script will execute all phases sequentially and print the output, including the final model performance and visualizations, to your console.
    ```bash
    python energy_consumption_prediction.py
    ```

---

## Results

The hybrid Random Forest model demonstrates a significant improvement in forecast accuracy over the simple baseline model. For the 2018 test period, the model achieved a Mean Absolute Error (MAE) that was approximately **90% lower** than the baseline, showcasing its ability to learn complex, non-linear patterns from the data.
