# Pwani Cloud Run App

## Overview

This is a containerized **Python Flask application** deployed on **Google Cloud Run** using Docker.
It demonstrates serverless deployment, CI/CD-ready containerization, and basic API endpoint design.

---

## Features

The application exposes the following endpoints:

### `/`

Returns a welcome message and developer name.

**Response:**

```json
{
  "message": "Welcome to Cloud Run",
  "Name": "Sarah Happiness"
}
```

---

### `/health`

Returns the health status of the application.

**Response:**

```json
{
  "status": "healthy"
}
```

---

### `/info`

Returns runtime information such as container hostname and timestamp.

**Response:**

```json
{
  "hostname": "<container hostname>",
  "timestamp": "<current timestamp>"
}
```

---

## Technologies Used

* Python 3
* Flask
* Gunicorn
* Docker
* Google Cloud Run
* Google Cloud Build
* Artifact Registry

---

## Project Structure

```text
studyjam-cloudrun-app/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## Prerequisites

Before deploying, ensure the following are set up:

### Enable required Google Cloud APIs

```bash
gcloud services enable run.googleapis.com cloudbuild.googleapis.com artifactregistry.googleapis.com
```

### Requirements

* Google Cloud Project
* Google Cloud CLI installed
* Docker installed (for local testing)
* Authenticated gcloud session

---

## Running Locally

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run the application

```bash
python app.py
```

App runs at:

```
http://localhost:8080
```

---

## Docker Commands

### Build image

```bash
docker build -t pwani-cloudrun-app .
```

### Run container

```bash
docker run -p 8080:8080 pwani-cloudrun-app
```

---

## Google Cloud Run Deployment

Deploy directly from source:

```bash
gcloud run deploy pwani-cloudrun-app \
  --source . \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

---

## Notes

* Ensure billing is enabled on your GCP project
* Artifact Registry is used for storing container images
* Cloud Build automatically builds the Docker image during deployment

---

## Author

**Sarah Happiness**

 