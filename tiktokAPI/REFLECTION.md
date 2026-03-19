# Reflection — TikTok REST API Practical
 
## What Was This Practical About?
 
This practical was about building a REST API backend using Node.js and Express. The goal was to create a server that handles users, videos, and comments — similar to how a real TikTok backend works. We learned how to design API endpoints, write controllers, and connect routes to logic.
 
 
## What I Learned
 
### 1. What a REST API Is
Before this practical, I had a basic idea of what an API is. Now I understand that a REST API is a set of rules for how a frontend and backend talk to each other. Each URL (endpoint) does a specific job depending on the HTTP method used GET to read, POST to create, PUT to update, and DELETE to remove.
 
### 2. How Express Works
I learned how to set up an Express server from scratch. Express makes it easy to define routes and connect them to functions (controllers). Without Express, setting up a server in plain Node.js would be much more complicated.
 
### 3. The MVC Pattern
This practical followed a **Model-View-Controller** structure:
- **Model** (`models/index.js`) — stores the data
- **Controller** (`controllers/`) — contains the logic
- **Routes** (`routes/`) — connects URLs to the right controller function
 
This separation makes the code clean and easy to understand. Each file has one clear job.
 
### 4. HTTP Status Codes
I learned that every response should have a proper status code. For example:
- `200` means the request worked
- `201` means something new was created
- `404` means the item was not found
- `409` means there is a conflict, like trying to like a video you already liked
 
Sending the right status code helps the frontend understand what happened.
 
### 5. In-Memory Data Storage
Instead of a real database, we stored data in a JavaScript object. This was simple and good for learning, but I also learned the limitation all data disappears when the server restarts. A real app would use a database like MongoDB or PostgreSQL.
 
### 6. Middleware
I learned what middleware is code that runs between the request and the response. We used:
- `morgan` to log every request
- `cors` to allow cross-origin requests
- `body-parser` to read JSON data from requests
 
 
## Challenges I Faced
 
### Challenge 1 — Module Not Found Error
When I first ran the server, I got this error:
```
Error: Cannot find module '../controllers/videoController'
```
This happened because the controller files were not created yet. I learned that Node.js needs every file to actually exist before it can load it. The fix was simple create the missing files and paste the code in.
 
### Challenge 2 — Broken JSON Syntax in models/index.js
The data model file had syntax errors the comments array was not closed properly and some objects were floating outside the array. This taught me how important it is to check brackets carefully in JavaScript. One missing `]` or `}` can break the whole file.
 
### Challenge 3 — Understanding the Folder Structure
At first it was confusing why we needed so many folders and files. After completing the practical, I understand that each folder has a purpose routes handle URLs, controllers handle logic, and models handle data. This structure makes the project easier to maintain as it grows.
 
---
 
## What Went Well
 
- Once all the files were in the right place, the server started correctly on the first try
- The controller logic was straightforward to follow because each function does one clear job
- Testing with `curl` commands was a quick way to check if each endpoint worked without needing a frontend
 
 
## What I Would Do Differently
 
- **Add a real database** — using in-memory storage is fine for learning, but I would use MongoDB next time so data is saved permanently
- **Add authentication** — right now anyone can like, follow, or delete anything. A real app needs login and password protection
- **Write tests** — I would add automated tests so I can check if the API still works every time I make a change
 
 
## Key Takeaways
 
1. A REST API uses HTTP methods (GET, POST, PUT, DELETE) to perform actions on resources
2. Express makes building a Node.js server much easier with its routing system
3. Separating code into models, controllers, and routes keeps everything organized
4. Always send the correct HTTP status code with every response
5. Small errors like a missing bracket or wrong file path can stop the whole server from starting — reading error messages carefully helps fix them fast
 
 
## Overall
 
This practical gave me a solid foundation in backend development. Building a working API from scratch even a simple one helped me understand how the backend of apps like TikTok, Instagram, or Twitter actually works behind the scenes. I feel more confident about building and connecting APIs to a frontend now.