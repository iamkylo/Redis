# Redis Learning Projects

This repository contains foundational Redis projects and practical examples for learning Redis with Node.js, Express, and MongoDB.

## Projects

### 1. 01-foundation-of-redis
Basic introduction to Redis with Express and MongoDB integration.

**Features:**
- Redis connection and ping test
- MongoDB connection verification
- Health check endpoints

**Run:** `npm run dev` from `01-foundation-of-redis/`

---

### 2. 02-setup-redis
Complete Redis setup example with Express and MongoDB integration.

**Features:**
- Redis client configuration
- Express server setup
- MongoDB integration
- Environment variable support

**Run:** `npm run dev` from `02-setup-redis/`

---

### 3. 03-site-banner
Practical example of Redis usage for dynamic banner content management.

**Features:**
- POST banner message to Redis cache
- GET banner from Redis
- DELETE banner from Redis
- Check banner existence

**API:**
- `POST /banner` - Set banner message
- `GET /banner` - Get banner message
- `DELETE /banner` - Remove banner
- `GET /banner/exists` - Check if banner exists

**Run:** `npm run dev` from `03-site-banner/`

---

### 4. 04-otp-login-ttl
Redis-based OTP system with automatic expiration using TTL.

**Features:**
- Generate OTPs for phone numbers
- Auto-expiring OTPs (30 seconds TTL)
- Verify OTPs before expiration
- Check remaining time-to-live

**API:**
- `POST /otp` - Generate OTP
- `POST /otp/verify` - Verify OTP
- `GET /otp/:phone/ttl` - Check TTL

**Run:** `npm run dev` from `04-otp-login-ttl/`

---

## Docker Setup

Run Redis and MongoDB services:

```bash
docker-compose up -d
```

**Services:**
- Redis 7 (Alpine) on port 6379
- MongoDB 7 on port 27017

## Environment Variables

Create a `.env` file in each project:

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
- **mongoose** - MongoDB ODM (for projects 1 & 2)

## Key Redis Concepts Covered

✅ Connection & Basic Commands  
✅ Caching Strategies  
✅ Time-To-Live (TTL) & Expiration  
✅ Redis Data Persistence  
✅ Integration with Express

## License

ISC
