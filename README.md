# Python CI/CD Pipeline on AWS

This project demonstrates a complete CI/CD (Continuous Integration / Continuous Deployment) pipeline that automatically builds, tests, and deploys a Python Flask web application to AWS EC2 using Jenkins, Docker, and Docker Hub.

---

## Workflow

**Flow:**  
`Git Push → Jenkins (Test) → Jenkins (Build) → Docker Hub (Push) → Jenkins (Deploy via SSH) → EC2 Server (Run)`

**Steps:**
1. Developer pushes new code to GitHub.  
2. Jenkins automatically triggers the pipeline.  
3. Runs `pytest` and `flake8` for testing and linting.  
4. Builds a Docker image and pushes it to **Docker Hub**.  
5. Deploys the latest image to a **separate EC2 Deploy Server** via SSH.  

---

## Features

- **Pipeline as Code:** Defined in `jenkinsfile`  
- **Automated Testing:** Runs pytest + flake8  
- **Containerized:** Uses Docker + docker-compose  
- **Two EC2 Servers:**  
  - Jenkins Server (CI/CD)  
  - Deploy Server (Production)  
- **Secure Deployments:** SSH key-based authentication  

---

## Tech Stack

| Category | Tools |
|-----------|-------|
| CI/CD | Jenkins |
| Cloud | AWS EC2 (Ubuntu 22.04) |
| Container | Docker, Docker Compose |
| Language | Python (Flask) |
| Testing | Pytest, Flake8 |
| Registry | Docker Hub |
| Source Control | Git, GitHub |

---

## Project Structure

```
.
├── app.py              # Flask app
├── test_app.py         # Unit tests
├── Dockerfile          # Multi-stage build
├── docker-compose.yml  # Deployment config
├── jenkinsfile         # CI/CD pipeline
├── requirements.txt    # Dependencies
└── README.md           # Documentation
```

---

## Screenshots

**1. Jenkins Pipeline Success:**
<img width="1498" height="961" alt="image" src="https://github.com/user-attachments/assets/575124ba-ad02-47d1-9a22-e01bd316f32c" />


**2. Application Running on EC2 Deploy Server:**
<img width="1498" height="961" alt="image" src="https://github.com/user-attachments/assets/ba67941c-6662-421b-b430-7cd080b43f97" />
