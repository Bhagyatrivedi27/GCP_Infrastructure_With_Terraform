# GCP Cloud Infrastructure with Terraform

## Overview

This project showcases the deployment of a cloud-based infrastructure on Google Cloud Platform (GCP) using Terraform. The infrastructure supports a serverless architecture with secure, scalable, and highly available components including Google Pub/Sub, Cloud Functions, VPC networking, IAM roles, and Google Cloud Storage. The project leverages Infrastructure as Code (IaC) principles to automate the provisioning and management of resources, ensuring consistency and repeatability across environments.

## Key Features

- **Asynchronous Messaging with Google Pub/Sub:** 
  - Implemented Google Pub/Sub topics and subscriptions for reliable, scalable, and decoupled communication between microservices.
  - Configured Pub/Sub with appropriate message retention policies and IAM bindings to secure access and manage message lifecycle.

- **Serverless Compute with Cloud Functions:**
  - Deployed Google Cloud Functions triggered by Pub/Sub messages to handle background processing tasks.
  - Integrated VPC Access Connectors for secure communication between Cloud Functions and other VPC resources.

- **Secure Data Management:**
  - Utilized Google Cloud Storage for storing application artifacts with encryption managed by Google KMS, ensuring data at rest is protected.
  - Created and managed KMS keys with regular rotation policies for enhanced security and compliance.

- **Highly Available Compute Resources:**
  - Configured Compute Engine instances with Instance Templates, Managed Instance Groups, and Auto-Scaling policies to handle varying workloads efficiently.
  - Implemented global load balancing and health checks to ensure high availability and fault tolerance across multiple regions.

- **Comprehensive Networking Setup:**
  - Designed and deployed a custom VPC with subnets, routes, and firewall rules to control traffic flow and secure the cloud environment.
  - Established private IP communication between services using Service Networking and private VPC connections.

## Technologies Used

- **Google Cloud Platform (GCP)**
  - Google Pub/Sub
  - Google Cloud Functions
  - Google Compute Engine
  - Google Cloud Storage
  - Google KMS (Key Management Service)
  - Google VPC (Virtual Private Cloud)
  - Google IAM (Identity and Access Management)

- **Terraform**
  - Infrastructure as Code (IaC)
  - Modular Terraform configurations for reusable and maintainable codebase
  - Automated provisioning and management of cloud resources

- **Other Tools**
  - Python for scripting and automation tasks
  - Bash for startup scripts and environment setup

## Getting Started

### Prerequisites

- Google Cloud Account
- Terraform installed locally
- Google Cloud SDK for authentication

### Setup

1. Clone this repository:
    ```bash
    git clone https://github.com/yourusername/gcp-terraform-project.git
    cd gcp-terraform-project
    ```

2. Update `terraform.tfvars` with your project-specific variables:
    ```hcl
    project_id          = "your-project-id"
    region              = "us-east1"
    credentials_file    = "/path/to/your/service-account-key.json"
    google_storage_bucket_name = "your-bucket-name"
    google_pubsub_topic_name   = "your-pubsub-topic-name"
    # and other variables...
    ```

3. Initialize Terraform and apply the configuration:
    ```bash
    terraform init
    terraform apply
    ```

### Project Structure

- **main.tf:** The main Terraform configuration file defining all the cloud resources.
- **variables.tf:** Contains the variables used throughout the Terraform configuration.
- **outputs.tf:** Defines the outputs of the Terraform run, such as resource names and URLs.
- **startup.tpl:** A template file for initializing environment variables on Compute Engine instances.
- **README.md:** This file, detailing the project and how to get started.

## Contributions

Contributions are welcome! Please submit a pull request or open an issue to discuss improvements.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.