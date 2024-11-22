# Vedina Movies API Documentation

[![Live Demo](/frontend/screenshot-1.png)](https://movies.vedina.ir)
[![Live Demo](/frontend/screenshot-2.png)](https://movies.vedina.ir)
[![Live Demo](/frontend/screenshot-3.png)](https://movies.vedina.ir)

## Overview

Vedina Movies is a comprehensive movie streaming platform API developed by Yousef Jafari for Vedina Co. This API provides endpoints for user management, movie browsing, favorites, watch history, subscription handling, payment processing, comments, and blog functionality.

## Table of Contents

- [Authentication](#authentication)
- [API Endpoints](#api-endpoints)
  - [User Management](#user-management)
  - [Movies](#movies)
  - [Favorites](#favorites)
  - [Watch History](#watch-history)
  - [Subscription](#subscription)
  - [Payment](#payment)
  - [Comments](#comments)
  - [Blog](#blog)
- [Version Info](#version-info)

## Authentication

Most endpoints require a valid session token. Include the session token in the URL where `:session` is specified.

## API Endpoints

### User Management

Base URL: `/users`

#### Register New User

```http
POST /users
Content-Type: application/json

{
  "name": "string",
  "email": "string",
  "phone": "string",
  "password": "string"
}
```

#### User Login

```http
POST /users/login
Content-Type: application/json

{
  "user": "string",
  "password": "string"
}
```

#### Get User Profile

```http
GET /users/:session
```

#### Update User Profile

```http
PATCH /users/:session
Content-Type: application/json

{
  "name": "string",
  "email": "string",
  "phone": "string"
}
```

#### Reset Password

```http
POST /users/reset-password
Content-Type: application/json

{
  "email": "string"
}
```

#### Change Password

```http
POST /users/change-password/:session
Content-Type: application/json

{
  "password": "string"
}
```

#### OTP Operations

Send OTP:

```http
GET /users/otp/send/:session
```

Verify OTP:

```http
GET /users/otp/verify/:session?otp=123456
```

### Movies

Base URL: `/movies`

#### Get All Movies

```http
GET /movies?search=string&target=title&limit=15&page=1&sort=string&order=string&basic=true&imdb=number&dub=boolean&sub=boolean&years=string&genres=string&countries=string
```

#### Get Single Movie

```http
GET /movies/:id?basic=false
```

#### Add Movie (Admin)

```http
POST /movies
Content-Type: application/json

{
  // Movie details
}
```

#### Update Movie (Admin)

```http
PUT /movies/:id
Content-Type: application/json

{
  // Updated movie details
}
```

#### Delete Movie (Admin)

```http
DELETE /movies/:id
```

### Favorites

Base URL: `/favorites`

#### Check if Movie is Favorited

```http
GET /favorites/is/:session/:movie
```

#### Get User's Favorites

```http
GET /favorites/:session
```

#### Add to Favorites

```http
GET /favorites/add/:session/:movie
```

#### Remove from Favorites

```http
GET /favorites/remove/:session/:movie
```

### Watch History

Base URL: `/watched`

#### Check if Movie is Watched

```http
GET /watched/is/:session/:movie
```

#### Get Watch History

```http
GET /watched/:session
```

#### Add to Watch History

```http
GET /watched/add/:session/:movie
```

#### Remove from Watch History

```http
GET /watched/remove/:session/:movie
```

### Subscription

Base URL: `/subscription`

#### Get Subscription Status

```http
GET /subscription/:session
```

#### Add Subscription

```http
GET /subscription/add/:session/:plan
```

### Payment

Base URL: `/pay`

#### Start Payment

```http
GET /pay/start/:session/:amount
```

#### Payment Callback

```http
GET /pay/callback/:session?trackId=string
```

### Comments

Base URL: `/comments`

#### Add Comment

```http
POST /comments/:session/:movie
Content-Type: application/json

{
  "comment": "string"
}
```

#### Get Movie Comments

```http
GET /comments/:movie
```

### Blog

Base URL: `/blog`

#### Get Blog Categories

```http
GET /blog/categories
```

#### Get All Blog Posts

```http
GET /blog?limit=number&page=number&search=string&categoryId=string&sort=string&order=string
```

#### Get Single Blog Post

```http
GET /blog/:id
```

### Version Info

```http
GET /version
```

## Response Format

All endpoints return JSON responses in the following format:

```json
{
  "status": "success",
  "data": {
    // Response data
  }
}
```

## Error Handling

Errors are returned in the following format:

```json
{
  "status": "error",
  "message": "Error message description"
}
```

## Author

- **Yousef Jafari**

## Company

- **Vedina Co.**

---

For additional support or inquiries, please contact Vedina Co. support team.
