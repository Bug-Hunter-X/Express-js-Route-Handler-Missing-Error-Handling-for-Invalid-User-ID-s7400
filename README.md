# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the code attempts to parse a user ID from a route parameter without checking if the parameter is a valid number. This can lead to unexpected crashes or unexpected behavior.

## Bug Description
The `/users/:id` route attempts to fetch a user from an array based on the ID provided in the URL.  If the `id` parameter is not a valid number, `parseInt(userId)` will return `NaN`, causing the `.find()` method to fail silently and returning `undefined`. The absence of proper error handling in this scenario can lead to application crashes or unexpected behavior.

## Bug Solution
The solution involves adding error handling to validate the `userId` and gracefully handle cases where the user is not found or the `userId` is invalid.