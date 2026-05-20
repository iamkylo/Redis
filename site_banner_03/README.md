# Site Banner

Practical Redis example demonstrating caching of banner content for a website.

## Overview

This project shows how to:
- Store dynamic content in Redis cache
- Retrieve cached content
- Delete cache entries
- Check cache key existence

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

### Set Banner Message
```
POST /banner
Content-Type: application/json

{
  "message": "Welcome to our website"
}

Response: { "success": true }
```

### Get Banner Message
```
GET /banner

Response: { "message": "Welcome to our website" }
```

### Delete Banner
```
DELETE /banner

Response: { "success": true }
```

### Check Banner Exists
```
GET /banner/exists

Response: { "exists": true }
```

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
```

## Files

- `package.json` - Project configuration and dependencies
- `src/index.js` - Main server code with banner management endpoints
