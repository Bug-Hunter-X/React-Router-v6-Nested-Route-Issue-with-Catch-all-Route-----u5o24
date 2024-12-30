# React Router v6 Nested Route Issue

This repository demonstrates a subtle bug in React Router v6 when using nested routes in conjunction with a catch-all route (`*`).  The catch-all route incorrectly prevents nested routes from rendering.

## Bug Description

The problem arises when a parent `Routes` component contains a catch-all route (`path="*"`). This route intercepts all navigation attempts, even those intended for nested routes within child `Routes` components. This leads to unexpected behavior where nested routes never render.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate to the `/about` route. You'll observe that the `NotFound` component renders instead of the `About` component.

## Solution

The solution involves restructuring the routes to avoid using a catch-all route in the parent `Routes`.  The catch-all route should be placed at the lowest level where it's actually needed.