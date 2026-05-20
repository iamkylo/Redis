# Foundation of Redis

Basic introduction to Redis with Express and MongoDB integration.

## Overview

This project demonstrates:
- Redis connection and health checks
- MongoDB connection and verification
- Simple RESTful API endpoints

## Installation

```bash
npm install
```

## Running

```bash
npm run dev
```

Server runs on `http://localhost:3000`

## API Endpoints

### Redis Check
```
GET /redis
Response: { "redis": "PONG" }
```

### MongoDB Check
```
GET /mongo
Response: { "mongo": "connected", "database": "chai_aur_redis" }
```

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
MONGO_URL=mongodb://localhost:27017/chai_aur_redis
```

## Files

- `package.json` - Project configuration and dependencies
- `src/index.js` - Main server code
