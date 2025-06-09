
# Time-Series Forecasting and Semantic Search Platform Deployed on Google Cloud

This project presents a cloud-deployed, end-to-end data analytics and visualization platform for **forecasting GitHub repository issue trends** using **time series models (LSTM)** and powering a **semantic search dashboard** with meaningful repository insights. It integrates ML modeling, Flask API services, React dashboards, and GitHub API automation — all containerized and deployable on **Google Cloud**.

---

## 📁 Repository Structure

```
HW5_Murali_Pranav/
├── Part 1/
│   ├── 📓 GitHub_Repos_Issues_Forecasting_Pranav 2 years.ipynb
│   ├── 📁 doc/                  # Evaluation PDFs and comparison charts
│   └── 📁 src/
│       ├── flask/              # Flask backend API (Python)
│       ├── LSTM-forecast/      # LSTM model and forecasting logic
│       └── react/              # React frontend dashboard
├── Part 2/
│   ├── 📁 Pull_GitHub_Issues/  # Jupyter notebooks and Docker for GitHub API
│   ├── 📁 Push_GitHub_Issues/  # Push results to backend
│   └── 📁 Readme/              # Module-specific notes
├── 📄 videolink.txt.txt        # Video demo link
```

---

## 🎯 Project Objectives

- Forecast GitHub issues using time-series deep learning models (LSTM).
- Automate issue data collection and visualization across repos.
- Provide an interactive semantic dashboard using React.js.
- Deploy the solution on Google Cloud using containerization tools.

---

## 🛠️ Tech Stack

- **ML & Forecasting**: Python, TensorFlow/Keras, Pandas, Matplotlib
- **Backend**: Flask, REST APIs, Docker
- **Frontend**: React.js, Chart.js, Bootstrap
- **DevOps**: Docker Compose, Google Cloud Platform (GCP)
- **Data Source**: GitHub API
- **Visualization**: Multi-chart dashboards (stacked bars, line graphs, stats overlays)

---

## 🔍 Key Modules

### 🔹 LSTM Time Series Forecasting
- Predicts future GitHub issue trends using historical data.
- Implemented in `LSTM-forecast/app.py` and demonstrated in notebooks.
- Evaluation includes Accuracy, RMSE, and visual comparisons.

### 🔹 Semantic Visualization Dashboard (React)
- Displays metrics such as open issues, commits, forks, and stars.
- Allows selection of repos and time ranges with rich UX.
- Component-based React architecture for modular charts.

### 🔹 Flask Backend API
- Serves ML forecast data to frontend.
- Routes for repo metadata, LSTM predictions, and dynamic queries.
- Includes Dockerfile and requirement specs for deployment.

### 🔹 GitHub Data Pull/Push Automation
- Pull module fetches GitHub repo data using authenticated API.
- Push module syncs processed outputs to backend endpoints.

---

## 📊 Evaluation Artifacts

- 📘 `Output.pdf`: Forecast results and observations
- 📘 `Time-Series_Model_Comparison.pdf`: Model comparison report
- 📓 `Pull_Analytics_Pranav-checkpoint.ipynb`: GitHub API script
- 📓 `Push_GitHub_Issues.ipynb`: Data push pipeline

---

## ☁️ Google Cloud Deployment

> _Note: Deployment steps assume Docker and GCP SDK are installed and authenticated._

### 🔹 Step 1: Build Docker Images
```bash
docker build -t lstm-api ./src/flask
docker build -t dashboard-ui ./src/react
```

### 🔹 Step 2: Push to Google Container Registry
```bash
gcloud auth configure-docker
docker tag lstm-api gcr.io/YOUR_PROJECT_ID/lstm-api
docker tag dashboard-ui gcr.io/YOUR_PROJECT_ID/dashboard-ui
docker push gcr.io/YOUR_PROJECT_ID/lstm-api
docker push gcr.io/YOUR_PROJECT_ID/dashboard-ui
```

### 🔹 Step 3: Deploy via Google Cloud Run or GKE
```bash
gcloud run deploy lstm-api \
  --image gcr.io/YOUR_PROJECT_ID/lstm-api \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

Repeat for the `dashboard-ui` container.

---

## 🚀 Local Development Instructions

### 🧪 Run Forecast Notebook
```bash
jupyter notebook "GitHub_Repos_Issues_Forecasting_Pranav 2 years.ipynb"
```

### 🧩 Run Flask API
```bash
cd src/flask
pip install -r requirements.txt
python app.py
```

### 🖥️ Run React App
```bash
cd src/react
npm install
npm start
```

### 🐳 Run All Using Docker Compose
```bash
docker-compose up --build
```

---

## 🎥 Demo

Link to recorded walkthrough:  
📺 _Check `videolink.txt.txt` in the root directory_

---

## 👥 Contributors

- **Pranav Murali** – Full-stack development, LSTM modeling, dashboard integration  
*University of Illinois Chicago — Graduate Coursework Submission*

---

## 📄 License

Licensed under the **MIT License**.  
See [LICENSE](./LICENSE) for full details.

---

> 🚀 This project combines deep learning, cloud deployment, and interactive analytics — enabling intelligent forecasting of GitHub repositories with real-world impact.
