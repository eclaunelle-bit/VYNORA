# 📚 API Documentation - Vynora

## Base URL
```
http://localhost:8000/api
```

## Authentication Endpoints

### Register
```
POST /auth/register
Body: {
  "email": "user@example.com",
  "password": "password123"
}
Response: {
  "message": "User registered successfully",
  "email": "user@example.com"
}
```

### Login
```
POST /auth/login
Body: {
  "email": "user@example.com",
  "password": "password123"
}
Response: {
  "access_token": "token",
  "token_type": "bearer"
}
```

### Google Login
```
POST /auth/google-login
Body: {
  "token": "google_token"
}
Response: {
  "access_token": "token",
  "token_type": "bearer"
}
```

### Apple Login
```
POST /auth/apple-login
Body: {
  "token": "apple_token"
}
Response: {
  "access_token": "token",
  "token_type": "bearer"
}
```

### Facebook Login
```
POST /auth/facebook-login
Body: {
  "token": "facebook_token"
}
Response: {
  "access_token": "token",
  "token_type": "bearer"
}
```

## Users Endpoints

### Get Current User
```
GET /users/me
Headers: {"Authorization": "Bearer token"}
Response: {
  "id": 1,
  "email": "user@example.com",
  "username": "username"
}
```

### Get User by ID
```
GET /users/{user_id}
Response: {
  "id": user_id,
  "email": "user@example.com",
  "username": "username"
}
```

### Update Profile
```
PUT /users/me
Headers: {"Authorization": "Bearer token"}
Body: { profile data }
```

### Search Users
```
GET /users/search/{query}
Response: {
  "results": [],
  "total": 0
}
```

### Follow User
```
POST /users/follow/{user_id}
Headers: {"Authorization": "Bearer token"}
```

### Unfollow User
```
DELETE /users/unfollow/{user_id}
Headers: {"Authorization": "Bearer token"}
```

## Posts Endpoints

### Get Feed
```
GET /posts/feed?skip=0&limit=20
Response: {
  "posts": [],
  "total": 0
}
```

### Create Post
```
POST /posts/create
Headers: {"Authorization": "Bearer token"}
Body: {
  "content": "Post content"
}
```

### Get Post by ID
```
GET /posts/{post_id}
```

### Update Post
```
PUT /posts/{post_id}
Headers: {"Authorization": "Bearer token"}
Body: {
  "content": "Updated content"
}
```

### Delete Post
```
DELETE /posts/{post_id}
Headers: {"Authorization": "Bearer token"}
```

### Like Post
```
POST /posts/{post_id}/like
Headers: {"Authorization": "Bearer token"}
```

### Comment Post
```
POST /posts/{post_id}/comment
Headers: {"Authorization": "Bearer token"}
Body: {
  "content": "Comment content"
}
```

## Messages Endpoints

### Get Conversations
```
GET /messages/conversations?skip=0&limit=20
Response: {
  "conversations": [],
  "total": 0
}
```

### Get Conversation Messages
```
GET /messages/conversations/{conversation_id}
```

### Send Message
```
POST /messages/send
Headers: {"Authorization": "Bearer token"}
Body: {
  "receiver_id": 123,
  "content": "Message content"
}
```

### Delete Message
```
DELETE /messages/{message_id}
Headers: {"Authorization": "Bearer token"}
```

## Groups Endpoints

### Get All Groups
```
GET /groups/
Response: {
  "groups": [],
  "total": 0
}
```

### Create Group
```
POST /groups/create
Headers: {"Authorization": "Bearer token"}
Body: {
  "name": "Group Name",
  "description": "Group description"
}
```

### Get Group Details
```
GET /groups/{group_id}
```

### Join Group
```
POST /groups/{group_id}/join
Headers: {"Authorization": "Bearer token"}
```

### Leave Group
```
DELETE /groups/{group_id}/leave
Headers: {"Authorization": "Bearer token"}
```

## Health Check

### Server Status
```
GET /health
Response: {
  "status": "healthy"
}
```

### Root Endpoint
```
GET /
Response: {
  "message": "Bienvenue sur Vynora API",
  "version": "1.0.0",
  "status": "online"
}
```
