# Azure Secure Serverless Workload

A portfolio project demonstrating secure Azure infrastructure,
identity, networking, DevSecOps, and serverless application deployment.

## Project Goal

Build an internal inspection-reporting API backed by Azure Functions
and private Azure Storage.

## Planned Architecture

- Microsoft Entra ID authentication
- Azure Functions (Flex Consumption)
- Managed identities and least-privilege RBAC
- Private Blob Storage and virtual networking
- Terraform Infrastructure as Code
- GitHub Actions CI/CD using OIDC federation
- Checkov and Gitleaks security scanning
- Azure Policy, monitoring, and KQL-based detection

## Resource Organization

One Azure subscription with four resource groups:
- Foundation / bootstrap
- Network
- Application
- Operations / security

## Deployment Strategy

Persistent bootstrap resources are created separately.
Workload infrastructure is managed through Terraform.

## Cost Goal

Target: approximately $10–$20/month when deployed.
Budget ceiling: approximately $50/month.

## Status

Day 1: Development environment and repository initialization.

## Documentation

Architecture, threat modeling, deployment instructions,
testing evidence, and operational procedures will be added
throughout implementation.
