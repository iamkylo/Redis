# 06 - Email Queue with Redis List

Job queue system using Redis Lists for processing emails asynchronously.

## Overview

This project demonstrates:
- Using Redis Lists (LPUSH/RPOP) as a queue
- FIFO (First-In-First-Out) job processing
- Adding jobs to the queue
- Processing jobs from the queue one-by-one

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

### Add Email to Queue
```
POST /emails
Content-Type: application/json

{
  "to": "user@example.com",
  "subject": "Welcome Email",
  "body": "This is the email content"
}

Response: 
{
  "queued": true,
  "job": {
    "to": "user@example.com",
    "subject": "Welcome Email",
    "body": "This is the email content",
    "createdAt": "2026-05-21T16:02:55.540Z"
  }
}
```

### Process One Email from Queue
```
GET /emails/process-one

Response:
{
  "message": "EMAIL SENT",
  "job": {
    "to": "user@example.com",
    "subject": "Welcome Email",
    "body": "This is the email content",
    "createdAt": "2026-05-21T16:02:55.540Z"
  }
}
```

When queue is empty:
```
Response:
{
  "message": "no jobs in the queue"
}
```

## How It Works

1. **Add Email**: `POST /emails` adds job to Redis List using `LPUSH`
2. **Queue Storage**: All jobs stored in order (FIFO)
3. **Process Job**: `GET /emails/process-one` retrieves job using `RPOP` (removes from queue)
4. **Job Structure**: Each job contains `to`, `subject`, `body`, and `createdAt`

## Redis Commands Used

- **LPUSH** - Push job to head of list (add)
- **RPOP** - Pop job from tail of list (remove & process)

## Features

- **Queue Management**: Jobs processed in order (FIFO)
- **Job Metadata**: Tracks creation time and email details
- **Error Handling**: Handles empty queues gracefully
- **Atomic Operations**: Uses Redis atomic operations for reliability

## Environment Variables

```env
REDIS_URL=redis://localhost:6379
```

## Use Cases

- **Email Delivery**: Queue up emails to be sent asynchronously
- **Background Jobs**: Process long-running tasks in the background
- **Task Processing**: Handle incoming requests that need delayed processing
- **Rate Limiting**: Control job processing speed

## Example Workflow

```bash
# 1. Add 3 emails to queue
POST /emails
{
  "to": "alice@example.com",
  "subject": "Hello Alice",
  "body": "Message 1"
}

POST /emails
{
  "to": "bob@example.com",
  "subject": "Hello Bob",
  "body": "Message 2"
}

POST /emails
{
  "to": "charlie@example.com",
  "subject": "Hello Charlie",
  "body": "Message 3"
}

# 2. Process emails one by one
GET /emails/process-one  # Returns Alice's email
GET /emails/process-one  # Returns Bob's email
GET /emails/process-one  # Returns Charlie's email
GET /emails/process-one  # Returns "no jobs in the queue"
```

## Files

- `package.json` - Project configuration
- `src/index.js` - Email queue with Redis List implementation
