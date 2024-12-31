# React 19 useEffect Bug

This repository demonstrates a bug in React 19 where the `useEffect` hook runs after every render, even when an empty dependency array is provided. This can lead to infinite loops and application crashes.

## Bug Description

The `useEffect` hook is intended to perform side effects after a component renders.  When an empty dependency array `[]` is provided, the effect should only run once after the initial render. However, in this example, the effect runs after every render, causing the console to log repeatedly and potentially leading to performance issues or crashes.

## Solution

The solution involves ensuring that the dependencies of the `useEffect` hook are correctly specified.  If the effect does not depend on any state or props, the empty dependency array `[]` should still work as expected. If it does depend on any values, include them in the dependency array. This ensures the effect only runs when those dependencies change.