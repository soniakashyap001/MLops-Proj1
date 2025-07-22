# 🚗 MLOps Project: Vehicle Insurance Price Prediction

This project implements a full end-to-end MLOps pipeline to predict vehicle insurance prices. It demonstrates data ingestion from MongoDB, model training, and automated deployment using GitHub Actions, Docker, and AWS services (EC2, ECR, S3).

---

## 🔧 Tech Stack

- **ML & Data Tools**: Python, scikit-learn, Pandas, NumPy  
- **APIs & Backend**: FastAPI, MongoDB Atlas, Pymongo  
- **MLOps**: GitHub Actions, Docker, Amazon EC2, ECR, S3  
- **CI/CD**: Self-hosted GitHub Runner on EC2 for Continuous Deployment  
- **Project Structure**: setup.py, pyproject.toml, modular pipeline architecture

---

## 📦 Workflow Overview

1. **Data Ingestion**  
   - Reads raw vehicle insurance data  
   - Pushes to MongoDB Atlas  
   - Retrieves and transforms into DataFrame

2. **Model Training**  
   - Data validation, transformation, and training pipeline  
   - Model stored locally and optionally pushed to S3

3. **Prediction API**  
   - FastAPI app serves real-time predictions  
   - API exposed via port `:5000` on EC2 instance

4. **CI/CD with GitHub Actions**  
   - On `push` to `main`, GitHub builds Docker image  
   - Pushes to Amazon ECR  
   - EC2 self-hosted runner pulls image and serves FastAPI app

---

## 🚀 How to Run (Locally)

```bash
# Step 1: Clone the repo
git clone https://github.com/soniakashyap001/MLops-Proj1.git
cd MLops-Proj1

# Step 2: Create environment & install packages
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt

# Step 3: Set MongoDB and AWS credentials as environment variables
export MONGODB_URL="your_connection_string"
export AWS_ACCESS_KEY_ID="your_key"
export AWS_SECRET_ACCESS_KEY="your_secret"

# Step 4: Run FastAPI app
python app.py


🌐 CI/CD Deployment (Auto-Triggered)
Docker builds and pushes image to Amazon ECR
EC2 instance with self-hosted runner pulls latest image
FastAPI app is auto-deployed and served on http://<EC2-IP>:5000

MLops-Proj1/
├── app.py                  # FastAPI prediction API
├── Dockerfile              # Image build configuration
├── .github/workflows/      # GitHub Actions CI/CD pipeline
├── requirements.txt        # Python dependencies
├── src/                    # Modular ML components
├── templates/              # Frontend templates for API UI
├── static/                 # CSS and UI assets
└── README.md               # Project overview


📬 Contact
For questions or collaboration, reach out on LinkedIn.

https://www.linkedin.com/in/sonia-kashyap-56990320/

⭐ Give the repo a star if you found it helpful!
