# React useEffect Hook - Missing Dependency

This repository demonstrates a common error in React applications involving the `useEffect` hook.  When a state variable is used within an effect, it *must* be included in the dependency array to prevent unintended infinite loops.

## The Problem

The `bug.js` file contains a simple counter component. However, the `useEffect` hook lacks the `count` state variable in its dependency array.  This causes the effect to run after every render, triggering a new state update, which in turn triggers another render, creating an infinite loop.

## The Solution

The `bugSolution.js` file shows the corrected code. By including `count` in the dependency array, the effect only runs when the value of `count` changes, preventing the infinite loop.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory `bug.js`.
3. Run `npm start` (Make sure you have Node.js and npm installed).
4. Observe the infinite loop in the console logs.
5. Then, run the code of `bugSolution.js` and check the proper working of useEffect Hook.

This example highlights the importance of carefully managing dependencies within the `useEffect` hook to avoid performance issues and unexpected behavior in your React components.