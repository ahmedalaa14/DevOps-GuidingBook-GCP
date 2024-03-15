# Network Policies in Google Cloud Platform (GCP)

## Introduction

Google Cloud Platform (GCP) provides Network Policies as a crucial component for controlling and securing the flow of traffic within a Virtual Private Cloud (VPC). Network Policies enable fine-grained control over communication between different resources, enhancing security and network segmentation.

## Key Concepts

### 1. **VPC (Virtual Private Cloud):**
   - A logically isolated section of GCP where you can deploy resources.
   - Acts as a private, virtual network for your GCP resources.

### 2. **Firewall Rules:**
   - Control the traffic allowed into and out of VM instances.
   - Applied at the instance level and can be specified for ingress and egress traffic.

### 3. **Network Policies:**
   - A GCP feature that enables the definition of rules to control traffic between pods in Google Kubernetes Engine (GKE) clusters.

## Benefits of Network Policies

1. **Micro-Segmentation:**
   - Define specific rules for communication between different segments of your network, enhancing security.

2. **Isolation and Access Control:**
   - Isolate workloads and control communication, ensuring that only necessary connections are allowed.

3. **Reduced Attack Surface:**
   - Limit communication pathways, reducing the potential attack surface within your infrastructure.

## Creating a Network Policy

### 1. **Define Policy Rules:**
   - Specify the desired communication rules between pods in the `networkpolicy.yaml` file.

   Example:

   ```yaml
   apiVersion: networking.k8s.io/v1
   kind: NetworkPolicy
   metadata:
     name: allow-nginx
   spec:
     podSelector:
       matchLabels:
         app: nginx
     policyTypes:
     - Ingress
     ingress:
     - from:
       - podSelector:
           matchLabels:
             app: web
       ports:
       - protocol: TCP
         port: 80