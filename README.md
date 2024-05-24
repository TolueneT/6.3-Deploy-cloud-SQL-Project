# GCP Project 6.3 Documentation

## Project Overview

### Project Name

**pistis-gcp-training**

### Description

This project involves setting up a Google Cloud Platform (GCP) infrastructure to deploy a simple web application, including a static website and a basic API service. The infrastructure will use various GCP services including App Engine, Cloud Storage, Cloud SQL, and VPC networking.

## **_Prerequisites_**

- Google Cloud SDK installed
- GCP project created
- Billing enabled for the GCP project

## Setup Steps

### 1. **Authenticate and Set Project**

'''
{

gcloud auth login
gcloud config set project pistis-gcp-training

}
'''

### 2. **Create a VPC and Subnet**

![Screenshot of VPC](images/Capture1.jpg)
![screenshort of subnet](images/Capture.JPG)

'''
{
gcloud compute networks create my-vpc --subnet-mode=custom
gcloud compute networks subnets create my-subnet --network=my-vpc --range=10.0.0.0/24 --region=us-central1

}
'''

### 3. **Create Firewalls Rules**

     - You create a firewall rules for security.

![Screenshort for firewall](images/capture2.jpg)

'''
{
gcloud compute firewall-rules create allow-internal --network=my-vpc --allow=tcp,udp,icmp --source-ranges=10.0.0.0/24
gcloud compute firewall-rules create allow-external --network=my-vpc --allow=tcp:80,tcp:443 --source-ranges=0.0.0.0/0
}
'''

### 4. **Set up a Database**

#### - Create a cloud SQL instance

#### - Create a databa

#### - Set up a user

![Screenshort for firewall](images/capture3.jpg)
![Screenshort for firewall](images/capture4.jpg)
![Screenshort for firewall](images/capture5.jpg)

# **Deployment**

## 1. Create an 'app.yaml' file in the project directory.

![Screenshort for firewall](images/capture6.jpg)

## 2. Deploy to app engine

'gcloud app deploy'
![Screenshort for firewall](images/capture7.jpg)
![Screenshort for firewall](images/capture8.jpg)

## 3. Verify Deployment

- visit the URL provided by the deployment output [Deployment link](https://PROJECT_ID.REGION_ID.r.appspot.com)
  ![Screenshort for firewall](images/capture9.jpg)
