# Backend Documentation

## Overview

The FlowStake backend provides API endpoints for activity verification, challenge management, and reward distribution.

## Technology Stack

- Node.js
- Express
- Prisma ORM
- PostgreSQL
- Auth0
- Supabase

## API Structure

```
api/
├── routes/            # API routes
├── middleware/        # Express middleware
├── services/         # Business logic
└── config/           # Configuration
```

## Database Schema

See [Database Documentation](../database/README.md) for complete schema details.

## Authentication

- JWT-based authentication
- Auth0 integration
- Wallet signatures
- Strava OAuth2

## API Endpoints

### Activities
- `POST /api/activities/verify`
- `GET /api/activities/user/:userId`

### Challenges
- `POST /api/challenges`
- `GET /api/challenges/active`
- `POST /api/challenges/:id/join`

### Profile
- `GET /api/profile/:userId`
- `PATCH /api/profile/:userId`

## Security

- Rate limiting
- Input validation
- Error handling
- Logging system

## Development

1. Install dependencies:
```bash
npm install
```

2. Set up environment:
```bash
cp .env.example .env
```

3. Start development server:
```bash
npm run dev
```

## Deployment

See [Deployment Guide](../deployment/README.md) for production deployment instructions.