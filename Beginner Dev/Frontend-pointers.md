# Common Frontend Theoretical Questions


## JavaScript

### What is a closure and what is a closure function?

A **closure** is created when a function remembers variables from its outer (lexical) scope.  

A **closure function** is a function that retains access to those outer-scope variables even after the outer function has finished executing.

This is possible because in JavaScript, variables are not garbage-collected as long as they are still referenced by a function.

---

### Callback Function

A callback function is a function that is passed as an argument to another function and is executed later, usually after an event or an asynchronous operation is completed.

---

### Handlers

Handlers are functions that are responsible for handling a specific event, request, or action, such as a click event, an API request, or an error.

---

### Events

Events are actions or occurrences triggered by user interactions or by the system, such as clicking a button, pressing a key, submitting a form, or loading a page.

---

### Hoisting in JavaScript

Hoisting is JavaScript’s behavior where variable and function declarations are moved to the top of their scope during compilation, allowing them to be accessed before their declaration in the code.

---

## React.js Questions & Model Answers

### What are the main features of React?

React is a component-based library for building user interfaces.  
Key features include a virtual DOM for performance optimization, reusable components, hooks for state and side-effect management, and unidirectional data flow for predictable application behavior.

---

### Difference between props and state?

Props are external inputs passed to a component by its parent and are immutable.  
State is internal to a component, mutable, and used to manage local data and UI behavior.

---

### How does the virtual DOM work?

React maintains a virtual DOM, which is a lightweight copy of the real DOM.  
When state or props change, React updates the virtual DOM and efficiently applies only the necessary changes to the real DOM using a diffing algorithm.

---

### What are hooks?

Hooks are functions such as `useState` and `useEffect` that allow developers to manage state and lifecycle features directly within functional components, eliminating the need for class components.

---

### Explain “lifting state up”.

Lifting state up means moving shared state to the closest common ancestor component so that multiple child components can access and update it.  
This helps maintain predictable and organized data flow.

---

## Next.js Questions & Model Answers

### Advantages of Next.js over plain React?

Next.js provides features like server-side rendering (SSR), static site generation (SSG), built-in routing, image optimization, and API routes.  
These features improve SEO, performance, and developer productivity.

---

### SSR vs SSG

SSR (Server-Side Rendering) generates pages on every request and is suitable for highly dynamic content.  
SSG (Static Site Generation) builds pages at build time, offering faster load times and better performance for static content.

---

### How do API routes work in Next.js?

API routes are serverless functions created inside the `/pages/api` directory.  
They handle backend logic such as data fetching, authentication, and act as API endpoints within the same project.

---

### How do you deploy a Next.js app?

Next.js applications can be deployed on platforms like Vercel, Netlify, or any Node.js-supported server.  
Platforms like Vercel provide built-in support for SSR, SSG, and serverless functions.

---

## Redux Questions & Model Answers

### What is Redux and why use it?

Redux is a state management library that enables predictable state updates using actions and reducers.  
It centralizes application state, improves debugging, and simplifies managing complex application logic.

---

### Redux data flow

Redux follows a unidirectional data flow:  
Component dispatches an action → reducer processes the action → store updates the state → UI re-renders based on the updated state.

---

### Benefits of Redux Toolkit

Redux Toolkit simplifies Redux development by providing utilities for creating reducers, actions, and handling asynchronous logic.  
It reduces boilerplate code and encourages best practices.

---

### Redux vs Context API

Redux is suitable for large-scale applications requiring_attach advanced state management, middleware, and debugging tools.  
The Context API is best for simple global state needs but may cause performance issues with frequent updates.

---

## Very Basic Web Development Questions

- What are semantic HTML elements, and why are they important?
- Explain relative, absolute, and fixed positioning in CSS.
- What is the difference between `visibility: hidden` and `display: none`?
- How do media queries work in CSS?
