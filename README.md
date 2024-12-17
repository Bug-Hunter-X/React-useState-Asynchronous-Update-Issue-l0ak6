# React useState Asynchronous Update

This repository demonstrates a common issue encountered when using React's `useState` hook: the asynchronous nature of updates.  The `bug.js` file shows a simple counter component where logging the count immediately after an update displays the *previous* count, not the updated one.  The solution, in `bugSolution.js`, explains how to correctly handle this using functional updates or effects.

## Bug
The bug lies in the assumption that `setCount` updates the state synchronously.  In reality, React updates the state asynchronously.  Therefore, accessing `count` immediately after `setCount` will reflect the old value.

## Solution
The solution involves using functional updates passed to `setCount`. This ensures the update is based on the latest state value, preventing race conditions.  Alternatively, using `useEffect` with the `count` dependency allows for reading the updated count after the state is updated asynchronously.