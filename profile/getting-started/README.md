# Getting Started with FlowStake

## Prerequisites

- Node.js 18+
- npm or yarn
- MetaMask wallet
- Auth0 account
- Strava API access
- Supabase account

## Environment Setup

1. Clone the repository:
```bash
git clone https://github.com/flowstake/flowstake.git
cd flowstake
```

2. Install dependencies:
```bash
npm install
```

3. Configure environment variables:
```bash
cp .env.example .env
```

Required environment variables:
```env
# Supabase
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_key

# Auth0
VITE_AUTH0_DOMAIN=your_auth0_domain
VITE_AUTH0_CLIENT_ID=your_auth0_client_id
VITE_AUTH0_CLIENT_SECRET=your_auth0_client_secret
VITE_AUTH0_AUDIENCE=your_auth0_audience

# Strava
VITE_STRAVA_CLIENT_ID=your_strava_client_id
VITE_STRAVA_CLIENT_SECRET=your_strava_client_secret
VITE_STRAVA_REDIRECT_URI=your_redirect_uri

# Base Chain
PRIVATE_KEY=your_private_key
BASE_RPC_URL=https://mainnet.base.org
ETHERSCAN_API_KEY=your_etherscan_key
```

4. Start development server:
```bash
npm run dev
```

## Configuration

### Auth0 Setup

1. Create an Auth0 application
2. Configure callback URLs
3. Set up social connections
4. Add custom rules

See [Auth0 Configuration](../auth/auth0.md) for details.

### Strava Integration

1. Create Strava API application
2. Configure OAuth2 settings
3. Set up webhook endpoints

See [Strava Integration](../auth/strava.md) for details.

### Smart Contract Deployment

1. Configure network settings
2. Deploy contracts
3. Verify on Basescan

See [Contract Deployment](../contracts/deployment.md) for details.

## Development Workflow

1. Create feature branch
2. Make changes
3. Run tests
4. Submit pull request

See [Contributing Guidelines](../contributing/README.md) for more information.

## Testing

```bash
# Run all tests
npm test

# Run specific test suite
npm test -- --grep "Auth"

# Generate coverage report
npm run test:coverage
```

## Building for Production

```bash
# Build frontend
npm run build

# Preview build
npm run preview
```

## Deployment

See [Deployment Guide](../deployment/README.md) for production deployment instructions.

## Support

- [Discord Community](https://discord.gg/flowstake)
- [GitHub Issues](https://github.com/flowstake/flowstake/issues)
- [Documentation](https://docs.flowstake.com)