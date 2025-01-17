# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the route `/users/:id` attempts to parse the `id` parameter as an integer without any validation. This can lead to unexpected behavior or crashes if the `id` parameter is not a valid integer.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file shows how to fix this issue by adding proper input validation and error handling.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `node bug.js`.
4. Send a request to `/users/abc` (or any non-integer value).

You'll likely encounter an error because `parseInt('abc')` returns `NaN`, causing the `users.find()` method to fail unexpectedly.

## Solution

The solution involves adding checks to ensure the `userId` is a valid integer before attempting to use it.