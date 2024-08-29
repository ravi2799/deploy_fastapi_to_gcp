# Deploy Fastapi on gcr

1. docker build -t name .
2. docker push name
3. gcloud auth login
4. gcloud config set project project_id
5. gcloud artifacts repositories create demoregistry --repository-format=docker --location=us-central1 --description="fastapi”
6. gcloud builds submit --region=us-central1 --tag us-central1-docker.pkg.dev/project_id/demoregistry/name
7. gcloud run deploy --image=us-central1-docker.pkg.dev/project_id/demoregistry/name
