# 🔥 Forest Fire Weather Index (FWI) Prediction

A machine learning web application that predicts the **Fire Weather Index (FWI)** using weather and fire-weather parameters.

The application is built with **Flask** and uses a trained **Ridge Regression** model together with a saved **StandardScaler** for preprocessing.

---

## 🚀 Features

- 🌡️ Temperature-based prediction
- 💧 Relative Humidity input
- 💨 Wind Speed input
- 🌧️ Rainfall input
- 📊 Fire Weather Indicators:
  - FFMC
  - DMC
  - ISI
- 🔥 Fire classification input
- 🌍 Region selection
- 🤖 Ridge Regression model for prediction
- 📏 StandardScaler preprocessing
- 🖥️ Responsive Flask web interface
- 🎨 Modern dark-themed UI

---

## 🧠 Machine Learning Pipeline

The application takes **9 input parameters**:

| Parameter | Description |
|---|---|
| Temperature | Temperature in °C |
| RH | Relative Humidity (%) |
| Ws | Wind Speed |
| Rain | Rainfall |
| FFMC | Fine Fuel Moisture Code |
| DMC | Duff Moisture Code |
| ISI | Initial Spread Index |
| Classes | Fire / Not Fire classification |
| Region | Selected geographical region |

The input values are first transformed using the saved `StandardScaler`, then passed to the trained Ridge Regression model to generate the FWI prediction.

```text
User Input
    ↓
Flask Web Form
    ↓
Input Validation
    ↓
StandardScaler
    ↓
Ridge Regression Model
    ↓
FWI Prediction
    ↓
Web Interface
```

---

## 📁 Project Structure

```text
Forest-Fire-FWI-Prediction/
│
├── application.py
├── requirements.txt
├── README.md
│
├── models/
│   ├── ridge.pkl
│   └── scaler.pkl
│
└── templates/
    ├── home.html
    └── index.html
```

> Make sure the trained model files are available at `models/ridge.pkl` and `models/scaler.pkl`.

---

## 🛠️ Technologies Used

- Python
- Flask
- NumPy
- Pandas
- Scikit-learn
- HTML5
- CSS3
- Bootstrap
- Jinja2
- Pickle

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Forest-Fire-FWI-Prediction
```

### 2. Create a virtual environment

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Application

Start the Flask application:

```bash
python application.py
```

The application runs on:

```text
http://localhost:5001
```

Open the URL in your browser and enter the required weather parameters.

---

## 📊 Input Values

| Input | Range |
|---|---:|
| Temperature | 0 – 50 °C |
| Relative Humidity | 0 – 100 % |
| Wind Speed | 0 – 100 |
| Rain | 0 – 50 |
| FFMC | 0 – 101 |
| DMC | 0 – 300 |
| ISI | 0 – 20 |
| Classes | 0 = Not Fire, 1 = Fire |
| Region | 0 = Bejaia, 1 = Sidi-Bel Abbes |

---

## 🔥 Prediction

After submitting the form, the application:

1. Collects the nine parameters.
2. Converts the values to floating-point numbers.
3. Applies the saved StandardScaler.
4. Sends the transformed data to the Ridge Regression model.
5. Displays the predicted FWI value on the web page.

---

## 🌐 Routes

### Home

```text
GET /
```

Displays the main FWI prediction interface.

### Prediction

```text
GET /prediction
POST /prediction
```

The `POST` request receives the prediction parameters and returns the predicted FWI value.

---

## 🧪 Example

Example input:

```text
Temperature: 30
RH: 40
Ws: 15
Rain: 0
FFMC: 90
DMC: 100
ISI: 8
Classes: 1
Region: 0
```

The model processes these values and displays the resulting FWI prediction.

---

## 📦 Dependencies

```text
Flask
pandas
numpy
scikit-learn
```

Install them using:

```bash
pip install -r requirements.txt
```

---

## 🔐 Model Files

The application uses two serialized machine learning files:

```text
models/ridge.pkl
models/scaler.pkl
```

- `ridge.pkl` → Trained Ridge Regression model
- `scaler.pkl` → Fitted StandardScaler used for preprocessing

---

## 🎯 Project Objective

The goal of this project is to provide a simple web-based interface for estimating the **Fire Weather Index** from environmental and meteorological conditions using machine learning.

---

## 👨‍💻 Author

**Shivesh Parashar**

Computer Science Engineering Student  
Jaypee Institute of Information Technology (JIIT)

---

## 🚀 Future Improvements

- Add model performance metrics
- Add prediction history
- Add graphical visualization of weather parameters
- Add REST API endpoints
- Deploy the application to a cloud platform
- Add authentication and user accounts
- Add real-time weather data integration

---

## 📄 License

This project is intended for educational and demonstration purposes.
