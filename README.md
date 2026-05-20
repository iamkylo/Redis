# Redis Learning Projects

This repository contains foundational Redis projects and setup guides for learning Redis with Node.js, Express, and MongoDB.

## Projects

### 1. Foundation of Redis (`foundation-of-redis-01`)
Introductory project demonstrating Redis integration with Express and MongoDB.

**Features:**
- Redis connection and ping test
- MongoDB connection verification
- RESTful API endpoints for both databases

**Getting Started:**
```bash
cd "foundation-of-redis-01"
npm install
npm run dev
```

**API Endpoints:**
- `GET /redis` - Check Redis connection
- `GET /mongo` - Check MongoDB connection

### 2. Setup Redis (`setup_redis`)
Complete Redis setup with Express and MongoDB integration.

**Features:**
- Express server setup
- Redis client configuration
- MongoDB integration
- Environment variable support

**Getting Started:**
```bash
cd setup_redis
npm install
npm run dev
```

### 3. Site Banner (`site_banner_03`)
Practical example of Redis usage for storing and managing dynamic banner content.

**Features:**
- POST banner message to Redis cache
- GET banner from Redis
- DELETE banner from Redis
- Check banner existence

**Getting Started:**
```bash
cd site_banner_03
npm install
npm run dev
```

**API Endpoints:**
- `POST /banner` - Set banner message
- `GET /banner` - Get banner message
- `DELETE /banner` - Remove banner
- `GET /banner/exists` - Check if banner exists

## Docker Setup

Use the provided `docker-compose.yml` to run Redis and MongoDB services:

```bash
docker-compose up -d
```

**Services:**
- Redis 7 (Alpine) on port 6379
- MongoDB 7 on port 27017

## Environment Variables

Create a `.env` file in each project root:

```env
REDIS_URL=redis://localhost:6379
MONGO_URL=mongodb://localhost:27017/chai_aur_redis
```

## Requirements

- Node.js 18+
- Docker & Docker Compose (optional)
- Redis (or use Docker)
- MongoDB (or use Docker)

## Dependencies

- **express** - Web framework
- **ioredis** - Redis client
- **mongoose** - MongoDB ODM

## License

ISC
