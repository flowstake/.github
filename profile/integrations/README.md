# Integration Guide

## Overview

This guide covers the integration of external services and protocols with FlowStake.

## Ethereum Attestation Service (EAS)

### Setup
```typescript
import { EAS, SchemaEncoder } from "@ethereum-attestation-service/eas-sdk";

const EAS_CONTRACT = "0xC2679fBD37d54388Ce493F1DB75320D236e1815e";
const eas = new EAS(EAS_CONTRACT);
```

### Activity Schema
```solidity
struct ActivityAttestation {
    address athlete;
    uint256 timestamp;
    string activityType;
    uint256 distance;
    uint256 duration;
    bytes32 stravaId;
    bytes32 proof;
}
```

### Creating Attestations
```typescript
const schemaEncoder = new SchemaEncoder("address athlete,uint256 timestamp...");
const encodedData = schemaEncoder.encodeData([
    { name: "athlete", value: address, type: "address" },
    { name: "timestamp", value: timestamp, type: "uint256" },
    // ... other fields
]);
```

## Safe Multi-Signature

### Initialization
```typescript
import Safe from '@safe-global/protocol-kit';

const safeConfig = {
    threshold: 3,
    owners: [owner1, owner2, owner3, owner4, owner5],
    chainId: 8453
};
```

### Transaction Execution
```typescript
const safeTransaction = await safeSdk.createTransaction({
    to,
    data,
    value
});
const signedTx = await safeSdk.signTransaction(safeTransaction);
```

## Hedgey Finance Vesting

### Setup
```typescript
const VESTING_FACTORY = "0x...";
const vestingSchedule = {
    beneficiary: address,
    amount: tokenAmount,
    duration: 365 days,
    cliff: 90 days
};
```

### Creating Vesting Schedule
```typescript
await vestingFactory.createVesting(
    vestingSchedule.beneficiary,
    vestingSchedule.amount,
    vestingSchedule.duration,
    vestingSchedule.cliff
);
```

## Strava Integration

### OAuth2 Flow
```typescript
const STRAVA_CONFIG = {
    clientId: process.env.STRAVA_CLIENT_ID,
    clientSecret: process.env.STRAVA_CLIENT_SECRET,
    redirectUri: "https://flowstake.com/strava-callback"
};
```

### Activity Sync
```typescript
async function syncStravaActivities(accessToken: string) {
    const activities = await fetch(
        "https://www.strava.com/api/v3/athlete/activities",
        {
            headers: { Authorization: `Bearer ${accessToken}` }
        }
    );
    return activities.json();
}
```

## Auth0 Integration

### Configuration
```typescript
const auth0Config = {
    domain: "dev-xxx.auth0.com",
    clientId: "your-client-id",
    audience: "https://api.flowstake.com"
};
```

### Authentication
```typescript
import { Auth0Provider } from "@auth0/auth0-react";

<Auth0Provider
    domain={auth0Config.domain}
    clientId={auth0Config.clientId}
    authorizationParams={{
        redirect_uri: window.location.origin
    }}
>
    <App />
</Auth0Provider>
```

## Supabase Integration

### Setup
```typescript
import { createClient } from '@supabase/supabase-js';

const supabase = createClient(
    process.env.SUPABASE_URL,
    process.env.SUPABASE_ANON_KEY
);
```

### Database Operations
```typescript
const { data, error } = await supabase
    .from('activities')
    .select('*')
    .eq('user_id', userId);
```

## API Integration

### Endpoints
```typescript
const API_ENDPOINTS = {
    activities: '/api/activities',
    challenges: '/api/challenges',
    attestations: '/api/attestations',
    profile: '/api/profile'
};
```

### Authentication
```typescript
const headers = {
    Authorization: `Bearer ${token}`,
    'Content-Type': 'application/json'
};
```

## WebSocket Integration

### Connection
```typescript
const ws = new WebSocket('wss://api.flowstake.com/ws');
ws.onmessage = (event) => {
    const data = JSON.parse(event.data);
    handleWebSocketMessage(data);
};
```

## Error Handling

### Standard Error Format
```typescript
interface ApiError {
    code: string;
    message: string;
    details?: any;
}
```

### Error Handling
```typescript
try {
    // API call
} catch (error) {
    handleError(error);
}
```