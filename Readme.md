# Learn React

## 1. React Base: How It Relates to `createElement` in Vanilla JavaScript

React may seem like magic, but at its core, it builds upon the fundamentals of the browser's native DOM API — especially `document.createElement`. Understanding how we create UI elements imperatively in vanilla JavaScript helps us appreciate how React simplifies UI construction using a declarative style.

---

### 🧠 Imperative vs Declarative Programming

**Imperative Programming** means telling the computer **how** to do something — step by step. You explicitly instruct it to create elements, set their properties, and insert them into the DOM.

**Declarative Programming**, on the other hand, means telling the computer **what** the UI should look like, and letting the framework (React in this case) figure out how to update the DOM efficiently.

React adopts a **declarative approach**, making UI development simpler, more predictable, and easier to manage.

---

### 🛠️ Imperative Style (Vanilla JavaScript)

```js
var h1 = document.createElement('h1');
h1.textContent = 'Hello React!';
document.getElementById('root').appendChild(h1);
```

> 🔍 Here, we manually create an `h1` tag, set its text, and append it to a DOM element. This is verbose and harder to maintain as the UI becomes more complex.

---

### ⚛️ Declarative Style (React)

```jsx
import { createRoot } from 'react-dom/client';

const root = createRoot(document.getElementById('root'));

root.render(
  <div>
    <h1>Hello React!</h1>
  </div>
);
```

> 🚀 In React, we describe the UI structure in JSX (which compiles down to `React.createElement` under the hood). React takes care of efficiently updating the DOM as state or props change.

---

### 📌 Why `createElement` is the Foundation of React

Even though we often write JSX, React transforms it behind the scenes into JavaScript calls like:

```js
React.createElement('h1', null, 'Hello React!');
```

This `createElement` function is very similar in spirit to `document.createElement`, but it creates a **virtual representation of the DOM** (called the Virtual DOM). React then uses this virtual structure to efficiently update the real DOM.

---

By starting with the browser’s `createElement` and progressing to React’s `createElement`, we gain a solid understanding of how modern front-end frameworks like React are designed to abstract complexity and improve developer experience.
