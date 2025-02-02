# React Native Asynchronous State Update Bug

This repository demonstrates a common bug in React Native applications related to asynchronous state updates.  The bug occurs when attempting to access a state variable immediately after calling a state update function.  Because state updates are asynchronous, the old state value is used, leading to unexpected results.

## Bug Description
When a state update function (like `setCount`) is called, the UI doesn't immediately reflect the new state value.  If you try to use the updated state value before the update is complete, you'll be working with the old state value.  This can cause unexpected calculations or UI behavior.

## Solution
The solution involves using the updated state value within a callback function passed to `setCount`. The callback receives the updated state value, ensuring you always work with the correct data.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npx react-native run-android` or `npx react-native run-ios` to run the app on your emulator or device.
4. Observe the incorrect count displayed after clicking the 'Increment' button. The console will also print the old, not the new value.

## Files
- `bug.js`: Demonstrates the bug in its original form
- `bugSolution.js`: Shows the correct usage with callback to fix the bug