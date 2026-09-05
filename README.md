# AAPL Stock Price Prediction Using LSTM

A time-series forecasting project that uses an **LSTM (Long Short-Term Memory)** neural network to predict Apple's (AAPL) stock closing prices based on historical market data.

## 📌 Project Overview

This project uses historical **Apple (AAPL)** stock data from **2015 to 2024** and trains an LSTM model to predict the next day's closing price.

The model looks at the previous **60 trading days** and uses those prices to predict the following day's closing price.

The project demonstrates how LSTM networks can be applied to sequential financial data.

## 🧠 How It Works

The project follows these steps:

1. **Download Stock Data**

   * Uses `yfinance` to download AAPL historical stock data.
   * Data is collected from January 1, 2015, to January 1, 2025.

2. **Select Closing Prices**

   * Only the daily closing price is used for prediction.

3. **Normalize the Data**

   * Uses `MinMaxScaler` to scale prices between `0` and `1`.
   * Scaling helps the LSTM train more effectively.

4. **Create Sequences**

   * Uses the previous 60 trading days as input.
   * The next trading day's closing price becomes the target.

5. **Split the Data**

   * 80% of the sequences are used for training.
   * 20% are used for testing.
   * The split is chronological because this is time-series data.

6. **Build the LSTM Model**

   * LSTM layer with 50 units.
   * Dense output layer with one neuron.

7. **Train the Model**

   * Optimizer: Adam
   * Loss function: Mean Squared Error
   * Epochs: `10`
   * Batch size: `32`

8. **Make Predictions**

   * The trained model predicts prices for the test period.
   * Predictions are converted back from the scaled values to actual USD prices.

9. **Compare Results**

   * Prints sample actual and predicted prices.
   * Creates a graph comparing actual vs predicted prices.

## 🏗️ Model Architecture

```text
Historical Closing Prices
          ↓
Previous 60 Trading Days
          ↓
       LSTM
      50 Units
          ↓
       Dense
       1 Unit
          ↓
Predicted Closing Price
```

## 🛠️ Technologies Used

* Python
* NumPy
* Matplotlib
* yFinance
* Scikit-learn
* TensorFlow
* Keras
* LSTM
* Time-Series Forecasting

## 📂 Project Structure

```text
aapl-stock-price-prediction-lstm/
│
├── aapl_stock_prediction.py
├── requirements.txt
└── README.md
```

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/AbdullahKamal9/aapl-stock-price-prediction-lstm.git
```

Move into the project directory:

```bash
cd aapl-stock-price-prediction-lstm
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## ▶️ Run the Project

Run the Python script:

```bash
python aapl_stock_prediction.py
```

The script will:

* Download AAPL stock data.
* Preprocess and normalize the data.
* Train the LSTM model.
* Predict test-set prices.
* Print actual vs predicted prices.
* Display an actual vs predicted price graph.

## 📊 Sample Output

The program prints a comparison similar to:

```text
📊 Sample of Actual vs Predicted Prices:
=======================================
Day 1: Actual = 180.25 | Predicted = 178.91
Day 2: Actual = 181.50 | Predicted = 180.72
...
```

The exact values will change depending on the downloaded data and model training.

## 📈 Visualization

The project generates a graph containing:

* **Actual Price** — real AAPL closing prices from the test set.
* **Predicted Price** — prices predicted by the LSTM model.

This makes it easier to visually compare the model's predictions with the actual market movement.

## 📚 What I Learned

This project demonstrates:

* Downloading financial data using `yfinance`
* Time-series data preprocessing
* Min-Max normalization
* Creating sliding-window sequences
* Reshaping data for LSTM networks
* Building LSTM models with TensorFlow/Keras
* Training neural networks on sequential data
* Making predictions on unseen data
* Inverse transforming normalized predictions
* Comparing predicted and actual values
* Visualizing time-series predictions

## ⚠️ Important Note

This project is for **educational purposes only**.

Stock prices are affected by many factors, including company performance, economic conditions, market sentiment, news, interest rates, and unexpected events.

An LSTM model trained only on historical closing prices cannot reliably predict future market movements and should **not be treated as financial advice or a trading system**.

## 👨‍💻 Author

**Abdullah Kamal**

GitHub: https://github.com/AbdullahKamal9
