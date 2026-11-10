# Type vs Interface in TypeScript: What's the Difference?

## Introduction

Type aliases and interfaces are used to define custom types in TypeScript. both `type` and `interface` help describe the structure of data. This blog will discuss the similarities and differences between them, and the best use cases for each. Let's dive in!.

- **Type Aliases:** are suitable for unions, tuples, primitive types, function types, and object types.
- **Interfaces:** are primarily designed for defining object shapes and support extension and declaration merging.

## Three Important Differences Between Type and Interface

## 1. Extending

We can extend an interface using `extends`.

```ts
interface Animal {
  name: string;
}

interface Dog extends Animal {
  bulldog: string;
}
```

With `type`, we use `&` (intersection).

```ts
type Animal = {
  name: string;
};

type Dog = Animal & {
  bulldog: string;
};
```

Both can be extended, but interfaces support declaration merging.

### 2. Declaration Merging

Interfaces with the same name are automatically merged.

```ts
interface Student {
  name: string;
}

interface Student {
  age: number;
}
```

Now, `Student` contains both `name` and `age` properties.

However, you cannot declare two type aliases with the same name.

### 3. What They Can Describe

- `interface`: are cleaner and more readable for object structures.
- `type`: Describes objects, strings, numbers, unions, tuples, and more.

## 4. When Should You Use Them?

| Use Case             | Recommended |
| -------------------- | ----------- |
| Object structures    | `interface` |
| API response objects | Either      |
| Union types          | `type`      |
| Primitive aliases    | `type`      |
| Tuples               | `type`      |
| Declaration merging  | `interface` |

## Conclusion

Think of `interface` as a way to describe object structures and `type` as a more flexible tool for defining different kinds of data.
