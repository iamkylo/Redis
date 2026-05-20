# 05 - Profile Cache: Redis JSON vs Hash

Comparison of two Redis data storage methods: JSON strings and Hash objects.

## Overview

This project demonstrates:
- Storing data as JSON strings in Redis
- Storing data as Redis Hash structures
- Comparing performance and use cases for each method
- CRUD operations with both storage methods

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

### JSON Storage Method

#### Save User as JSON
```
POST /user/:id/json
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "age": 30
}

Response: { "savedAs": "JSON" }
```

#### Get User from JSON
```
GET /user/:id/json

Response: { "user": { "name": "John Doe", "email": "john@example.com", "age": 30 } }
```

---

### Hash Storage Method

#### Save User as Hash
```
POST /user/:id/hash
Content-Type: application/json

{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "age": 28
}

Response: { "savedAs": "hash" }
```

#### Get User from Hash
```
GET /user/:id/hash

Response: { "user": { "name": "Jane Doe", "email": "jane@example.com", "age": 28 } }
```

---

## JSON vs Hash Comparison

| Aspect | JSON | Hash |
|--------|------|------|
| **Storage** | Entire object as string | Individual field-value pairs |
| **Memory** | Higher (full serialization) | Lower (structured storage) |
| **Partial Update** | Must read-deserialize-modify-serialize | Direct field update (HSET) |
| **Query** | All or nothing | Can retrieve specific fields |
| **Speed (small data)** | Faster (single operation) | Slightly slower |
| **Speed (large data)** | Slower (serialize entire object) | Faster (targeted updates) |
| **Use Case** | Simple objects, infrequent updates | Complex objects, frequent field updates |

## Features

- **JSON Method**: Simple, atomic updates, good for small immutable data
- **Hash Method**: Efficient field-level access, better for complex user profiles
- **Easy Switching**: Test both methods with same API structure

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
```

## Best Practices

- Use **JSON** for: small, simple objects that are updated atomically
- Use **Hash** for: large, complex objects with frequent individual field updates
- Use **Hash** for: user profiles, product details, settings objects
- Use **JSON** for: API responses, immutable snapshots, simple configurations

## Files

- `package.json` - Project configuration
- `src/index.js` - Main server with JSON and Hash comparison
