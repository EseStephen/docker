# My Streamlit Data Processing App

Just a simple Streamlit app I built for processing/exploring data

## What I Did

- Wrote a basic Streamlit app (lives in `data_process.py`)
- Created a **Dockerfile** using a lightweight Python base image (`python:3.11-slim-bookworm`)
- Made sure dependencies install first (from `requirements.txt`) for good caching
- Exposed port 8501 (Streamlit's default)
- Built a **multi-architecture** image so it works on both Intel/AMD (linux/amd64) and Apple Silicon (linux/arm64) machines
- Pushed it to Docker Hub as `esestephen/my-streamlit-app:v0`
- Can run the container locally or anywhere that pulls from Docker Hub
