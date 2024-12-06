# Database Documentation

## Overview

FlowStake uses PostgreSQL with Prisma ORM for data management and Supabase for backend services.

## Schema

### Users
```sql
CREATE TABLE profiles (
  id UUID PRIMARY KEY,
  email TEXT UNIQUE,
  wallet_address TEXT UNIQUE,
  strava_id TEXT UNIQUE,
  name TEXT,
  avatar_url TEXT,
  created_at TIMESTAMP
);
```

### Activities
```sql
CREATE TABLE activities (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES profiles(id),
  strava_activity_id TEXT UNIQUE,
  type TEXT,
  distance FLOAT,
  duration INTEGER,
  elevation_gain FLOAT,
  start_date TIMESTAMP,
  verified BOOLEAN
);
```

### Challenges
```sql
CREATE TABLE challenges (
  id UUID PRIMARY KEY,
  creator_id UUID REFERENCES profiles(id),
  type TEXT,
  activity_type TEXT,
  token_type TEXT,
  stake_amount FLOAT,
  target_distance FLOAT,
  target_time INTEGER,
  start_date TIMESTAMP,
  end_date TIMESTAMP
);
```

## Migrations

See [Migration Guide](./migrations/README.md) for database migration procedures.

## Security

- Row Level Security (RLS)
- Access policies
- Data encryption
- Backup procedures

## Performance

- Indexing strategy
- Query optimization
- Connection pooling
- Monitoring

## Development

1. Install tools:
```bash
npm install -g prisma
```

2. Generate client:
```bash
prisma generate
```

3. Run migrations:
```bash
prisma migrate dev
```

## Backup & Recovery

See [Backup Procedures](./backup/README.md) for detailed instructions.