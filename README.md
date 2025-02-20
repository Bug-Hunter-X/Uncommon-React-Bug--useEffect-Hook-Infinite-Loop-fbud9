# Uncommon React Bug: useEffect Hook Infinite Loop

This repository demonstrates a subtle bug that can occur when using the `useEffect` hook in React.  The problem arises from a missing or incomplete dependency array, leading to an infinite loop of re-renders.

## The Bug
The bug is located in `bug.js`. The `useEffect` hook is used to log the value of the `count` state variable. However, because `count` is not included in the dependency array, the effect runs after *every* render. This creates a situation where the state updates internally, triggering a re-render, which in turn triggers the `useEffect` again, causing an infinite loop.