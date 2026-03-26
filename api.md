# API Documentation

Base URL: `http://localhost:5000/api`

---

## Auth

### POST `/auth/register`
Register a new user.

**Body:**
```json
{ "name": "Arjun", "email": "arjun@example.com", "password": "secret123" }
```

**Response:** `201`
```json
{ "_id": "...", "name": "Arjun", "email": "arjun@example.com", "token": "jwt..." }
```

---

### POST `/auth/login`
Login with existing credentials.

**Body:**
```json
{ "email": "arjun@example.com", "password": "secret123" }
```

**Response:** `200` — same as register

---

## Transactions

All routes require `Authorization: Bearer <token>` header.

### GET `/transactions`
Returns all transactions for the authenticated user (sorted newest first).

---

### POST `/transactions`
Create a new transaction.

**Body:**
```json
{
  "type": "expense",
  "amount": 500,
  "category": "Food & Dining",
  "description": "Lunch at cafe",
  "date": "2025-06-01"
}
```

---

### PUT `/transactions/:id`
Update a transaction by ID.

---

### DELETE `/transactions/:id`
Delete a transaction by ID.

---

## AI

### POST `/ai/chat`
Ask an AI question about your finances.

**Body:**
```json
{ "question": "Where am I overspending?" }
```

**Response:**
```json
{ "answer": "Based on your transactions, you've spent the most on Food & Dining..." }
```
