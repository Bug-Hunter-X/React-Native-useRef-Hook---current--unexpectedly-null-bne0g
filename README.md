# React Native useRef Hook: Unexpectedly Null 'current' Property

This repository demonstrates a common issue encountered when using the `useRef` hook in React Native functional components.  The problem arises when accessing the `current` property of the ref, which unexpectedly returns `null` even after the component has mounted. This often happens when attempting to access the ref from within a callback function or after a state update.

The `useRefBug.js` file reproduces the issue, while `useRefSolution.js` provides a corrected implementation.

## Steps to Reproduce

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` or `yarn install`.
4. Run the app using your preferred React Native development environment.
5. Observe the console output and the behavior of the component.

## Solution

The issue is resolved by ensuring that the ref is accessed *after* the component has fully mounted and rendered.  This can be achieved by using the `useEffect` hook with an empty dependency array, thereby ensuring the callback is executed only once after the initial render.