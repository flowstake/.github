# Frontend Documentation

## Overview

The FlowStake frontend is built with React 18.3, TypeScript, and Vite. It provides a modern, responsive interface for users to interact with the platform.

## Technology Stack

- React 18.3
- TypeScript
- Vite
- Tailwind CSS
- React Router
- React Query
- Zustand
- ethers.js

## Project Structure

```
src/
├── components/          # React components
│   ├── auth/           # Authentication components
│   ├── presale/        # Presale components
│   └── profile/        # Profile components
├── hooks/              # Custom React hooks
├── lib/                # Utility functions
├── pages/              # Route components
├── stores/             # State management
└── types/              # TypeScript types
```

## Getting Started

1. Install dependencies:
```bash
npm install
```

2. Set up environment variables:
```bash
cp .env.example .env
```

3. Start development server:
```bash
npm run dev
```

## Component Guidelines

- Use TypeScript for all components
- Follow atomic design principles
- Implement responsive design
- Use Tailwind CSS for styling
- Add proper prop types and documentation

## State Management

- Use Zustand for global state
- React Query for server state
- Local state with useState
- Context for theme/auth

## Testing

```bash
# Run tests
npm test

# Test coverage
npm run test:coverage
```

## Building

```bash
# Production build
npm run build

# Preview build
npm run preview
```