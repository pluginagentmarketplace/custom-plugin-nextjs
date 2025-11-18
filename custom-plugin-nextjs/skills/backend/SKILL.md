---
name: backend-skills
description: Master Node.js, Express, PHP, Laravel, Java, Spring Boot, API design, and database integration. Build scalable APIs and server applications.
---

# Backend Development Skills

## Express.js Fundamentals

```javascript
const express = require('express');
const app = express();

app.use(express.json());

// Routes
app.get('/api/users/:id', async (req, res) => {
  try {
    const user = await User.findById(req.params.id);
    res.json(user);
  } catch (error) {
    res.status(500).json({error: error.message});
  }
});

app.listen(3000);
```

## RESTful API Design

```
HTTP Methods:
GET    /api/users       - List all
GET    /api/users/:id   - Get one
POST   /api/users       - Create
PUT    /api/users/:id   - Update
DELETE /api/users/:id   - Delete

Status Codes:
200 OK          - Success
201 Created     - Resource created
400 Bad Request - Validation error
401 Unauthorized- Auth required
404 Not Found   - Resource missing
500 Server Error
```

## Database Operations

```javascript
// SQL with Sequelize
const user = await User.findByPk(1);
await user.update({email: 'new@example.com'});

// MongoDB with Mongoose
const user = await User.findById(id);
user.email = 'new@example.com';
await user.save();
```

## Authentication & Security

```javascript
// JWT Authentication
const jwt = require('jsonwebtoken');

const token = jwt.sign(
  {userId: user.id},
  process.env.JWT_SECRET,
  {expiresIn: '24h'}
);

// Middleware
const authenticateToken = (req, res, next) => {
  const token = req.headers.authorization?.split(' ')[1];
  jwt.verify(token, process.env.JWT_SECRET, (err, user) => {
    if (err) return res.sendStatus(403);
    req.user = user;
    next();
  });
};
```

## Middleware Pattern

```javascript
// Custom middleware
app.use((req, res, next) => {
  console.log(`${req.method} ${req.path}`);
  next();
});

// Error handling
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({error: 'Internal Server Error'});
});
```

## Database Query Optimization

- **Indexing**: Index frequently queried columns
- **Connection Pooling**: Reuse connections
- **Query Optimization**: Use SELECT only needed columns
- **N+1 Prevention**: Use JOINs instead of loops
- **Caching**: Cache frequently accessed data
- **Pagination**: Limit results per page

## Error Handling Best Practices

```javascript
// Structured error response
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Email is required",
    "details": [{
      "field": "email",
      "message": "Must be valid email"
    }]
  }
}
```

## Testing Backend APIs

```javascript
// Unit test with Jest
test('GET /api/users/:id returns user', async () => {
  const res = await request(app).get('/api/users/1');
  expect(res.status).toBe(200);
  expect(res.body.email).toBeDefined();
});
```

## Performance Considerations

- **Async/await** for non-blocking operations
- **Connection pooling** for databases
- **Caching** with Redis
- **Rate limiting** to prevent abuse
- **Compression** for responses (gzip)
- **Logging** for monitoring

## Key Concepts Checklist

- [ ] Express routing and middleware
- [ ] Request/response handling
- [ ] JSON parsing and validation
- [ ] Database CRUD operations
- [ ] SQL query optimization
- [ ] Authentication (JWT, OAuth)
- [ ] Error handling
- [ ] API versioning
- [ ] Rate limiting
- [ ] CORS configuration
- [ ] Environment variables
- [ ] Testing with Jest/Supertest
- [ ] Logging and monitoring
- [ ] Security best practices

---

**Source**: https://roadmap.sh
