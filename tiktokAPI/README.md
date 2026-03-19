# tiktokclone
# TikTok REST API
 
A simple backend REST API built with Node.js and Express. This API works like a TikTok backend — it lets you manage users, videos, and comments.
 
 
## What This Project Does
 
This project creates a backend server that handles:
- **Users** — create, read, update, and delete user accounts
- **Videos** — upload, view, update, and delete videos
- **Comments** — add, view, update, and delete comments on videos
- **Likes** — like and unlike videos and comments
- **Followers** — follow and unfollow other users
 
 
## Technologies Used
 
| Tool | What it does |
|------|-------------|
| Node.js | Runs the JavaScript on the server |
| Express | Makes it easy to create API routes |
| Morgan | Logs every request in the terminal |
| CORS | Allows the frontend to talk to the backend |
| Body-Parser | Reads the data sent in requests |
| Dotenv | Loads secret settings from a `.env` file |
| Nodemon | Automatically restarts the server when you save changes |
 
 
## Project Structure
 
```
server/
├── .env                        # Environment variables (PORT, NODE_ENV)
├── package.json                # Project info and scripts
└── src/
    ├── app.js                  # Sets up Express and middleware
    ├── index.js                # Starts the server
    ├── controllers/
    │   ├── videoController.js  # Logic for video endpoints
    │   ├── userController.js   # Logic for user endpoints
    │   └── commentController.js# Logic for comment endpoints
    ├── models/
    │   └── index.js            # In-memory data (acts as a database)
    ├── routes/
    │   ├── videos.js           # Video API routes
    │   ├── users.js            # User API routes
    │   └── comments.js         # Comment API routes
    ├── middleware/             # (For future use)
    └── utils/                  # (For future use)
```
 
 
## How to Install and Run
 
### Step 1 — Clone or set up the project
```bash
mkdir -p server
cd server
npm init -y
```
 
### Step 2 — Install dependencies
```bash
npm install express cors morgan body-parser dotenv
npm install --save-dev nodemon
```
 
### Step 3 — Create a `.env` file
```
PORT=3000
NODE_ENV=development
```
 
### Step 4 — Start the server
```bash
npm run dev