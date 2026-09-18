# Steps provided by Claude on how to make this project

## Step 1: Train a model and track it (MLflow)
Use a single-table dataset like the UCI Default of Credit Card Clients (30,000 rows, one CSV). Write a plain Python script that trains a simple model with scikit-learn. Log every run to MLflow so you can compare settings and scores side by side.
Concept you learn is experiment tracking. "Which version of the model is best, and how was it made?"

## Step 2: Save and version the model (MLflow Model Registry)
Register your best model in MLflow and mark it as "production." When you train a better one, promote the new version instead.
Concept you learn is model versioning. Knowing exactly which model is live and being able to roll back.

## Step 3: Serve the model as an API (FastAPI)
Write a small FastAPI app that loads the production model and has one endpoint. You send it a customer's details, it returns the chance they won't repay.
Concept you learn is model serving. Turning a file into something other apps can use.

## Step 4: Package and deploy it (Docker and Kubernetes)
Put the API in a Docker image and deploy it to kind or k3s with a Deployment and a Service. Add a simple GitHub Actions workflow that runs a few unit tests and builds the image.
Concept you learn is deployment and CI. This is where your existing Kubernetes experience shines.

## Step 5: Monitor it (Prometheus metrics and a drift check)
Expose basic metrics from the API (request count, latency, prediction values) and view them in Grafana. Then write a small script that compares new incoming data against the training data and flags when they look different.