# What I’ll do

1. **Rename files** to `.tsx` since they contain JSX.
2. **Define prop and state types** with `interface`s.
3. **Type functional components** (props) and **class components** (`Props`, `State`, and method signatures).
4. **Use safe `setState` pattern** (updater function) to avoid stale state.
5. **Add meaningful comments** explaining each change.

---

# Code 01 – Functional component (TypeScript)

```tsx
import React from "react";

interface GreetingProps {
  name: string;
}

const Greeting = ({ name }: GreetingProps) => {
  return <div>Hello, {name}!</div>;
};

export default Greeting;
```


# Code 02 – Class component (TypeScript)

```tsx

import React, { Component } from "react";
interface CounterProps {}

interface CounterState {
  count: number;
}

class Counter extends Component<CounterProps, CounterState> {
  state: CounterState = {
    count: 0,
  };
  increment = (): void => {
    this.setState((prevState) => ({ count: prevState.count + 1 }));
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}

export default Counter;
```
