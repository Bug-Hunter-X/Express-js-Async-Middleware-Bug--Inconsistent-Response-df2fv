# Express.js Async Middleware Bug: Inconsistent Response

This repository demonstrates a common bug in Express.js applications involving asynchronous middleware and inconsistent responses.

## Bug Description
The bug arises when an asynchronous operation (like fetching data from a database) is performed within a request handler, and the response is sent before the operation completes.  This can result in inconsistent or incorrect data being sent to the client.

## Bug Reproduction
1. Clone this repository.
2. Run `npm install` to install the dependencies.
3. Run `node bug.js` to start the server.
4. Make a request to `/users/:id` (replace :id with a valid or invalid ID).
5. Observe that sometimes the correct data is returned, and sometimes the response is delayed or incomplete.

## Solution
The solution involves ensuring the response is sent only after the asynchronous operation completes.