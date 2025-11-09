# 🥑 Avocado Price Time Series Analysis (2015–2020)

A public data science project analyzing the historical trends and seasonality of avocado prices using a Kaggle dataset. The analysis creates a **robust national price index**, adjusts for **inflation**, and applies the **Prophet** model for forecasting.

### 🎯 Project Goals

1.  **Data Engineering:** Create a single, national **Weighted Average Price** time series from regional data.
2.  **Inflation Adjustment:** Fetch CPI data from FRED to calculate the **Real Price** (inflation-adjusted price), enabling accurate year-over-year comparison.
3.  **Exploratory Analysis:** Use **Time Series Decomposition** to separate the data into **Trend**, **Seasonal**, and **Residual** components.
4.  **Autocorrelation Analysis:** Examine **ACF and PACF plots** to understand the underlying correlation structure.
5.  **Forecasting:** Apply the **Prophet** model (from Meta/Facebook) to project future price movements.

---

### 🚀 Setup and Run the Analysis

This project uses **`uv`** for fast dependency management.

#### 1. Data Source

The primary dataset, `avocado-updated-2020.csv`, must be downloaded manually due to its size.

1.  **Download the Dataset:** Obtain the file from **[Kaggle: Avocado Prices 2020 Dataset](https://www.kaggle.com/datasets/timmate/avocado-prices-2020/data)**.
2.  **Organize Data:** Create a folder named `data` in the root of this repository and place the downloaded CSV file inside it:

    ```
    /avocado-prices
    ├── av.ipynb
    ├── data/
    │   └── avocado-updated-2020.csv  <-- Place file here
    └── README.md
    └── requirements.txt
    ```

#### 2. Environment Setup (using `uv`)

You will need Python 3 and the `uv` tool installed on your system.

1.  **Install `uv`** (if you haven't already):
    ```bash
    pip install uv
    ```
2.  **Create and Activate Virtual Environment:**
    ```bash
    uv venv
    source .venv/bin/activate    # macOS/Linux
    .venv\Scripts\activate       # Windows (Command Prompt)
    ```
3.  **Install Dependencies:** *Note: Ensure `prophet` (or `pystan` and `prophet`) is included in your `requirements.txt` file.*
    ```bash
    uv pip install -r requirements.txt
    ```

#### 3. Run the Notebook

1.  Start a Jupyter session from the project root directory:
    ```bash
    jupyter notebook av.ipynb
    ```
2.  Open the `av.ipynb` notebook in your browser and run all cells sequentially to execute the full analysis.

---

### 📈 Key Findings

* The **Real Price** of avocados shows an overall **slow upward trend**, even after accounting for general inflation.
* Strong **annual seasonality** is present, with prices typically peaking in Summer.
* The **ACF and PACF plots** confirm the time series is non-stationary and exhibits strong periodic correlation.
* The **Prophet model** was effectively used to decompose the time series and provide a reliable forecast that captures both the long-term trend and yearly seasonality.

---

### 📚 Dependencies

Dependencies are managed in `requirements.txt`. Key libraries include:

* `pandas`
* `pandas-datareader`
* `statsmodels`
* `prophet`
* `matplotlib`
* `seaborn`

---

