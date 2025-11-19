---
name: frontend-skills
description: Master HTML5, CSS3, JavaScript ES6+, React, Vue, Angular, and modern web development. Learn responsive design, accessibility, and web performance optimization.
---

# Frontend Development Skills

## HTML5 Fundamentals

```html
<!-- Semantic markup -->
<header><nav></nav></header>
<main>
  <article><h1>Title</h1><p>Content</p></article>
</main>
<footer></footer>

<!-- Accessibility -->
<img alt="descriptive text" src="image.jpg">
<button aria-label="Close">×</button>
<label for="email">Email:</label>
<input id="email" type="email">
```

## CSS3 Modern Layouts

```css
/* Flexbox */
.flex-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

/* Grid */
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

/* Responsive */
@media (max-width: 768px) {
  .grid { grid-template-columns: 1fr; }
}
```

## JavaScript ES6+ Essentials

```javascript
// Arrow functions
const add = (a, b) => a + b;

// Destructuring
const {name, age} = user;
const [first, ...rest] = array;

// Async/await
async function fetchData() {
  const data = await fetch('/api/data');
  return data.json();
}

// Array methods
arr.map(x => x * 2)
   .filter(x => x > 5)
   .reduce((acc, x) => acc + x, 0);
```

## React Hooks Pattern

```jsx
import {useState, useEffect} from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return <button onClick={() => setCount(count + 1)}>
    Count: {count}
  </button>;
}
```

## State Management

```javascript
// Context API
const UserContext = createContext();
<UserContext.Provider value={{user, setUser}}>
  <App />
</UserContext.Provider>

// useContext hook
const {user} = useContext(UserContext);
```

## Performance Optimization

```javascript
// Code splitting
const LazyComponent = lazy(() => import('./Component'));

// Memoization
const MemoizedComponent = memo(Component);
const value = useMemo(() => expensiveComputation(), [deps]);

// useCallback
const handleClick = useCallback(() => {
  // handler
}, [dependencies]);
```

## Web Performance Metrics

- **LCP** (Largest Contentful Paint) < 2.5s
- **FID** (First Input Delay) < 100ms
- **CLS** (Cumulative Layout Shift) < 0.1
- **TTL** (Time to Interactive) < 5s

## Accessibility Standards

- **WCAG 2.1 Level AA** compliance
- **Keyboard navigation** support
- **Screen reader** compatibility
- **Color contrast** ratios (4.5:1 minimum)
- **Semantic HTML** structure

## Testing Patterns

```javascript
// Unit test with Jest
test('Counter increments', () => {
  render(<Counter />);
  fireEvent.click(screen.getByRole('button'));
  expect(screen.getByText(/Count: 1/)).toBeInTheDocument();
});
```

## Key Concepts Checklist

- [ ] Semantic HTML elements
- [ ] CSS Flexbox and Grid layouts
- [ ] JavaScript async/await patterns
- [ ] React hooks (useState, useEffect, useContext)
- [ ] Component composition
- [ ] Props and state management
- [ ] Event handling
- [ ] Conditional rendering
- [ ] List rendering with keys
- [ ] Form handling
- [ ] API integration
- [ ] Error boundaries
- [ ] Performance optimization
- [ ] Accessibility compliance
- [ ] Responsive design

---

**Source**: https://roadmap.sh
