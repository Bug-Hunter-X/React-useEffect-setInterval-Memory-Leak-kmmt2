# React useEffect setInterval Memory Leak
This example demonstrates a common mistake in React: using `setInterval` within the `useEffect` hook without a cleanup function. This leads to memory leaks and unexpected behavior.

## Problem
The `setInterval` function is called repeatedly, creating a new interval every time the component renders.  When the component unmounts, these intervals continue to run in the background, causing memory leaks.  The counter will continue to increment even after the component is removed from the DOM. 

## Solution
The solution involves returning a cleanup function from `useEffect` that clears the interval when the component unmounts. This ensures that the interval is stopped when it's no longer needed.

## How to reproduce
1. Clone the repository.
2. Navigate to the directory in your terminal.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the counter behavior and see that it continues to increment even if you navigate away from the component.