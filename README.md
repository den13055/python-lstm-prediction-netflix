# Netflix Stock Price Prediction

An application for predicting Netflix (NFLX) stock prices using an LSTM neural network. Implemented in Python with a web interface powered by Streamlit.

## 📌 Features

- Download historical Netflix stock price data from Yahoo Finance
- Visualization of historical closing prices
- Trained LSTM model (4-layer architecture) for forecasting
- Forecast for a user-specified number of days (1–10)
- Comparison of predicted and actual values ​​during the test period
- Evaluation of model accuracy using the RMSE metric

## 📁 Project Structure

| File | Description |
|------------------------|----------|
| `app.py` | Streamlit application with user interface |
| `Model_Creation.ipynb` | Jupyter notebook with model training |
| `Model_50.h5` | Trained model file (not included in the repository) |
| `requirements.txt` | List of Python dependencies |

## 🛠️ Technologies Used

- **Python 3.10+**
- **TensorFlow / Keras** – building and loading the LSTM model
- **Streamlit** – web interface
- **yfinance** – loading stock data
- **Pandas, NumPy** – data processing
- **Scikit-learn** – feature scaling (MinMaxScaler)
- **Matplotlib** – plotting

## 🚀 Installation and Run

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/netflix-stock-prediction.git
cd netflix-stock-prediction
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

3. **Prepare the model:**
- Make sure the trained model file `Model_50.h5` is in the project root.
- If it is not there, run the `Model_Creation.ipynb` notebook to train the model or download a pre-trained version.

4. **Run the application:**
```bash
streamlit run app.py
```

5. Open `http://localhost:8501` in your browser.

## 📈 Usage

- Select the number of days for the forecast using the slider (from 1 to 10).
- Click the **"Forecast"** button.
- The application will download current historical data, display a closing price chart, compare actual and predicted values ​​in the test section, display the RMSE, and generate a forecast for the selected period.

## 🧠 Model Training

- The model was trained on Netflix stock data from 2010 to the current date.

- Time step (window) — **50 days**.

- **LSTM architecture:**
4 LSTM layers (50, 60, 80, 120 neurons) with alternating Dropout layers for regularization.

- Optimizer: Adam, loss function: mean_squared_error.

- Forecasts for future days are built recursively: one day's forecast is inserted back into the window to generate subsequent values.

## ⚠️ Notes

- An internet connection is required for the application to run (data download via Yahoo Finance).
- This project is for educational and demonstration purposes only and should not be used for real trading without additional validation.

## 📄 License

MIT LICENSE
