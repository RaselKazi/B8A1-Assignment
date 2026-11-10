# Type vs Interface in TypeScript: Whats the Difference?

##

Type aliases and interfaces are both used to define custom types in TypeScript. Both `type` and `interface` help describe the shape of data. This blog will go over the similarities and differences between them. When to use each one. Lets get started.

- **Type Aliases:** work with unions, tuples, primitive types, function types and object types.

- **Interfaces:** are mainly used for defining the shape of objects and support extension and declaration merging.

## Three Differences Between Type and Interface

## 1. Extending

You can extend an interface using the `extends` keyword.

```ts
interface Animal {
  name: string;
}

interface Dog extends Animal {
  bulldog: string;
}
```

With `type` you use the `&` operator (intersection).

```ts
type Animal = {
  name: string;
};

type Dog = Animal & {
  bulldog: string;
};
```

Both can be extended,. Only interfaces support declaration merging.

### 2. Declaration Merging

When you have two interfaces with the name they are automatically merged.

```ts
interface Student {
  name: string;
}

interface Student {
  age: number;
}
```

Now the `Student` type has both `name` and `age` properties.

You cannot define two type aliases with the same name. That would cause an error.

### 3. What They Can Describe

- `interface`: works best for describing object shapes. It's clean and easy to read.

- `type`: can describe objects, strings, numbers, unions, tuples and many other types.

## 4. When Should You Use Them?

| Use Case             | Recommended |
| -------------------- | ----------- |
| Object structures    | `interface` |
| API response objects | Either      |
| Union types          | `type`      |
| Primitive aliases    | `type`      |
| Tuples               | `type`      |
| Declaration merging  | `interface` |

##

Think of `interface` as a way to describe the structure of objects. Think of `type`, as a flexible tool that can define many kinds of data. Choose based on what you're trying to do.
