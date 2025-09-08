# XOps Microchallenge App

This project is a static website served by **nginx**, designed for the CI/CD + Argo CD microchallenge. It demonstrates a simple, production-ready workflow for deploying static content using modern DevOps practices.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Local Development](#local-development)
- [Building & Running with Docker](#building--running-with-docker)
- [CI/CD Pipeline](#cicd-pipeline)
- [Argo CD Deployment](#argo-cd-deployment)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview
This repository contains a static website (HTML/CSS/JS) that is served using an nginx container. The project is intended to be used as a demonstration for:
- Building containerized static sites
- Automating deployments with CI/CD pipelines
- Managing deployments with Argo CD

## Features
- **Static Content**: Simple, fast, and secure static site
- **nginx**: Used as the web server for production-grade performance
- **Dockerized**: Easily build and run the site in a container
- **CI/CD Ready**: Integrates with modern CI/CD tools (e.g., GitHub Actions, GitLab CI)
- **Argo CD Compatible**: Designed for GitOps workflows and deployment via Argo CD

## Project Structure
```
├── Dockerfile         # Docker build instructions for nginx static site
├── index.html         # Main static HTML file
├── readme.md          # Project documentation
```

## Getting Started

### Prerequisites
- [Docker](https://www.docker.com/get-started) installed
- (Optional) [kubectl](https://kubernetes.io/docs/tasks/tools/) and [Argo CD CLI](https://argo-cd.readthedocs.io/en/stable/cli_installation/)

## Local Development
You can edit `index.html` directly and preview changes using any static file server or by running nginx locally.

## Building & Running with Docker

1. **Build the Docker image:**
	```sh
	docker build -t xops-microchallenge-app .
	```
2. **Run the container:**
	```sh
	docker run -d -p 8080:80 xops-microchallenge-app
	```
3. **Access the site:**
	Open [http://localhost:8080](http://localhost:8080) in your browser.

## CI/CD Pipeline
This project is designed to be integrated with CI/CD tools such as GitHub Actions, GitLab CI, or Jenkins. A typical pipeline will:
- Build the Docker image
- Run tests (if any)
- Push the image to a container registry
- Deploy to a Kubernetes cluster (optionally via Argo CD)

> **Note:** Example pipeline YAMLs can be added in `.github/workflows/` or `.gitlab-ci.yml` as needed.

## Argo CD Deployment
To deploy this app using Argo CD:

1. **Push your Docker image to a registry** (e.g., Docker Hub, GitHub Container Registry).
2. **Create a Kubernetes manifest** (e.g., `deployment.yaml`, `service.yaml`) that pulls your image.
3. **Register your app in Argo CD:**
	- Point Argo CD to your Git repository and manifest path.
	- Sync the application to deploy.

> For more details, see the [Argo CD documentation](https://argo-cd.readthedocs.io/).

