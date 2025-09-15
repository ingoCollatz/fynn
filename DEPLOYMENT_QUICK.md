# Quick Deployment Guide

## GitHub Secrets Setup

Add these secrets in your GitHub repository settings (Settings → Secrets and variables → Actions):

1. **SERVER_HOST** - Your Hetzner server IP address
2. **SERVER_USER** - SSH username (usually `root`)
3. **SERVER_SSH_KEY** - Complete SSH private key content

## Deployment

- Push to `main` branch → deploys to `https://fynn-schomann.de`
- Push to `staging` branch → deploys to `https://staging.fynn-schomann.de`

## Prerequisites on Server

- Docker & Docker Compose installed
- Traefik reverse proxy running
- External Docker network named `web`
- DNS records pointing to your server

For detailed setup instructions, see [DEPLOYMENT.md](./DEPLOYMENT.md)