slidenumbers: true

# Invariant

---

## What is an Invariant?

---

> An expression whose value doesn't change during program execution

---

## How can we use this?

---

### Assert state which your program assumes to be true.

---

## Usage

---

`npm install invariant`

---

```
var invariant = require('invariant');

// No errors
invariant(true, 'This will not throw');

// Error: Invariant Violation: This will throw an error with this message
invariant(false, 'This will throw an error with this message');
```

---

## Real World

---

```

export dummyMiddleware = ({ dispatch }) => next => action => {
    ...

    invariant(
      actionTypes.length === 3,
      'You must provide 3 action types, one for PENDING, FULFILLED, and REJECTED'
    );

    invariant(
      actionTypes.every(i => typeof i === 'string'),
      'Every action type must be a string'
    );

    const { actionTypes } = action;
    const [ PENDING, FULFILLED, REJECTED ] = actionTypes;

    ...
}
```

---

## Thank You
