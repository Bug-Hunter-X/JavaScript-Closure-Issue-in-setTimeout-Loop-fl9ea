# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common closure issue in JavaScript when using `setTimeout` within a loop.  The expected behavior is to log the numbers 0-9 with a one-second delay between each. However, due to the way closures work, the loop completes before the `setTimeout` callbacks execute, resulting in all callbacks logging the final value of 'i' (which is 10). 

## Bug Description:
The problem lies in how JavaScript handles closures. Each `setTimeout` callback function creates a closure over the variable `i`.  However, by the time these callbacks finally execute, the loop has already finished, and 'i' has its final value of 10. 

## Solution:
The solution involves using an Immediately Invoked Function Expression (IIFE) or `let` within the loop to create a new scope for each iteration, ensuring each callback captures its own unique value of 'i'.