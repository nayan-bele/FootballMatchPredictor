# Football Expected Goal Predictor

A data-driven machine learning application that predicts the expected score of football matches using historical performance metrics. Built with **TensorFlow**, **Streamlit**, and **SQLite**.

## Overview
This project processes over 7,000 historical football matches to generate data-driven score forecasts. It utilizes a **multi-output neural regression architecture** that maps the average performance metrics of two opposing teams to specific home and away goal targets.

## Features
- **Automated Data Pipeline:** Cleans and structures raw CSV match data into a queryable SQLite database.
- **Neural Regression:** Uses TensorFlow to predict continuous goal values based on 48 high-dimensional match features, including team performance metrics and integrated betting odds.
- **Context-Aware Inference:** Incorporates position-aware feature methodology to accurately distinguish between home and away team performance dynamics.
- **Interactive Dashboard:** Provides a real-time web interface via Streamlit to input teams and generate score predictions.

## Tech Stack
- **Language:** Python 3.x
- **ML Framework:** TensorFlow/Keras
- **Data Processing:** Pandas, NumPy
- **Database:** SQLite3
- **Deployment:** Streamlit

## Project Structure
- `data_loader.py` — Handles ingestion, cleaning, and preprocessing of raw CSV match data into the database.
- `train_ml.py` — Executes neural network training and saves the model.
- `engine.py` — Performs SQL-based data retrieval and real-time model inference.
- `app.py` — Serves the interactive user interface for match predictions.
- `global_vault/` — Contains all raw CSV dataset files for supported leagues.

## How to Run

### Prerequisites
Make sure you have Python 3.x installed. Then install all required dependencies:

```bash
pip install -r requirements.txt
```

### Step 1 — Initialize the Database
Load and preprocess the raw CSV data into a local SQLite database:

```bash
python data_loader.py
```

### Step 2 — Train the Model
Train the neural network on the processed match data:

```bash
python train_ml.py
```

### Step 3 — Launch the App
Start the Streamlit web interface to make predictions:

```bash
streamlit run app.py
```

Once running, open your browser and navigate to `http://localhost:8501`. Select a home and away team from the dropdowns and click **Predict** to generate a score forecast.
