# GreenAccounter
Repository for running the GreenAccounter demo.

This document describes how to set up and deploy the GreenAccounter project.

---

## Setup Instructions

Follow the steps below in order.


### 1. Configuration File

Create a file named `config` in the project root directory and add the following information:

- Firebase SDK key  
- Firebase JSON file name  
  - Download the JSON key file from the Firebase Console  
  - Place the JSON file in the project root directory
    


### 2. ElectricityMaps API Key

Create a file named `electricitymaps.txt` and add your ElectricityMaps API key.
- YOUR_ELECTRICITYMAPS_API_KEY



### 3. SSH Configuration

Configure the `ssh_data` file with the appropriate credentials for your deployment environment, such as:

- Server address
- Username
- SSH key or authentication details


This configuration is required for Kubernetes deployment.



### 4. Kubernetes Deployment

After completing all configuration steps, deploy the project by running:

```bash
bash make_file.bash
```

This script automatically prepares and deploys all required Kubernetes resources.


### 5. Deep Learning Model Setup
Region Configuration

Set the region codes used by the deep learning model:

- KR — South Korea
- IT-CSO — Italy (Corsica)
- US — United States

_Note: In this demo version, regions are fixed for testing purposes._

### 6. Docker Deployment for Deep Learning Model

The deep learning model (VGGNet) is deployed using Docker in a cloud environment.

Deployment steps:

1. Containerize the VGGNet model using Docker
2. Push the Docker image to your cloud provider
3. Deploy one Docker instance per region

Each re
gion operates independently and processes region-specific electricity data.
