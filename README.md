# Faceo Analytics — IllumiNet Low-Light Emotion Recognition Microservice

Microservice running on default Port 8006 as part of the FACEO Facial Intelligence Platform.

## Features
- **Endpoint**: Microservice API for IllumiNet Low-Light Emotion Recognition Microservice
- **Container**: Production-ready Dockerfile optimized for Google Cloud Run
- **Port**: Supports dynamic `$PORT` environment variable (defaults to 8006)
- **Cost**: Supports Scale-to-Zero (`min-instances = 0`) and request-based CPU allocation on GCP

## Local Run
```bash
pip install -r requirements.txt
python main.py
```

## Docker Build & Run
```bash
docker build -t lowlight-emotion-recognition-api .
docker run -p 8006:8006 -e PORT=8006 lowlight-emotion-recognition-api
```

## GCP Cloud Run Deployment
```bash
gcloud run deploy lowlight-emotion-recognition-api \
  --source . \
  --region asia-southeast1 \
  --min-instances 0 \
  --max-instances 1 \
  --memory 1Gi --cpu 1 \
  --cpu-throttling \
  --allow-unauthenticated
```
