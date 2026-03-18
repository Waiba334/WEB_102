# Reflection - Social Media API Project

## What I Learned

### Part 1 - API Design
Before writing any code, I learned the importance of planning and designing
API endpoints properly. Creating the design table helped me understand:

- **REST conventions**: How to properly name endpoints using nouns instead
  of verbs, for example using /users instead of /getUsers.

- **HTTP Methods**: The difference between GET, POST, PUT, and DELETE and
  when to use each one appropriately.

- **HTTP Status Codes**: Understanding which status codes to return for
  different scenarios, such as 200 for success, 201 for created, 404 for
  not found, and 401 for unauthorized.

- **Request and Response structure**: How to structure request bodies and
  response bodies in a consistent and predictable way.

### Part 2 - API Implementation

#### Server Setup
Setting up the Express server taught me how middleware works in Node.js.
I learned that middleware functions run in sequence and each one can
modify the request and response objects before passing them to the next
function using next().

I learned about important security and utility packages:
- **Helmet** protects the app by setting various HTTP headers
- **CORS** controls which domains can make requests to the API
- **Morgan** logs HTTP requests which is very useful for debugging

#### MVC Architecture
This project introduced me to the MVC (Model-View-Controller) pattern:
- **Controllers** handle the business logic
- **Routes** define the URL endpoints and connect them to controllers
- **Models** (represented by mock data in this project) manage the data

This separation of concerns makes the code much more organized and
easier to maintain compared to putting everything in one file.

#### Error Handling
I learned how to implement centralized error handling in Express using:
- A custom ErrorResponse class that extends the built in Error class
- An async wrapper middleware that catches errors in async functions
- A global error handler middleware that formats all errors consistently

This approach is much better than writing try catch blocks in every
controller function.

#### Pagination
Implementing pagination taught me how to slice arrays based on page
number and limit, and how to calculate total pages. This is an essential
feature for any API that returns lists of data.

#### Content Negotiation
One of the most interesting things I learned was content negotiation.
The same endpoint can return different formats (JSON or XML) based on
the Accept header in the request. I learned how to override the res.json
method to check the Accept header and return the appropriate format.

## Challenges I Faced

1. **Understanding Middleware**: At first the concept of middleware was
   confusing. I did not understand how next() worked and why it was
   needed. After practicing and reading the documentation, I understood
   that middleware functions form a chain and next() passes control to
   the next function in that chain.

2. **Async Error Handling**: Understanding why we need an async wrapper
   was challenging. Without it, errors in async functions would not be
   caught by the error handler middleware. The async wrapper ensures
   all promise rejections are forwarded to the error handler.

3. **Project Structure**: Deciding how to organize files and folders
   took some thought. Following the MVC pattern helped but required
   understanding how all the pieces fit together.

4. **Content Negotiation**: Implementing XML conversion was tricky
   because I had to handle nested objects and arrays differently.
   The recursive nature of the conversion logic required careful
   thought and testing.

5. **Module Not Found Errors**: I encountered several module not found
   errors when files were not created or had incorrect paths. This
   taught me the importance of checking file paths and making sure
   all required files exist before running the server.

## What I Would Do Differently

1. Use a real database like MongoDB or PostgreSQL instead of mock data
   so the data persists between server restarts.
2. Implement proper JWT authentication instead of the simulated
   X-User-Id header approach.
3. Add input validation middleware using a library like Joi or
   express-validator.
4. Write automated tests using Jest or Mocha to test all endpoints.
5. Add rate limiting to prevent abuse of the API.
6. Use environment variables for all configuration values.

## Comparison: Frontend vs Backend Development

Working on both the TikTok clone (frontend) and the Social Media API
(backend) gave me a complete picture of full-stack development:

- **Frontend** focuses on user interface, user experience, and how
  data is displayed to the user.
- **Backend** focuses on data management, business logic, security,
  and how data is stored and retrieved.

Both are equally important and they work together to create a complete
web application. The API I built in this practical could potentially
serve as the backend for the TikTok clone I built in the previous
practical.

## Conclusion

Building this RESTful API from scratch gave me a solid understanding
of how backend development works. I now understand how web applications
communicate with servers, how data flows from the database to the user
interface, and how to design APIs that are consistent, secure, and easy
to use. These skills are fundamental for any full-stack developer and
will be valuable in future projects.