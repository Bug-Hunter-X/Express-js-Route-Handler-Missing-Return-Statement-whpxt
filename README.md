# Express.js Route Handler Missing Return Statement

This repository demonstrates a common error in Express.js route handlers: omitting a `return` statement within a conditional branch.  This can lead to unexpected behavior, where multiple responses might be sent, or unintended logic execution.

## Bug

The `bug.js` file contains an Express.js route handler that fetches user data. If the user is not found, it sends a 404 response. However, if a user *is* found, it continues execution and implicitly sends another response. 

## Solution

The `bugSolution.js` file corrects this by adding a `return` statement before `res.send(userData)`. This ensures that only one response is sent, preventing unexpected behavior.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory in your terminal.
3. Run `node bug.js` and make requests to `/users/:id` with both existing and non-existing IDs. Observe the responses.
4. Repeat with `node bugSolution.js`. Compare the behavior.
