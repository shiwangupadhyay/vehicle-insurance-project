# 🚀 MLOps Project: End-to-End Deployment & Automation

## 📌 Overview
This project is a complete **MLOps Pipeline** designed to showcase end-to-end model development, deployment, and automation. It features **data ingestion, validation, transformation, model training, evaluation, and deployment**, all integrated with **MongoDB, AWS, Docker, and CI/CD pipelines**.

---
## 📂 Project Structure
```
📦 MLOps-Project
├── 📜 setup.py  # Package setup
├── 📜 pyproject.toml  # Dependency management
├── 📂 src
│   ├── 📂 components  # Data ingestion, validation, transformation, training, etc.
│   ├── 📂 configuration  # MongoDB and AWS connections
│   ├── 📂 entity  # Data entities and schemas
│   ├── 📂 utils  # Helper functions
│   ├── 📂 pipelines  # Model pipeline & inference
├── 📂 notebooks  # EDA & MongoDB operations
├── 📂 static & template  # Web UI assets
├── 📜 requirements.txt  # Project dependencies
├── 📜 Dockerfile  # Containerization
├── 📜 .github/workflows/aws.yaml  # CI/CD Pipeline
└── 📜 README.md  # Project Documentation
```

---
## 🛠️ Getting Started

### 🔹 1. Project Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/mlops-project.git
   cd mlops-project
   ```
2. Create the project template:
   ```bash
   python template.py
   ```
3. Setup local package imports:
   ```bash
   # Modify setup.py & pyproject.toml accordingly
   ```
4. Create & activate a virtual environment:
   ```bash
   conda create -n vehicle python=3.10 -y
   conda activate vehicle
   ```
5. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
6. Verify package installation:
   ```bash
   pip list
   ```

---
## 📦 MongoDB Setup
1. **Sign up** on [MongoDB Atlas](https://www.mongodb.com/atlas) and create a new project.
2. **Create a cluster** (M0 service, default settings).
3. **Set up database access:**
   - Create a user with username & password.
   - Allow network access: `0.0.0.0/0` (accessible from anywhere).
4. **Get Connection String:**
   - Select **Python Driver (3.6 or later)**.
   - Copy & save connection string (replace `<password>`).
5. **Push Data to MongoDB:**
   - Create `notebook/mongoDB_demo.ipynb`.
   - Load dataset and insert into MongoDB.
   - Verify data via **MongoDB Atlas > Browse Collections**.

---
## 📌 Logging & Exception Handling
- Implemented logging & exception handling in `logger.py` and `exception.py`.
- Tested using `demo.py`.

---
## 📊 Data Ingestion
- **MongoDB Connection** → Fetch Data → Convert to DataFrame.
- Configuration in `configuration.mongo_db_connections.py`.
- **Run data ingestion pipeline:**
  ```bash
  python demo.py  # Ensure MongoDB connection URL is set first
  ```

---
## 🔎 Data Validation & Transformation
- Validate dataset schema using `config.schema.yaml`.
- Implement transformation logic in `entity.estimator.py`.
- Follow **step-by-step pipeline execution**.

---
## 📈 Model Training & Evaluation
1. **Train the Model**
   ```bash
   python training_pipeline.py
   ```
2. **Model Evaluation & AWS Setup:**
   - Configure **AWS IAM User & S3 bucket**.
   - Store models in `my-model-mlopsproj100` S3 bucket.
   - Implement storage logic in `aws_storage` and `s3_estimator.py`.

---
## 🛠️ Deployment & CI/CD Setup
### 🔹 AWS & Docker Setup
1. **Create AWS IAM User & ECR Repository**
2. **Setup EC2 Instance (Ubuntu 24.04, T2 Medium)**
3. **Install Docker in EC2:**
   ```bash
   sudo apt-get update -y
   sudo apt-get upgrade -y
   curl -fsSL https://get.docker.com -o get-docker.sh
   sudo sh get-docker.sh
   sudo usermod -aG docker ubuntu
   newgrp docker
   ```

### 🔹 GitHub Actions & Self-Hosted Runner
1. **Set up Runner in EC2**
   - Configure GitHub self-hosted runner (`./run.sh`).
   - Add **AWS Credentials & ECR Repo** as **GitHub Secrets**.

2. **Trigger CI/CD Pipeline**
   - Push code to GitHub.
   - Actions workflow (`.github/workflows/aws.yaml`) will deploy.

### 🔹 Access the Web App
- Open **EC2 Security Settings** → **Allow Port 5080**.
- Run the app in EC2:
  ```bash
  python app.py
  ```
- Open browser:
  ```
  http://<public-ip>:5080
  ```

---
## 🏆 Key Features
✅ **End-to-End MLOps Pipeline** (Data Ingestion → Deployment)  
✅ **MongoDB Atlas Integration**  
✅ **Model Storage on AWS S3**  
✅ **Automated CI/CD with GitHub Actions**  
✅ **Self-Hosted Runner on EC2**  
✅ **Dockerized Application**  
✅ **Scalable & Production-Ready**  

---
## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---
## 📞 Contact
📧 Email: shiwangupadhyay8@gmail.com.com  
🖥️ GitHub: [https://github.com/shiwangupadhyay/]

---
## 📜 License
This project is **MIT Licensed**.

---
🚀 **Happy Coding!** 🎯
