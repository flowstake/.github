# API Documentation

## Overview

The FlowStake API provides endpoints for activity verification, challenge management, and user interactions.

## Base URL

```
Production: https://api.flowstake.com
Development: http://localhost:3000
```

## Authentication

```http
Authorization: Bearer <jwt_token>
```

## Endpoints

### Activities

#### Verify Activity
```http
POST /api/activities/verify
Content-Type: application/json

{
  "stravaActivityId": "string",
  "type": "string",
  "distance": number,
  "duration": number
}
```

#### Get User Activities
```http
GET /api/activities/user/:userId
```

### Challenges

#### Create Challenge
```http
POST /api/challenges
Content-Type: application/json

{
  "type": "individual",
  "activityType": "running",
  "tokenType": "ETH",
  "stakeAmount": number,
  "targetDistance": number,
  "startDate": "string",
  "endDate": "string"
}
```

#### Join Challenge
```http
POST /api/challenges/:id/join
```

### Profile

#### Get Profile
```http
GET /api/profile/:userId
```

#### Update Profile
```http
PATCH /api/profile/:userId
Content-Type: application/json

{
  "name": "string",
  "email": "string"
}
```

## Error Handling

```json
{
  "error": "string",
  "message": "string",
  "details": {}
}
```

## Rate Limiting

- 100 requests per 15 minutes
- 429 Too Many Requests response

## Versioning

Current version: v1
Format: `/api/v1/endpoint`

## Testing

```bash
# Run API tests
npm run test:api

# Test specific endpoint
npm run test:api -- --grep "Activities"
```