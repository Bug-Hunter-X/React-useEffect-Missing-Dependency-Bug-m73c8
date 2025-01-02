# React useEffect Missing Dependency Bug
This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The counter component does not update as expected because the `count` state variable is not included in the dependency array of the `useEffect` hook. This leads to the interval function only being set up once during initial render. The corrected version includes `count` in the dependency array which correctly updates the counter every second. 

## Bug
The bug lies in the `MyComponent` function. The `useEffect` hook is intended to update the counter every second, but due to the missing dependency, it only runs once during the initial mount.  This is a subtle error that can be hard to debug without understanding how the dependencies affect `useEffect`'s behavior.

## Solution
The solution involves adding `count` to the dependency array of `useEffect`. This ensures that the interval is recreated whenever the `count` value changes, resulting in the expected counter behavior.