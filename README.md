# React: Memory Leak with setInterval in useEffect Hook

This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook.  Failure to properly clear the interval when the component unmounts leads to a memory leak.

## The Problem

The `bug.js` file shows an implementation where `setInterval` is used to update a counter every second. However, it omits the crucial cleanup function in `useEffect` to clear the interval using `clearInterval`.

This results in the interval continuing to run even after the component is unmounted, leading to a memory leak.

## The Solution

The `bugSolution.js` file demonstrates the correct way to use `setInterval` in `useEffect`.  A cleanup function is returned from `useEffect`, which calls `clearInterval` to stop the interval when the component is unmounted, preventing the memory leak.