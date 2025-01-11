# React UseEffect setInterval Memory Leak
This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to include a cleanup function to stop the interval when the component unmounts.

## The Problem
The provided `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it lacks a cleanup function to clear the interval when the component is unmounted. This leads to a memory leak, as the interval continues to run even after the component is no longer needed. Additionally, this will lead to unexpected behavior if you remount the component.

## The Solution
The `bugSolution.js` file shows the correct implementation. The `useEffect` hook now includes a cleanup function that uses `clearInterval` to stop the interval when the component unmounts, resolving the memory leak issue.  This ensures that resources are properly managed and prevents unexpected behavior.