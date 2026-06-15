# Pwani Cloud Run App

## Overview

This project is a containerized Python Flask application deployed on Google Cloud Run. It demonstrates serverless container deployment using Docker and Google Cloud Platform.

## Features

The application exposes the following endpoints:

### `/`

Returns a welcome message and developer name.

Example response:

```json
{
  "message": "Welcome to Cloud Run",
  "Name": "Sarah Happiness"
}
```

### `/health`

Returns the health status of the application.

Example response:

```json
{
  "status": "healthy"
}
```

### `/info`

Returns the container hostname and current timestamp.

Example response:

```json
{
  "hostname": "<container hostname>",
  "timestamp": "<current timestamp>"
}
```

## Technologies Used

* Python 3
* Flask
* Docker
* Gunicorn
* Google Cloud Run

## Project Structure

```text
studyjam-cloudrun-app/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
```

## Running Locally

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
python app.py
```

The application runs on:

```text
http://localhost:8080
```

## Docker Commands

Build the Docker image:

```bash
docker build -t studyjam-cloudrun-app .
```

Run the container:

```bash
docker run -p 8080:8080 studyjam-cloudrun-app
```

## Google Cloud Run Deployment

Deploy the application using:

```bash
gcloud run deploy pwani-cloudrun-app --source . --platform managed --region us-central1 --allow-unauthenticated
```

## Author

 