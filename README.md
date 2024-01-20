# Continuous Deployment Project

## Overview
This repository contains the code for our Continuous Deployment (CD) pipeline. The pipeline uses Jenkins to automate the deployment process. The deployment is parameterized, allowing us to select specific commits for deployment.

## Jenkins Pipeline
The Jenkins pipeline is configured to build with parameters. This means you can select a specific commit for deployment. This commit corresponds to a git commit hash.

## Docker
We use Docker to containerize our application. Each commit corresponds to a Docker image that is hosted on Docker Hub. You can select a specific Docker image for deployment by choosing the corresponding commit in the Jenkins pipeline.

## Helm
Helm is a package manager for Kubernetes that helps deploy complex applications by bundling necessary resources into Charts. These charts contain all the information needed to run an application on a cluster. In our deployment process, Helm is used to replace the image name in the Kubernetes configuration and deploy it to the Kubernetes cluster. Helm allows for modularization and versioning, simplifies the deployment process, reduces redundancy, and maintains a chart repository for easy deployment of applications.

## Kubernetes
The selected Docker image is deployed to a Kubernetes cluster. The deployment process involves replacing the image name in Helm and deploying it to the Kubernetes cluster.

CI project: https://github.com/rahilnawab/CI
