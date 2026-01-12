# Python Docker App

A simple Flask web application with automated Docker build and deployment to Google Artifact Registry.

## 🚀 Features

- Flask REST API with multiple endpoints
- Docker containerization
- Automated CI/CD with GitHub Actions
- Google Cloud Artifact Registry integration

## 📋 API Endpoints

- `GET /` - Welcome message with timestamp
- `GET /health` - Health check endpoint
- `GET /info` - Application and environment information

## 🛠️ Local Development

### Run Locally (without Docker)

```bash
# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

Visit: `http://localhost:8000`

### Run with Docker

```bash
# Build the image
docker build -t python-app:latest .

# Run the container
docker run -p 8000:8000 python-app:latest
```

Visit: `http://localhost:8000`

## 🔐 GitHub Secrets Setup

Before pushing to GitHub, add the following secret to your repository:

1. Go to: `Settings` → `Secrets and variables` → `Actions`
2. Click `New repository secret`
3. Name: `GCP_SA_KEY`
4. Value: Your Google Cloud service account JSON key

## 📦 Deployment

The app automatically builds and pushes to Google Artifact Registry when you push to the `main` branch.

**Registry URL:** `asia-south1-docker.pkg.dev/pradhi-shared-envs/docker-images/python-app:latest`

## 🏗️ Project Structure

```
.
├── .github/
│   └── workflows/
│       └── build.yaml          # CI/CD workflow
├── app.py                      # Flask application
├── requirements.txt            # Python dependencies
├── Dockerfile                  # Docker configuration
├── .dockerignore              # Docker ignore rules
└── README.md                  # This file
```

## 📝 Next Steps

1. Add `GCP_SA_KEY` secret to GitHub
2. Commit and push to GitHub
3. Check GitHub Actions for build status
4. Deploy your container from Artifact Registry
