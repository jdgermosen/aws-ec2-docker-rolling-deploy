# Manual Deployment Notes – AI Prodigy Infrastructure

This document explains how I deployed and updated our production infrastructure manually using Docker on EC2 with high availability and zero downtime.

## Infrastructure Overview

- **EC2 Auto Scaling Group** (2 AZs)
- **Application Load Balancer** with path-based routing (`/api`, `/client`)
- **Dockerized Services** (WebSocket, Flask API, UI)
- **Route 53** domain management
- **Secrets Manager** for secure env var access

## Deployment Steps

### Initial setup

1. SSH into the EC2 instance:
   ```bash
   ssh -i ~/.ssh/key.pem ec2-user@<public-ip>
