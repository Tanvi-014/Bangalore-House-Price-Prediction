# 🏡 Bangalore House Price Prediction

A full-stack machine learning web application that predicts Bangalore house prices based on location, square footage, BHK, and bathrooms — built with Python, Scikit-learn, Flask, HTML, CSS, JavaScript, and jQuery.

---

## Features

📍 Dynamic location dropdown loaded from backend  
📐 Square footage based prediction  
🛏️ BHK selection support  
🛁 Bathroom count support  
🤖 Machine learning powered price prediction  
⚡ Fast Flask REST API backend  
🌐 Interactive frontend UI  
📦 Serialized trained ML model using Pickle  
📂 JSON-based metadata loading for locations  

---

## Tech Stack

| Layer | Tech |
|------|------|
| Machine Learning | Python, NumPy, Pandas, Scikit-learn |
| Visualization | Matplotlib |
| Backend | Flask |
| Frontend | HTML, CSS, JavaScript, jQuery |
| API Testing | Postman |
| Model Storage | Pickle |
| Metadata Storage | JSON |

---

## Project Structure

```bash
blrhouseprediction/
├── client/
│   ├── app.html              # Frontend UI
│   ├── app.css               # Styling
│   └── app.js                # Frontend logic + API calls
│
├── server/
│   ├── server.py             # Flask backend
│   ├── util.py               # Model loading + prediction logic
│   └── artifacts/
│       ├── columns.json      # Feature metadata
│       └── bangalore_home_prices_model_pickle
│
├── Bengaluru_House_Data.csv  # Dataset
├── model.ipynb               # Training notebook
└── README.md
```

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/bangalore-house-price-prediction.git
cd bangalore-house-price-prediction
```

---

### 2. Create virtual environment

```bash
python -m venv venv
```

Activate:

**Windows**
```bash
venv\Scripts\activate
```

**Mac/Linux**
```bash
source venv/bin/activate
```

---

### 3. Install dependencies

```bash
pip install flask numpy pandas scikit-learn matplotlib jupyter
```

---

### 4. Start backend server

```bash
cd server
python server.py
```

Server runs on:

```bash
http://127.0.0.1:5000
```

---

### 5. Start frontend

Open:

```bash
client/app.html
```

using **Live Server** (VS Code recommended)

Frontend runs on:

```bash
http://127.0.0.1:5500
```

---

## How It Works

### Machine Learning Pipeline

The model pipeline includes:

- Data cleaning
- Missing value handling
- Outlier removal
- Feature engineering
- Location dimensionality reduction
- One-hot encoding
- Train/test split
- Model evaluation using GridSearchCV
- Final Linear Regression model training
- Model export using Pickle

---

### Backend API

Flask loads:

- trained ML model
- feature columns
- location metadata

Endpoints:

#### GET `/get_location_names`

Returns all available Bangalore locations.

Example response:

```json
{
  "locations": [
    "1st phase jp nagar",
    "electronic city",
    "rajaji nagar"
  ]
}
```

---

#### POST `/predict_home_price`

Predicts house price.

Request body:

```json
{
  "total_sqft": 1000,
  "location": "1st phase jp nagar",
  "bhk": 2,
  "bath": 2
}
```

Response:

```json
{
  "estimated_price": 83.87
}
```

---

### Frontend Flow

User:

- enters square footage
- selects BHK
- selects bathrooms
- chooses location
- clicks **Estimate Price**

Frontend sends AJAX request to Flask backend.

Backend:

- preprocesses input
- creates feature vector
- runs prediction
- returns estimated price

Frontend displays:

```bash
₹83.87 Lakhs
```

---

## API Testing

Backend endpoints were tested using Postman.

Example tested routes:

```bash
GET  http://127.0.0.1:5000/get_location_names
POST http://127.0.0.1:5000/predict_home_price
```

---

## Challenges Faced

During development:

- Jupyter kernel setup issues
- Python virtual environment configuration
- Flask dependency/import issues
- Scikit-learn version compatibility changes
- Route debugging
- Form-data request formatting in Postman
- Frontend/backend port mismatch
- Model artifact loading bugs
- Dynamic dropdown integration

---

## Future Improvements

🚀 Deploy to Render / Railway / AWS  
📱 Fully responsive mobile UI  
📈 Better regression models (XGBoost / Random Forest)  
🗺️ Map-based location picker  
📊 Price trend visualizations  
🧠 Smarter feature engineering  
☁️ Public API deployment  

---

## Learning Outcomes

This project helped strengthen understanding of:

- end-to-end ML workflows
- regression modeling
- feature engineering
- Flask API development
- frontend-backend integration
- AJAX requests
- debugging deployment issues
- serving trained machine learning models

---
