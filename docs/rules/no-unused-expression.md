# Enforce that an expression gets used

In functional programming, methods do not mutate any values or cause side-effects, and it is therefore useless to call a method without using its result. The result should be assigned to a variable, passed as a parameter of another function, etc. Unused literals are reported too as they represent dead code.

### Fail

```js
1 + 2;

foo();

Object.assign(a, b);

function foo(a, b) {
  a + b;
}
```

### Pass

```js
const sum = 1 + 2;

const result = foo();

const result = foo(Object.assign(a, b));

function foo(a, b) {
  return a + b;
}

const foo = (a, b) => a + b;
```
