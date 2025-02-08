# React useEffect Infinite Loop Bug

This repository demonstrates a subtle bug in React's `useEffect` hook where an empty dependency array doesn't prevent the effect from running after every render due to closure over a changing variable. 

## Bug Description
The `useEffect` hook in `bug.js` is intended to log the count only once.  However, because the function inside the effect closes over `count`, which changes on each render, the effect is triggered repeatedly, leading to an infinite loop of console logs.

## Solution
The `bugSolution.js` file demonstrates a fix by using a functional update within the `setCount` call and removing the unnecessary closure of `count`.