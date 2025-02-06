# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common issue in JavaScript related to closures and the `setTimeout` function within a loop.  The problem arises because the closure created by `setTimeout` does not capture the value of `i` at the time of its creation, but rather captures a reference to the variable `i` itself.  As a result, by the time `setTimeout` finally executes, the loop has already completed, and `i` will hold its final value.

## Bug
The `bug.js` file contains the code exhibiting this issue.  Running this code will print the number 10 ten times instead of the expected sequence 0 through 9.

## Solution
The `bugSolution.js` file demonstrates how to solve this problem using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, capturing the current value of `i` in each separate scope.