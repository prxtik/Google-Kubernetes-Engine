# Google-Kubernetes-Engine

This repository contains the source code for building a Cloud-Native CI/CD Pipeline and Deploying workload to Google Kubernetes Engine (GKE). The project demonstrates the understanding of containerization, CI/CD, and Google Kubernetes Engine (GKE) by building a cloud-native application on Google Cloud Platform (GCP). This project was developed as a part of CSCI 5409 course of MACS program at Dalhousie University.

## Overview

- Containerization using Docker.
- Building CI/CD pipelines with GCP tools.
- Utilizing Kubernetes concepts.
- Implementing persistent storage in GKE.
- Managing containers with Kubernetes tools.
- Understanding application update strategies in GKE.

## Key Components

- Container 1: Responsible for storing files in GKE persistent volumes, calculating product totals, and interacting with Container 2.

- Container 2: Listens on a specified port, calculates product totals, and communicates with Container 1.

## Workflow

- Created two microservices that facilitate file storage, retrieval, and product total calculations, making them essential for the assignment's objectives.

  - a POST API with endpoint: `/store-file`

    - Purpose: This endpoint is used to store a file in GKE's persistent storage.
    - Input: It expects a JSON input with the file name and data to be stored in CSV format.
    - Output for Success: If the file is stored successfully, it returns a success message.
    - Output for Failure: In case of errors during file storage or missing file name, appropriate error messages are returned.

  - a POST API with endpoint: `/calculate`
    - Purpose: This endpoint calculates the total of a product from a specified file in GKE's persistent storage.
    - Input: It expects a JSON input with the file name and the product for which the total should be calculated.
    - Output for Success: If the file exists and the calculation succeeds, it returns the total.
    - Output for Failure: If the file is not found, the contents are in the wrong format, or there are missing parameters, it returns corresponding error messages.

- Implemented a CI/CD pipeline for deployment on GKE.
- Configured a persistent volume accessible to both containers.
- Exposed Container 1 as a service to the internet.
- Implemented specific APIs as described in the assignment document.
- Recorded a video demonstrating cluster creation, CI/CD pipeline operation, and application functionality.
