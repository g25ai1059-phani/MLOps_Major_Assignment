# End-to-End MLOps Pipeline using GitHub Actions, Docker and Kubernetes

## Project Overview

This project demonstrates the implementation of a complete MLOps pipeline using the Olivetti Faces dataset from Scikit-Learn. The pipeline covers model development, automated CI/CD, Docker containerization, Docker Hub integration, and Kubernetes deployment with self-healing capabilities.

The machine learning model is trained using a Decision Tree Classifier and deployed as a Flask web application.

---

## Project Objectives

* Train a machine learning model using the Olivetti Faces dataset.
* Automate model training and testing using GitHub Actions.
* Containerize the application using Docker.
* Push Docker images to Docker Hub.
* Deploy the application on Kubernetes.
* Demonstrate Kubernetes self-healing and replica management.

---

## Technology Stack

| Component          | Technology               |
| ------------------ | ------------------------ |
| Language           | Python 3.11              |
| Dataset            | Olivetti Faces           |
| ML Framework       | Scikit-Learn             |
| Model              | Decision Tree Classifier |
| Web Framework      | Flask                    |
| Version Control    | Git                      |
| Repository         | GitHub                   |
| CI/CD              | GitHub Actions           |
| Containerization   | Docker                   |
| Container Registry | Docker Hub               |
| Orchestration      | Kubernetes               |
| Platform           | Docker Desktop           |

---

## Git Branching Strategy

The repository follows the required branching strategy:

### main

Initial repository setup including:

* README.md
* .gitignore

### dev

Model development and CI/CD implementation:

* train.py
* test.py
* GitHub Actions workflow

### docker_cicd

Deployment implementation:

* Flask application
* Dockerfile
* Docker Hub integration
* Kubernetes deployment

---

## Project Structure

```text
MLOps_Major_Assignment/
│
├── train.py
├── test.py
├── app.py
├── savedmodel.pth
├── requirements.txt
├── Dockerfile
├── .dockerignore
├── deployment.yaml
├── service.yaml
├── README.md
│
├── templates/
│   └── index.html
│
└── .github/
    └── workflows/
        └── ci.yml
```

---

## Model Training

The training script:

1. Loads the Olivetti Faces dataset.
2. Splits data into:

   * 70% Training
   * 30% Testing
3. Trains a Decision Tree Classifier.
4. Saves the model as:

```text
savedmodel.pth
```

Run training:

```bash
python train.py
```

---

## Model Testing

The testing script:

1. Loads the trained model.
2. Evaluates model performance.
3. Displays classification metrics and accuracy.

Run testing:

```bash
python test.py
```

---

## GitHub Actions CI/CD

The CI pipeline automatically:

* Checks out repository code.
* Installs dependencies.
* Executes train.py.
* Generates savedmodel.pth.
* Executes test.py.
* Displays model accuracy.

Workflow file:

```text
.github/workflows/ci.yml
```

---

## Flask Application

The Flask web application provides a user interface for prediction.

Features:

* Accept image index input.
* Load trained model.
* Predict face class.
* Display predicted person ID.

Run locally:

```bash
python app.py
```

Application URL:

```text
http://localhost:5000
```

---

## Docker Containerization

Build Docker image:

```bash
docker build -t olivetti-face-app .
```

Run container:

```bash
docker run -p 5000:5000 olivetti-face-app
```

Application URL:

```text
http://localhost:5000
```

---

## Docker Hub Repository

Docker Image:

```text
phanipervela/olivetti-face-app:v1
```

Docker Hub Repository:

```text
https://hub.docker.com/r/phanipervela/olivetti-face-app
```

Push image:

```bash
docker push phanipervela/olivetti-face-app:v1
```

---

## Kubernetes Deployment

Deploy application:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

Verify deployment:

```bash
kubectl get deployments
kubectl get pods
kubectl get svc
```

---

## Kubernetes Self-Healing

Deployment configuration uses:

```yaml
replicas: 3
```

Delete a pod:

```bash
kubectl delete pod <pod-name>
```

Kubernetes automatically creates a replacement pod to maintain the desired replica count.

---

## Results

Successfully implemented:

✅ Machine Learning Model Training

✅ Automated CI/CD using GitHub Actions

✅ Docker Containerization

✅ Docker Hub Integration

✅ Kubernetes Deployment

✅ Service Exposure

✅ Self-Healing Demonstration

---

## Learning Outcomes

* Git Branching Strategy
* Continuous Integration
* Docker Containerization
* Container Registry Management
* Kubernetes Deployment
* Replica Management
* Self-Healing Infrastructure
* End-to-End MLOps Workflow

---

## Author

**Phani Pramod Pervela**

PGD in Artificial Intelligence

MLOps Major Assignment
