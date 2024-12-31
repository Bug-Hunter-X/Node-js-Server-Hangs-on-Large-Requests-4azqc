# Node.js Server Hang on Large Requests

This repository demonstrates a common issue in Node.js where servers can hang when receiving large requests without proper error handling. The `server.js` file shows the problematic code, while `serverSolution.js` provides a fix.

## Problem

The server in `server.js` doesn't handle potential errors during request processing, specifically when dealing with large request bodies. This can lead to the server becoming unresponsive, requiring a restart.

## Solution

The solution in `serverSolution.js` addresses this by adding an `error` event listener to the request object (`req.on('error', ...)`). This listener catches potential errors and prevents the server from hanging. The server gracefully handles errors by sending appropriate error responses to the client.

## How to Run

1. Clone this repository.
2. Navigate to the directory in your terminal.
3. Run `node server.js` (or `node serverSolution.js`) to start the server.
4. Send a large request to the server (e.g., using a tool like `curl` with a large JSON payload) to observe the behavior.