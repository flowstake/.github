# Strava Integration Guide

## Overview

FlowStake integrates with Strava for activity tracking and verification using OAuth2 authentication.

## Authentication Flow

1. **Authorization Request**
```typescript
const authUrl = getStravaAuthUrl();
// Redirects to Strava login
```

2. **Authorization Response**
```typescript
// Callback handler
async function handleCallback(code: string) {
  const tokens = await exchangeStravaToken(code);
  await updateUserProfile(tokens);
}
```

3. **Token Management**
```typescript
// Token refresh
async function refreshToken(refreshToken: string) {
  const newTokens = await refreshStravaToken(refreshToken);
  await updateStoredTokens(newTokens);
}
```

## API Integration

### Activity Sync
```typescript
async function syncActivities(userId: string, accessToken: string) {
  const activities = await getAthleteActivities(accessToken);
  await storeActivities(userId, activities);
}
```

### Webhook Events
```typescript
// Activity webhook handler
app.post('/webhook', async (req, res) => {
  const { object_type, object_id, aspect_type } = req.body;
  await handleStravaWebhook(object_type, object_id, aspect_type);
});
```

## Security

1. **Token Storage**
   - Encrypted in database
   - Never exposed to client
   - Regular rotation

2. **Webhook Verification**
   - Signature validation
   - Rate limiting
   - IP whitelisting

3. **Error Handling**
   - Token expiration
   - API limits
   - Network issues

## Resources

- [Strava API Documentation](https://developers.strava.com/docs/)
- [OAuth2 Best Practices](https://oauth.net/2/best-practices/)
- [Webhook Guide](https://developers.strava.com/docs/webhooks/)