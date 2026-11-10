# Type vs Interface in TypeScript: What's the Difference?

In TypeScript, both `type` and `interface` help describe the structure of data. They tell TypeScript which properties an object should have and what types of values those properties can contain.

## Three Important Differences Between Type and Interface

### 1. Extending

We can extend an interface using `extends`.

```ts
interface Animal {
  name: string;
}

interface Dog extends Animal {
  breed: string;
}
```

With `type`, we use `&` (intersection).

```ts
type Animal = {
  name: string;
};

type Dog = Animal & {
  breed: string;
};
```

Both approaches create a `Dog` type with `name` and `breed` properties.

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

However, you cannot declare two type aliases with the same name in the same scope.

### 3. What They Can Describe

- `interface`: Mainly describes object structures.
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

## 5. Real-World Example

Imagine you are building an e-commerce application.

```ts
interface Product {
  id: string;
  name: string;
  price: number;
}

type ProductStatus = "available" | "out-of-stock";

const product: Product = {
  id: "P001",
  name: "Laptop",
  price: 50000,
};

const status: ProductStatus = "available";
```

Here, we use `interface` to describe product information and `type` to define the possible product statuses.

## Conclusion

Think of `interface` as a way to describe object structures and `type` as a more flexible tool for defining different kinds of data.

**Remember:** Both are useful, and neither is always better. Choose the one that makes your code easier to understand and maintain.
