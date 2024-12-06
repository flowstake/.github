# Deployment Documentation

## Overview

FlowStake deployment configuration for production environments.

## Infrastructure

- Frontend: Netlify
- Backend: Docker containers
- Database: Supabase
- Smart Contracts: Base Chain

## Frontend Deployment

### Netlify Configuration

```toml
[build]
  command = "npm run build"
  publish = "dist"

[build.environment]
  NODE_VERSION = "20"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200

[build.environment.production]
  VITE_SUPABASE_URL = "https://xllxefohcoryuzdzwbep.supabase.co"
  VITE_AUTH0_DOMAIN = "dev-t0svn2hdswfwani8.us.auth0.com"
```

### DNS Configuration

```toml
[[dns.records]]
  type = "A"
  name = "@"
  ttl = 3600
  value = "75.2.60.5"

[[dns.records]]
  type = "AAAA"
  name = "@"
  ttl = 3600
  value = "2600:1f16:0:0:0:0:0:1"
```

## Backend Deployment

### Docker Configuration

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]
```

### Environment Variables

```env
NODE_ENV=production
DATABASE_URL=postgresql://user:password@host:5432/db
JWT_SECRET=your-secret
PORT=3000
```

## Database Deployment

See [Database Deployment](../database/deployment.md) for detailed instructions.

## Monitoring

- Application metrics
- Error tracking
- Performance monitoring
- Security alerts

## CI/CD Pipeline

- Automated testing
- Build verification
- Deployment automation
- Rollback procedures

## Security

- SSL/TLS configuration
- API security
- Database security
- Smart contract verification