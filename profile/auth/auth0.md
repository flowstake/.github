# Auth0 Integration Guide

## Overview

FlowStake uses Auth0 for authentication and authorization, including social connections and custom rules for Strava integration.

## Configuration

### Application Settings

1. Create Regular Web Application
2. Configure allowed URLs:
   ```
   Allowed Callback URLs: https://flowstake.com/callback
   Allowed Logout URLs: https://flowstake.com
   Allowed Web Origins: https://flowstake.com
   ```

### Rules

1. **Strava Connection**
   - Handles Strava OAuth flow
   - Stores tokens securely
   - Updates user metadata

2. **Activity Sync**
   - Syncs Strava activities
   - Manages webhooks
   - Tracks sync status

3. **Token Refresh**
   - Handles token expiration
   - Automatic refresh
   - Updates storage

See [Auth0 Rules](./rules.md) for implementation details.

## Social Connections

### Strava

1. Enable Strava connection
2. Configure client ID and secret
3. Set up scopes:
   - `read`
   - `activity:read_all`

### GitHub

1. Enable GitHub connection
2. Configure OAuth App
3. Set required scopes

## User Metadata

### App Metadata
```json
{
  "strava_connected": boolean,
  "last_sync": string,
  "kyc_status": string
}
```

### User Metadata
```json
{
  "wallet_address": string,
  "preferences": {
    "notifications": boolean,
    "newsletter": boolean
  }
}
```

## Actions

### Post Login
- Update profile
- Sync activities
- Check KYC status

### Post Registration
- Create Supabase profile
- Set default preferences
- Welcome email

## Security

1. **Token Storage**
   - Secure token management
   - Encryption at rest
   - Limited exposure

2. **Scope Management**
   - Minimal permissions
   - Regular audits
   - Access control

3. **Rate Limiting**
   - API protection
   - Brute force prevention
   - DDoS mitigation

## Error Handling

1. **Authentication Errors**
   - Invalid credentials
   - Expired tokens
   - Network issues

2. **Integration Errors**
   - Strava API failures
   - Token refresh issues
   - Sync problems

## Monitoring

1. **Metrics**
   - Login success rate
   - Token refresh rate
   - Error frequency

2. **Alerts**
   - Authentication failures
   - Integration issues
   - Security events

## Resources

- [Auth0 Documentation](https://auth0.com/docs)
- [Strava OAuth Guide](https://developers.strava.com/docs/authentication/)
- [Security Best Practices](https://auth0.com/docs/security)