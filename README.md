# WEB_102

# Social Media API

A RESTful API for a social media platform built with Node.js and Express.js.

## Tech Stack

- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **Morgan** - HTTP request logger
- **Helmet** - Security middleware
- **CORS** - Cross-Origin Resource Sharing
- **Dotenv** - Environment variable management
- **Nodemon** - Development auto-restart


## Project Structure

social-media-api/
├── controllers/
│   ├── userController.js
│   ├── postController.js
│   ├── commentController.js
│   ├── likeController.js
│   └── followerController.js
├── routes/
│   ├── users.js
│   ├── posts.js
│   ├── comments.js
│   ├── likes.js
│   └── followers.js
├── middleware/
│   ├── errorHandler.js
│   ├── formatResponse.js
│   └── async.js
├── utils/
│   ├── mockData.js
│   └── errorResponse.js
├── public/
│   └── docs.html
├── .env
├── .gitignore
├── server.js
└── package.json


## Security Features

- **Helmet.js** - Sets various HTTP headers for security
- **CORS** - Controls which domains can access the API
- **Input Validation** - Validates request data before processing
- **Error Handling** - Centralized error handling middleware

