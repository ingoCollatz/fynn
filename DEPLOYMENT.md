# Deployment Setup for Fynn Website

This document contains all the information needed to deploy the Fynn website to your Hetzner server.

## Required GitHub Secrets

You need to configure the following secrets in your GitHub repository settings:

### Server Connection
- **`SERVER_HOST`** - The IP address or hostname of your Hetzner server
- **`SERVER_USER`** - The SSH username (typically `root` or your user account)
- **`SERVER_SSH_KEY`** - The private SSH key for server access (full content of your private key file)

## Domain Configuration

The deployment is configured for the following domains:

### Production (main branch)
- **Primary**: `https://fynn-schomann.de`
- **WWW redirect**: `https://www.fynn-schomann.de`

### Development (dev branch)
- **Development**: `https://fynn.stacktastik.dev`

## Server Setup Requirements

Your Hetzner server needs the following prerequisites:

### 1. Docker & Docker Compose
```bash
# Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

### 2. Traefik Reverse Proxy
Your server should have Traefik running with:
- SSL certificate resolver named `myresolver`
- External network named `web`
- Entrypoint named `websecure`

### 3. Directory Structure
The deployment will create the following structure on your server:
```
~/fynn/
├── main/
│   ├── docker-compose.main.yml
│   └── image.tar (temporary)
└── dev/
    ├── docker-compose.dev.yml
    └── image.tar (temporary)
```

## DNS Configuration

Configure your domain DNS to point to your Hetzner server:

```
fynn-schomann.de        A     YOUR_SERVER_IP
www.fynn-schomann.de    A     YOUR_SERVER_IP
fynn.stacktastik.dev A    YOUR_SERVER_IP
```

## Deployment Process

The deployment happens automatically when you push to:
- **main branch** → deploys to production
- **dev branch** → deploys to development

### Manual Deployment Steps:

1. **Set up GitHub Secrets** in your repository settings
2. **Configure DNS** to point to your server
3. **Ensure Traefik is running** on your server
4. **Push to main or dev branch**

The GitHub Actions workflow will:
1. Run tests and build the SvelteKit application
2. Create a Docker image
3. Upload the image to your server
4. Deploy using Docker Compose
5. Perform health checks
6. Report deployment status

## Testing the Deployment

After deployment, the workflow automatically tests:
- Site accessibility via HTTPS
- SSL certificate validity
- Response time and status codes

## Troubleshooting

### Common Issues:

1. **SSH Connection Failed**
   - Verify `SERVER_HOST`, `SERVER_USER`, and `SERVER_SSH_KEY` secrets
   - Ensure your server accepts SSH connections
   - Check firewall settings

2. **Domain Not Accessible**
   - Verify DNS configuration
   - Check Traefik configuration
   - Ensure port 80/443 are open

3. **Docker Issues**
   - Verify Docker is running: `sudo systemctl status docker`
   - Check Docker Compose version compatibility
   - Ensure `web` network exists: `docker network ls`

### Logs and Debugging:

```bash
# Check container logs
docker logs fynn-main  # or fynn-dev

# Check Traefik logs
docker logs traefik

# View running containers
docker ps

# Check network connectivity
docker network inspect web
```

## Security Considerations

- SSH keys should be kept secure and rotated regularly
- Use strong passwords for server access
- Keep Docker and system packages updated
- Monitor server logs for suspicious activity
- Consider implementing fail2ban for SSH protection

## Contact

For deployment issues or questions, contact the development team or refer to the GitHub repository issues.