# Streamlit Student Data Processing App

Simple Streamlit application to upload, process, and store student data from CSV files (now with PostgreSQL backend!).

## What I Built

- Streamlit app (`data_process_db.py`) — handles CSV upload, processing, visualization, and saving to DB
- Dockerfile based on lightweight `python:3.11-slim-bookworm` image
- Dependencies installed from `requirements.txt` (cached layer for faster rebuilds)
- Port 8501 exposed
- Multi-architecture Docker image (supports linux/amd64 and linux/arm64)
- Image pushed to Docker Hub: `esestephen/multicontainer-app:v0`
- Added `compose.yml` for multi-container setup: Streamlit app + PostgreSQL database

## Build and Run the Docker Image (Single Container)

### Build (multi-platform)

Built for both Intel/AMD and Apple Silicon compatibility:

```bash
# First time only (if you haven't set up buildx)
docker buildx create --use

# Build & push directly to Docker Hub
docker buildx build \
  --platform linux/arm64,linux/amd64 \
  -t esestephen/multicontainer-app:v0 \
  --push .
```

## I added a compose.yml to run the full stack: the Streamlit app + a persistent PostgreSQL database.

Start everything:

```bash
# Start 
docker compose up -d

# Stop
docker compose down
# Add -v to also remove the database volume (careful!)
# docker compose down -v
```

