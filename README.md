# React 19 useEffect setInterval memory leak
This repository demonstrates a common mistake when using setInterval within a React 19 useEffect hook, resulting in a memory leak.  The `bug.js` file shows the incorrect implementation, while `bugSolution.js` provides the correct solution.

## Problem
The problem lies in failing to properly clean up the interval created by `setInterval`.  Without a cleanup, the interval continues to run indefinitely even after the component unmounts, leading to memory leaks. 

## Solution
The solution involves adding a return function to the useEffect hook.  This function clears the interval using `clearInterval` when the component unmounts, preventing memory leaks.