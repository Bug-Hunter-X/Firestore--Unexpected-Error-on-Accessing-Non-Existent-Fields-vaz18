# Firestore: Unexpected Error on Accessing Non-Existent Fields

This repository demonstrates a common yet easily overlooked issue in Firebase Firestore:  accessing non-existent fields in a document throws an error, rather than gracefully returning `undefined`. This can cause unexpected crashes in your application.

The `bug.js` file showcases the problematic code. The `bugSolution.js` provides a solution using optional chaining or the nullish coalescing operator.

## How to Reproduce

1. Clone the repository.
2. Set up a Firebase project and connect it.
3. Create a Firestore collection and document.  Make sure the document *does not* contain an 'address' field.
4. Run `bug.js`.  Observe the error. 
5. Run `bugSolution.js`. Observe the corrected behavior.

## Solution

Use optional chaining (`?.`) or the nullish coalescing operator (`??`) to safely access fields.  This ensures your code doesn't fail when a field is missing. 