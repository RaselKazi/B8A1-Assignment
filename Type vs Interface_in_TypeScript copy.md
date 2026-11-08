## Introduction

A union type allows a value to belong to more than one type. Before using a value, TypeScript often needs evidence about which member of the union is currently present. Type narrowing is the process of using runtime checks to reduce a broad type to a more specific one.

## Practical narrowing techniques

The `typeof` operator is useful for primitive values. For example, a function receiving `string | number` can safely call string or numeric operations after checking the value.

```ts
function formatValue(value: string | number): string {
  if (typeof value === "string") {
    return value.trim().toLowerCase();
  }

  return value.toFixed(2);
}
```

Use `instanceof` to distinguish class instances. It checks whether an object's prototype chain contains a class's prototype.

```ts
class ApiError extends Error {
  constructor(message: string) {
    super(message);
    this.name = "ApiError";
  }
}

function getErrorMessage(error: Error | string): string {
  if (error instanceof Error) {
    return error.message;
  }

  return error;
}
```

The `in` operator checks whether a property exists on an object. It is useful for discriminating between object types.

```ts
type EmailUser = { email: string };
type PhoneUser = { phone: string };

function getContact(user: EmailUser | PhoneUser): string {
  return "email" in user ? user.email : user.phone;
}
```

## Conclusion

Type narrowing makes union types practical without unsafe assertions. Prefer clear runtime checks such as `typeof`, `instanceof`, and `in`; they improve readability and help the compiler verify that each operation is valid.
'''
(base / "type-narrowing.md").write_text(blog2, encoding="utf-8")
