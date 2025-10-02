# GCP Automation SDK

A comprehensive collection of GCP (Google Cloud Platform) automation tools and scripts using official Google Cloud SDKs in multiple programming languages.

## Overview

This repository contains GCP automation utilities organized by SDK language, providing reusable code for common Google Cloud operations, resource management, and infrastructure automation tasks.

## Repository Structure

```
.
├── go-sdk/          # Go-based GCP automation scripts
└── python-sdk/      # Python-based GCP automation scripts
```

## Prerequisites

### For Go SDK (`/go-sdk`)
- Go 1.19 or later
- Google Cloud Client Libraries for Go
- Valid GCP credentials configured
- A GCP project with billing enabled

### For Python SDK (`/python-sdk`)
- Python 3.8 or later
- Google Cloud Client Libraries for Python
- Valid GCP credentials configured
- A GCP project with billing enabled

## GCP Authentication Setup

Configure your GCP credentials using one of the following methods:

### Method 1: gcloud CLI Authentication
```bash
gcloud auth application-default login
gcloud config set project YOUR_PROJECT_ID
```

### Method 2: Service Account Key
```bash
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/service-account-key.json"
export GCP_PROJECT_ID="your-project-id"
```

### Method 3: Service Account Key (Alternative)
```bash
gcloud auth activate-service-account --key-file=/path/to/service-account-key.json
```

## Getting Started

### Go SDK
```bash
cd go-sdk
go mod download
go run main.go
```

### Python SDK
```bash
cd python-sdk
pip install -r requirements.txt
python main.py
```

## Common Use Cases

This repository provides automation for common GCP tasks including:

- **Compute Engine**: VM instance provisioning, monitoring, and lifecycle management
- **Cloud Storage**: Bucket management, object uploads/downloads, and access control
- **Cloud Functions**: Deployment, invocation, and monitoring
- **IAM**: Service account, role, and policy management
- **Cloud Monitoring**: Metrics collection and alerting configuration
- **VPC Networks**: Network infrastructure automation
- **Cloud SQL**: Database instance management
- **BigQuery**: Dataset and table operations
- **Pub/Sub**: Topic and subscription management
- **Cloud Run**: Containerized application deployment

## Security Best Practices

- Never commit service account keys to version control
- Use service accounts with minimal required permissions (principle of least privilege)
- Enable audit logging for sensitive operations
- Regularly rotate service account keys
- Use Secret Manager for sensitive data
- Enable VPC Service Controls for enhanced security
- Use Workload Identity for GKE workloads

## Project Setup

Before running the scripts, ensure your GCP project has the necessary APIs enabled:

```bash
gcloud services enable compute.googleapis.com
gcloud services enable storage.googleapis.com
gcloud services enable cloudfunctions.googleapis.com
gcloud services enable iam.googleapis.com
gcloud services enable monitoring.googleapis.com
```

## Environment Variables

Common environment variables used across scripts:

```bash
export GCP_PROJECT_ID="your-project-id"
export GCP_REGION="us-central1"
export GCP_ZONE="us-central1-a"
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/key.json"
```

## Contributing

Contributions are welcome! Please ensure:
- Code follows language-specific best practices
- All scripts include proper error handling
- Documentation is updated accordingly
- Tests are included where applicable
- Service account permissions are documented

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues, questions, or contributions, please open an issue in the repository.

## Additional Resources

- [Google Cloud Go Documentation](https://cloud.google.com/go/docs)
- [Google Cloud Python Documentation](https://cloud.google.com/python/docs)
- [GCP Best Practices](https://cloud.google.com/architecture/framework)
- [GCP IAM Best Practices](https://cloud.google.com/iam/docs/best-practices)
- [gcloud CLI Reference](https://cloud.google.com/sdk/gcloud/reference)

## Troubleshooting

### Common Issues

**Authentication Error:**
```bash
# Verify authentication
gcloud auth list
gcloud config list project
```

**API Not Enabled:**
```bash
# Enable required APIs
gcloud services list --available
gcloud services enable <API_NAME>
```

**Permission Denied:**
- Verify service account has necessary IAM roles
- Check organization policies
- Review project-level permissions
