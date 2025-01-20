# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation within the request handler can cause the server to hang or become unresponsive.  The main event loop gets blocked, preventing the server from handling other requests.

The `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## How to Reproduce

1. Clone this repository.
2. Run `node bug.js`.
3. Make a request to `http://localhost:3000`.  Notice the server will be unresponsive for approximately 5 seconds before responding.
4. Run `node bugSolution.js` and make another request.  The server will respond immediately.

## Solution

The key to resolving this issue is to avoid blocking the event loop.  Asynchronous operations, like using promises, are crucial for creating responsive and scalable Node.js applications.