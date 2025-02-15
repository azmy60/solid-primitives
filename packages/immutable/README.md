<p>
  <img width="100%" src="https://assets.solidjs.com/banner?type=Primitives&background=tiles&project=Immutable" alt="Solid Primitives Immutable">
</p>

# @solid-primitives/immutable

[![turborepo](https://img.shields.io/badge/built%20with-turborepo-cc00ff.svg?style=for-the-badge&logo=turborepo)](https://turborepo.org/)
[![size](https://img.shields.io/bundlephobia/minzip/@solid-primitives/immutable?style=for-the-badge&label=size)](https://bundlephobia.com/package/@solid-primitives/immutable)
[![version](https://img.shields.io/npm/v/@solid-primitives/immutable?style=for-the-badge)](https://www.npmjs.com/package/@solid-primitives/immutable)
[![stage](https://img.shields.io/endpoint?style=for-the-badge&url=https%3A%2F%2Fraw.githubusercontent.com%2Fsolidjs-community%2Fsolid-primitives%2Fmain%2Fassets%2Fbadges%2Fstage-2.json)](https://github.com/solidjs-community/solid-primitives#contribution-process)

Functional programming helpers for making non-mutating changes to data. Keeping it immutable.

## Installation

```bash
npm install @solid-primitives/immutable
# or
yarn add @solid-primitives/immutable
```

## How to use it

```ts
import { pick } from "@solid-primitives/immutable";

const original = { foo: 123, bar: "baz" };
const newObj = pick(original, "foo");
original; // { foo: 123, bar: "baz" }
newObj; // { foo: 123 }
```

Use it for changing signals:

```ts
import { push, update } from "@solid-primitives/immutable";

const [list, setList] = createSignal([1, 2, 3]);
setList(p => push(p, 4));

const [user, setUser] = createSignal({
  name: "John",
  street: { name: "Kingston Cei", number: 24 }
});
setUser(p => update(p, "street", "number", 64));
```

## List of functions:

### Copying

- **`shallowArrayCopy`** - make shallow copy of an array
- **`shallowObjectCopy`** - make shallow copy of an object
- **`shallowCopy`** - make shallow copy of an array/object
- **`withArrayCopy`** - apply mutations to the an array without changing the original
- **`withObjectCopy`** - apply mutations to the an object without changing the original
- **`withCopy`** - apply mutations to the an object/array without changing the original

### Array

- **`push`** - non-mutating `Array.prototype.push()`
- **`drop`** - non-mutating function that drops n items from the array start
- **`dropRight`** - non-mutating function that drops n items from the array end
- **`filterOut`** - standalone `Array.prototype.filter()` that filters out passed item
- **`filter`** - standalone `Array.prototype.filter()`
- **`sort`** - non-mutating `Array.prototype.sort()` as a standalone function
- **`sortBy`** - Sort an array by object key, or multiple keys
- **`map`** - standalone `Array.prototype.map()` function
- **`slice`** - standalone `Array.prototype.slice()` function
- **`splice`** - non-mutating `Array.prototype.splice()` as a standalone function
- **`fill`** - non-mutating `Array.prototype.fill()` as a standalone function
- **`concat`** - Creates a new array concatenating array with any additional arrays and/or values.
- **`remove`** - Remove item from array
- **`removeItems`** - Remove multiple items from an array
- **`flatten`** - Flattens a nested array into a one-level array
- **`filterInstance`** - Flattens a nested array into a one-level array
- **`filterOutInstance`** - Flattens a nested array into a one-level array

### Object

- **`omit`** - Create a new subset object without the provided keys
- **`pick`** - Create a new subset object with only the provided keys
- **`split`** - Split object into multiple subset objects.
- **`merge`** - Merges multiple objects into a single one.

### Object/Array

- **`get`** - Get a single property value of an object by specifying a path to it.
- **`update`** - Change single value in an object by key, or series of recursing keys.

### Number

- **`add`** - `a + b + c + ...` _(works for numbers or strings)_
- **`substract`** - `a - b - c - ...`
- **`multiply`** - `a * b * c * ...`
- **`divide`** - `a / b / c / ...`
- **`power`** - `a ** b ** c ** ...`
- **`clamp`** - clamp a number value between two other values

## Changelog

See [CHANGELOG.md](./CHANGELOG.md)
