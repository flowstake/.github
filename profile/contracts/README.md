# Smart Contracts Documentation

## Overview

FlowStake smart contracts handle challenge creation, staking, and reward distribution on the Base blockchain.

## Contracts

### FlowstakeChallenge.sol
- Challenge creation and management
- Staking mechanism
- Activity verification
- Reward distribution

### FSTCrowdsale.sol
- Token presale implementation
- Price stages
- Vesting schedule
- Distribution rules

## Deployment

### FST Token
- **Network**: Base Chain
- **Address**: `0xf80d6EC0AF3abe8AFb1C83EC873C8942CC83B24a`
- **Supply**: 1,000,000,000 FST

### Presale Contract
- **Rate**: 1 ETH = 1000 FST
- **Soft Cap**: 1000 ETH
- **Duration**: 30 days
- **Min Purchase**: 0.01 ETH
- **Max Purchase**: 100 ETH

## Development

1. Install dependencies:
```bash
npm install
```

2. Compile contracts:
```bash
npx hardhat compile
```

3. Run tests:
```bash
npx hardhat test
```

4. Deploy:
```bash
npx hardhat run scripts/deploy.js --network base
```

## Security

- OpenZeppelin contracts
- Audit reports
- Security best practices
- Emergency procedures

## Contract Interaction

### Web3 Integration
```typescript
import { ethers } from 'ethers';
import { CONTRACTS } from './config/contracts';

// Contract initialization
const contract = new ethers.Contract(
  CONTRACTS.ADDRESS,
  CONTRACTS.ABI,
  signer
);
```

### Key Functions
- `createChallenge()`
- `joinChallenge()`
- `verifyActivity()`
- `distributeRewards()`

## Testing

```bash
# Run all tests
npm test

# Run specific test
npx hardhat test test/FlowstakeChallenge.test.js

# Coverage report
npx hardhat coverage
```