## Introduction

TypeScript provides both `type` aliases and `interface` declarations to describe the shape of data. They often look interchangeable, but they support different capabilities. Choosing deliberately makes a codebase easier to extend and maintain.

## Understanding the differences

An interface is commonly used to describe object contracts. Interfaces can be extended with `extends`, and declarations with the same name are merged through declaration merging.

```ts
interface User {
  id: number;
  name: string;
}

interface Admin extends User {
  permissions: string[];
}
```

A type alias can represent more than object shapes. It can describe unions, intersections, primitives, tuples, and function signatures.

```ts
type Status = "pending" | "active" | "blocked";

type ApiResult<T> =
  | { success: true; data: T }
  | { success: false; error: string };
```

Both interfaces and object type aliases support many similar object-composition patterns. However, a type alias cannot be reopened through declaration merging. This distinction matters when designing public libraries or extending third-party declarations.

## When should you choose one?

Prefer an interface for object-oriented contracts, class implementation, and object shapes that may be extended by consumers. Prefer a type alias when defining unions, mapped or conditional types, tuples, and other type expressions. Consistency within a project is also important.

## Conclusion

Neither option is universally better. Use interfaces for extensible object contracts and type aliases for flexible type composition. Select the construct that communicates the intended design most clearly.
'''
(base / "type-vs-interface.md").write_text(blog1, encoding="utf-8")
