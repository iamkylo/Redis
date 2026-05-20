# 02 - Setup Redis

Complete Redis setup example with Express and MongoDB integration.

## Overview

This project provides a foundation for:
- Redis client configuration
- Express server setup
- MongoDB integration
- Environment variable management

## Installation

```bash
npm install
```

## Running

```bash
npm run dev
```

Server runs on `http://localhost:3000`

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
MONGO_URL=mongodb://localhost:27017/chai_aur_redis
```

## Files

- `package.json` - Project configuration and dependencies
- `src/index.js` - Main server code with Redis and MongoDB setup
