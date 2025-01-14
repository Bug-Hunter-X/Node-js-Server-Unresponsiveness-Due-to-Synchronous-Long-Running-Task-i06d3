# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to a long-running synchronous operation within the request handler.  The `bug.js` file contains the problematic code.  The solution is shown in `bugSolution.js`.

## Problem

Node.js is single-threaded.  When a long-running synchronous task is executed in the request handler, it blocks the event loop, preventing other requests from being processed. This leads to unresponsiveness and potential hangs.

## Solution

The solution involves using asynchronous operations or offloading long-running tasks to a worker thread or other process to prevent blocking the event loop.  The `bugSolution.js` file demonstrates the use of asynchronous operations using `setTimeout`.  For even more robust solutions in a real application, consider using worker threads or message queues.