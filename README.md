# React useEffect Hook Runs on Every Render

This repository demonstrates a common React performance issue: an `useEffect` hook running after every render because it lacks dependencies.  The included `bug.js` file shows the problematic code, while `bugSolution.js` provides a corrected version.

## Problem

The `useEffect` hook in `bug.js` doesn't specify any dependencies.  As a result, it re-runs on every render of the component, causing unnecessary re-renders and potentially an infinite loop if the effect modifies the state in a way that triggers another re-render.

## Solution

The `bugSolution.js` file solves this by adding the `count` variable as a dependency array. This ensures the effect only runs when the value of `count` changes.