# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to clear the interval in the cleanup function. This leads to memory leaks and unexpected behavior.

## Bug

The `bug.js` file shows a React component that uses `setInterval` to update a counter every second.  However, it fails to include a cleanup function within the `useEffect` hook to clear the interval. This means that the interval continues to run even after the component unmounts, causing a memory leak.

## Solution

The `bugSolution.js` file demonstrates the correct way to use `setInterval` in a React component. The `useEffect` hook now includes a cleanup function that uses `clearInterval` to stop the interval when the component unmounts or updates.