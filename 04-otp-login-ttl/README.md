# 04 - OTP Login with TTL

Redis-based OTP (One-Time Password) system with time-to-live (TTL) expiration.

## Overview

This project demonstrates:
- Generating OTPs and storing them in Redis
- Setting automatic expiration times (TTL) on cache keys
- Verifying OTPs before they expire
- Checking remaining TTL for OTPs

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

### Generate OTP
```
POST /otp
Content-Type: application/json

{
  "phone": "9876543210"
}

Response: { "message": "OTP SENT", "otp": "123456" }
```

### Verify OTP
```
POST /otp/verify
Content-Type: application/json

{
  "phone": "9876543210",
  "otp": "123456"
}

Response: { "message": "OTP verified successfully" }
```

### Check TTL (Time To Live)
```
GET /otp/9876543210/ttl

Response: { "ttl": 25 }
```

## Features

- **Auto Expiration**: OTPs automatically expire after 30 seconds
- **Phone-based Storage**: Each phone number gets its own OTP
- **TTL Checking**: View remaining time before OTP expires
- **Verification**: Validate OTP and auto-delete after verification

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
```

## How It Works

1. User requests OTP for their phone number
2. System generates random 6-digit OTP
3. OTP is stored in Redis with 30-second TTL
4. User submits OTP for verification
5. System validates OTP and deletes it from cache
6. If OTP expires before verification, user gets "OTP EXPIRED" message

## Files

- `package.json` - Project configuration
- `src/index.js` - Main server with OTP logic
