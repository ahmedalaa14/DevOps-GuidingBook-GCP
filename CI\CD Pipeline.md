# Comprehensive Guide for Creating a CI/CD Pipeline in GCP using Cloud Build

## Prerequisites

1. **Google Cloud Platform Account:**
   - Ensure you have a GCP account and a project set up.

2. **Enable Cloud Build API:**
   - Navigate to the [Cloud Build API](https://console.cloud.google.com/apis/library/cloudbuild.googleapis.com) in the GCP Console and enable it.

3. **GitHub Repository:**
   - Have your application code hosted on a GitHub repository.

## Setup Cloud Build Trigger

1. **Create a Cloud Build Trigger:**
   - In the GCP Console, go to Cloud Build > Triggers.
   - Click on "Create Trigger."
   - Choose your repository and branch.
   - Configure build settings in the "Build Configuration" section.

   Example `cloudbuild.yaml`:

   ```yaml
   steps:
     - name: 'gcr.io/cloud-builders/gcloud'
       args: ['app', 'deploy']

   steps:
    - name: 'gcr.io/cloud-builders/npm'
    args: ['install']
    - name: 'gcr.io/cloud-builders/npm'
    args: ['test']


   steps:
    - name: 'gcr.io/cloud-builders/npm'
    args: ['install']
    - name: 'gcr.io/cloud-builders/npm'
    args: ['test']
    - name: 'gcr.io/cloud-builders/gcloud'
    args: ['app', 'deploy']


    steps:
    - name: 'gcr.io/cloud-builders/npm'
    args: ['install']
    - name: 'gcr.io/cloud-builders/npm'
    args: ['test']