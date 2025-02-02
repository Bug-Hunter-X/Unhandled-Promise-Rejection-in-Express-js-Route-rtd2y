# Unhandled Promise Rejection in Express.js
This repository demonstrates a common error in Express.js applications: neglecting to handle promise rejections in asynchronous route handlers.  Failure to handle these rejections can lead to silent failures, making debugging significantly harder.

## The Problem
The `bug.js` file showcases an Express.js route that performs an asynchronous operation (`someAsyncOperation()`).  However, it omits any error handling within the `.catch()` block. If `someAsyncOperation()` rejects, the error will be silently swallowed, and the application will continue to run without providing any indication of the failure.

## The Solution
The `bugSolution.js` demonstrates the corrected approach.  It includes comprehensive error handling in the `.catch()` block.  This allows the application to gracefully handle errors, preventing unexpected behavior and enabling appropriate logging or responses to the client.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install express`.
4. Run `node bug.js` (to observe the silent failure) or `node bugSolution.js` (to observe proper error handling).