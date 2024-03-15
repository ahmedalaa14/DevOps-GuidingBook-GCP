# Infrastructure as Code (IaC) for Google Cloud Platform

## Introduction

Infrastructure as Code (IaC) is a key DevOps practice that involves managing and provisioning infrastructure using code, rather than manual processes. In the context of Google Cloud Platform (GCP), several tools and services facilitate the implementation of IaC, providing a consistent and repeatable way to manage cloud resources.

## Key Concepts

### 1. **Declarative Configuration**

IaC in GCP relies on declarative configuration files, where you specify the desired state of your infrastructure. Tools like Google Cloud Deployment Manager use YAML or Python templates to define resources and their properties.

### 2. **Google Cloud Deployment Manager**

Google Cloud Deployment Manager is a service that allows you to create and manage GCP resources through declarative configurations. It supports versioning, making it easy to track changes to infrastructure over time.

### 3. **Templates and Jinja**

Deployment Manager templates are written using YAML or Python with embedded Jinja expressions. Jinja is a templating engine that allows dynamic content and reuse of common configurations.

## Sample Infrastructure as Code (IaC) Template

```yaml
# infrastructure.yaml

resources:
- name: my-storage-bucket
  type: storage.v1.bucket
  properties:
    location: US
    storageClass: MULTI_REGIONAL

- name: my-instance
  type: compute.v1.instance
  properties:
    zone: us-central1-a
    machineType: zones/us-central1-a/machineTypes/n1-standard-1
    diskImage: projects/debian-cloud/global/images/debian-9-stretch-v20190213