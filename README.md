# Express.js Route Handler Error: Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid input.  Specifically, the route `/users/:id` attempts to access a user by ID, but doesn't handle cases where the ID is not a valid integer. 

## The Bug
The `bug.js` file contains the flawed code. The route fails to handle scenarios where `req.params.id` cannot be converted to an integer or if a user with the specified ID is not found.  This can result in unexpected errors or application crashes.

## The Solution
The `bugSolution.js` file provides a corrected version with robust error handling. It addresses both potential problems: an invalid ID and a non-existent user.  It includes comprehensive checks and appropriate HTTP status codes for each error condition.

## How to reproduce the Bug
1. Clone this repository.
2. Run `npm install express` to install Express.js.
3. Run `node bug.js`. 
4. Send a GET request to `/users/abc` (invalid ID) or `/users/999` (non-existent user).