# Redis Learning Projects - package.json Files

## 01-foundation-of-redis
```json
{
  "name": "foundation-of-redis",
  "version": "1.0.0",
  "description": "Foundation of Redis - Basic setup with Express and MongoDB",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js"
  },
  "keywords": ["redis", "express", "mongodb"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1",
    "mongoose": "^9.6.2"
  }
}
```

## 02-setup-redis
```json
{
  "name": "setup-redis",
  "version": "1.0.0",
  "description": "Redis setup with Express and MongoDB",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js"
  },
  "keywords": ["redis", "express", "mongodb"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1",
    "mongoose": "^9.6.2"
  }
}
```

## 03-site-banner
```json
{
  "name": "site-banner",
  "version": "1.0.0",
  "description": "Redis banner caching example",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js"
  },
  "keywords": ["redis", "express", "caching", "banner"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1"
  }
}
```

## 04-otp-login-ttl
```json
{
  "name": "otp-login-ttl",
  "version": "1.0.0",
  "description": "OTP login with TTL using Redis",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js"
  },
  "keywords": ["redis", "otp", "ttl", "express"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1"
  }
}
```

## 05-profile-cache-redis-json-vs-hash
```json
{
  "name": "profile-cache-redis-json-vs-hash",
  "version": "1.0.0",
  "description": "Compare Redis JSON and Hash storage methods",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js"
  },
  "keywords": ["redis", "json", "hash", "caching", "express"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1"
  }
}
```

## 06-email-queue-redis-list
```json
{
  "name": "email-queue-redis-list",
  "version": "1.0.0",
  "description": "Email queue system using Redis Lists",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js"
  },
  "keywords": ["redis", "queue", "list", "email", "express"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1"
  }
}
```

## 07-pub-sub-redis
```json
{
  "name": "pub-sub-redis",
  "version": "1.0.0",
  "description": "Redis Pub/Sub messaging system",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node src/index.js",
    "subscriber": "node src/subscriber.js"
  },
  "keywords": ["redis", "pub-sub", "messaging", "express"],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.2.1",
    "ioredis": "^5.10.1"
  }
}
```
