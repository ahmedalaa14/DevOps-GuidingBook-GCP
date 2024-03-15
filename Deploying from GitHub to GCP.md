# Deploying from GitHub to Google Cloud Platform (GCP) using Cloud Build

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
   - Configure build settings (e.g., Dockerfile path, substitution variables).

2. **Connect GitHub Repository:**
   - Authorize Cloud Build to access your GitHub repository.
   - Select your GitHub repository and configure the trigger settings.

## Create cloudbuild.yaml File

1. **Create `cloudbuild.yaml` in the Root of Your Project:**
   - This file defines the build steps for Cloud Build.

   ```yaml
   steps:
     - name: 'gcr.io/cloud-builders/gcloud'
       args: ['app', 'deploy']