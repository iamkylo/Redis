# 07 - Pub/Sub Redis

Real-time messaging system using Redis Pub/Sub (Publish/Subscribe) pattern.

## Overview

This project demonstrates:
- Publishing messages to Redis channels
- Subscribing to channels for real-time notifications
- Pub/Sub pattern for decoupled messaging
- Multiple subscribers receiving same message

## Installation

```bash
npm install
```

## Running

**Terminal 1 - Start Publisher API:**
```bash
npm run dev
```
Server runs on `http://localhost:3000`

**Terminal 2+ - Start Subscriber(s):**
```bash
npm run subscriber
```

## How It Works

### Publisher (API Server)
1. Exposes REST endpoint to publish notifications
2. Receives POST request with message
3. Publishes message to Redis channel
4. Returns count of active subscribers

### Subscriber(s)
1. Connects to Redis and subscribes to channel
2. Listens for incoming messages
3. Logs all received notifications
4. Can have multiple subscribers on same channel

## API Endpoints

### Publish Notification
```
POST http://localhost:3000/notifications
Content-Type: application/json

{
  "title": "Welcome Notification"
}

Response:
{
  "message": "Notification sent to 2 subscribers"
}
```

## Example Workflow

**Step 1:** Start Publisher (Terminal 1)
```bash
npm run dev
# Output: PUBLISHER SERVER IS RUNNING ON PORT 3000 !!!
```

**Step 2:** Start Subscriber 1 (Terminal 2)
```bash
npm run subscriber
# Output: Subscribed Successfully to 'notifications' channel !!!
```

**Step 3:** Start Subscriber 2 (Terminal 3)
```bash
npm run subscriber
# Output: Subscribed Successfully to 'notifications' channel !!!
```

**Step 4:** Send Notification (Terminal 1 - using Postman or curl)
```bash
curl -X POST http://localhost:3000/notifications \
  -H "Content-Type: application/json" \
  -d '{"title":"Hello Everyone"}'
```

**Output on Subscribers:**
```
Terminal 2:
Received on  notifications : { title: 'Hello Everyone', createdAt: '2026-05-21T20:42:08.559Z' }

Terminal 3:
Received on  notifications : { title: 'Hello Everyone', createdAt: '2026-05-21T20:42:08.559Z' }
```

## Redis Commands Used

- **PUBLISH** - Send message to all subscribers on a channel
- **SUBSCRIBE** - Listen for messages on a channel

## Features

- **Real-time Messaging**: Instant message delivery to all subscribers
- **Decoupled Architecture**: Publishers don't need to know subscribers
- **Multiple Subscribers**: Many clients can subscribe to same channel
- **Channel-based**: Organize messages by channels
- **Fire-and-Forget**: Messages not persisted (received in real-time only)

## Use Cases

- **Notifications**: Real-time alerts to multiple users
- **Live Updates**: Broadcasting game updates, stock prices, etc.
- **Chat Systems**: Broadcasting messages to chat rooms
- **Event Broadcasting**: System events to interested listeners
- **Live Dashboards**: Real-time data updates

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
```

## Key Differences from Queues

| Feature | Queue (List) | Pub/Sub |
|---------|------|--------|
| **Persistence** | Messages stored | Messages not stored |
| **Delivery** | FIFO, one consumer | All subscribers get message |
| **Use Case** | Task processing | Real-time notifications |
| **Timing** | Consumer processes later | Subscribers online get message |

## Limitations

⚠️ **Important**: Pub/Sub messages are NOT persisted. If no subscribers are online, messages are lost.

For persistence, use Redis Lists (Queue) or Redis Streams instead.

## Files

- `package.json` - Project configuration
- `src/index.js` - Publisher API endpoint
- `src/subscriber.js` - Subscriber that listens for messages
