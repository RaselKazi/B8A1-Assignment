# B8A1 — Problem Solving with TypeScript & OOP

This repository contains solutions for the B8A1 assignment covering TypeScript fundamentals, generics, type narrowing, asynchronous programming, and object-oriented programming.

## Project structure

```text
.
├── solutions.ts
├── type-vs-interface.md
├── type-narrowing.md
└── README.md
```

## Requirements

- Node.js (LTS recommended)
- TypeScript

## Implemented problems

1. `multiplyValue` — optional multiplier with a default of `2`.
2. `processInput` — union types and `typeof` narrowing.
3. `formatCoordinate` — readonly coordinate tuple.
4. `concatenateArrays` — generic rest parameters.
5. `Course` and `getPopularCourses` — interface and non-mutating filtering.
6. `pluckValues` — generic property selection with `keyof`.
7. `Employee` and `Manager` — inheritance and access modifiers.
8. `validateAgeAsync` — Promise resolution and rejection.

## Technical blogs

- [Type vs Interface](./type-vs-interface.md)
- [Type Narrowing](./type-narrowing.md)

## Notes

The assignment's coding-requirements section also names `getUniqueNumbers`, `Product`, and `updateProductPrice`, but the problem descriptions do not define their signatures or expected behavior. They are intentionally not guessed here. Confirm the missing specifications with the instructor before adding implementations.

All required problem solutions are in the single `solutions.ts` file. No `any`, sample calls, or `console.log` statements are used in that submission file.
'''
