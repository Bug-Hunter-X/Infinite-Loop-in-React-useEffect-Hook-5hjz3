# React useEffect Hook Bug

This repository demonstrates a common bug in React's `useEffect` hook: an infinite loop caused by a missing dependency in the dependency array. 

## Bug Description
The `useEffect` hook is used to perform side effects in functional components.  However, if a dependency is omitted from the dependency array, the effect will run after every render, potentially causing an infinite loop if the effect function modifies the state.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the infinite loop in your browser's console.

## Solution
The solution involves adding all state variables used within the `useEffect` function to its dependency array. In this case, the `count` variable must be included.  This ensures the effect only runs when `count` changes.