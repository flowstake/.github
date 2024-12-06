# FlowStake

A fitness platform that combines exercise with blockchain technology, using Proof of Activity as a Stake. FlowStake enables users to earn cryptocurrency rewards by completing fitness challenges.

## Features

### Core Features
- **Wallet Integration**
  - MetaMask support
  - Secure transaction handling
  - Real-time account updates

- **Strava Integration via Auth0**
  - Secure OAuth2 authentication
  - Activity tracking and verification
  - Automated syncing
  - Performance metrics

- **Challenge System**
  - Individual challenges
  - Group competitions
  - Custom reward structures
  - Difficulty levels

### User Experience
- **Modern UI/UX**
  - Responsive design
  - Dark mode interface
  - Interactive components
  - Real-time updates

- **Activity Tracking**
  - Distance tracking
  - Time monitoring
  - Performance analytics
  - Achievement system

- **Social Features**
  - Activity sharing
  - Community challenges
  - Global leaderboard
  - Team competitions

## Quick Start

```bash
# Install dependencies
npm install

# Set up environment variables
cp .env.example .env

# Start development server
npm run dev

# Build for production
npm run build

# Deploy contracts
npm run deploy
```

## Environment Setup

Create `.env` file with the following variables:

```env
# Supabase
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_key

# Base Chain
PRIVATE_KEY=your_private_key
BASE_RPC_URL=https://mainnet.base.org
ETHERSCAN_API_KEY=your_etherscan_key

# Auth0
VITE_AUTH0_DOMAIN=your_auth0_domain
VITE_AUTH0_CLIENT_ID=your_auth0_client_id
VITE_AUTH0_CLIENT_SECRET=your_auth0_client_secret
VITE_AUTH0_AUDIENCE=your_auth0_audience

# Strava (via Auth0)
VITE_STRAVA_CLIENT_ID=your_strava_client_id
VITE_STRAVA_CLIENT_SECRET=your_strava_client_secret
VITE_STRAVA_REDIRECT_URI=your_redirect_uri
```

## Technology Stack

### Frontend
- **React 18.3**
  - TypeScript
  - Vite
  - React Router
  - React Query
  - Zustand

- **Authentication**
  - Auth0 integration
  - Wallet signatures
  - Strava OAuth2

- **Styling**
  - Tailwind CSS
  - Custom animations
  - Responsive layouts
  - Dark mode support

- **Web3 Integration**
  - ethers.js
  - MetaMask connectivity
  - Smart contract interaction

### Backend
- **Database**
  - Supabase
  - PostgreSQL
  - Row Level Security

- **Authentication**
  - Auth0 Rules System
  - JWT tokens
  - Wallet signatures
  - OAuth2 (Strava)

### Smart Contracts
- **Solidity**
  - OpenZeppelin
  - Hardhat
  - Base Chain

## Project Structure

```
flowstake/
├── contracts/                # Smart contracts
│   ├── FlowstakeChallenge.sol
│   └── FSTCrowdsale.sol
├── src/
│   ├── components/          # React components
│   │   ├── auth/           # Authentication components
│   │   ├── auth0/          # Auth0 specific components
│   │   ├── presale/        # Presale components
│   │   └── profile/        # Profile components
│   ├── config/             # Configuration files
│   │   └── auth0/          # Auth0 rules and settings
│   ├── hooks/              # Custom React hooks
│   ├── lib/                # Utility functions
│   │   ├── auth0/          # Auth0 utilities
│   │   ├── supabase/       # Supabase client & helpers
│   │   └── web3/           # Web3 utilities
│   ├── pages/              # Route components
│   ├── providers/          # Context providers
│   ├── stores/             # State management
│   └── types/              # TypeScript types
├── api/                    # Backend API
│   ├── routes/            # API routes
│   ├── middleware/        # Express middleware
│   └── services/          # Business logic
└── prisma/                # Database schema
```

## Smart Contracts

### FST Token
- **Network**: Base Chain
- **Address**: `0xf80d6EC0AF3abe8AFb1C83EC873C8942CC83B24a`
- **Supply**: 1,000,000,000 FST
- [View on Basescan](https://basescan.org/token/0xf80d6EC0AF3abe8AFb1C83EC873C8942CC83B24a)

### Presale Contract
- **Network**: Base Chain
- **Rate**: 1 ETH = 1000 FST
- **Soft Cap**: 1000 ETH
- **Min Purchase**: 0.01 ETH
- **Max Purchase**: 100 ETH
- **Duration**: 30 days

## Auth0 Integration

See [Auth0 Documentation](profile/docs/auth0/README.md) for detailed setup and configuration.

### Key Features
- Secure Strava OAuth2 authentication
- Automated token refresh
- Activity synchronization
- User metadata management

### Rules System
1. Strava Connection
2. Activity Sync
3. Token Refresh

## Development

### Prerequisites
- Node.js 18+
- npm or yarn
- MetaMask wallet
- Auth0 account
- Strava API access

### Running Locally

1. Install dependencies:
```bash
npm install
```

2. Configure environment:
```bash
cp .env.example .env
# Update .env with your credentials
```

3. Start development server:
```bash
npm run dev
```

### Testing

```bash
# Run tests
npm test

# Run tests with coverage
npm run test:coverage
```

### Deployment

1. Build the application:
```bash
npm run build
```

2. Deploy to production:
```bash
npm run deploy:prod
```

## Security

- Smart contracts are audited
- Auth0 handles authentication
- Secure wallet connections
- JWT for API authentication
- Rate limiting implemented
- Row Level Security with Supabase

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Connect With Us

- [Website](https://flowstake.com)
- [Twitter](https://x.com/flowstake)
- [YouTube](https://www.youtube.com/@Flowstake1)
- [TikTok](https://tiktok.com/@flowstake1)
- [Instagram](https://www.instagram.com/flowstake)
- [GitHub](https://github.com/flowstake)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
