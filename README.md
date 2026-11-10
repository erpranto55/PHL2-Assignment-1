# B8A1: Problem Solving with TypeScript & OOP

This repository contains the complete solutions for **Assignment 1 (Batch 8)**, assessing core TypeScript concepts including basic types, optional/default/rest parameters, readonly tuples, interfaces, type narrowing, generics, Promises, and Object-Oriented Programming (OOP).

---

## Repository Structure

```
.
├── solutions.ts
├── type-vs-interface.md
├── type-narrowing.md
└── README.md
```

---

##  Assignment Overview

### Problem Solving (`solutions.ts`)

All problem solutions are implemented strictly in [`solutions.ts`](solutions.ts) with explicit parameter and return types, zero noise, and exact matching output formats:

1. **`multiplyValue`**: Multiplies a value by an optional multiplier (defaulting to 2 if undefined), correctly handling `0`.
2. **`processInput`**: Uses `typeof` type narrowing to handle `string` (trim and lowercase), `number` (multiplied by 10), and `boolean` ("Active" / "Inactive").
3. **`formatCoordinate`**: Accepts a `readonly [number, number, string]` tuple and outputs formatted coordinate strings without rounding.
4. **`concatenateArrays`**: Generic function utilizing rest parameters (`...arrays: T[][]`) to merge multiple arrays of type `T` in order without `any`.
5. **`Course` & `getPopularCourses`**: Defines the `Course` interface and filters published courses with students greater than or equal to a minimum threshold without mutating the source array.
6. **`pluckValues`**: Generic function with keyof constraint (`<T, K extends keyof T>`) plucking values from an array of objects while preserving order.
7. **`Employee` & `Manager`**: Demonstrates OOP inheritance, private/protected access modifiers, and super calls with structured formatted return methods (`getDetails` and `getRoleInfo`).
8. **`validateAgeAsync`**: Async function returning `Promise<string>` that resolves after 1 second if age >= 18 or rejects immediately with an `Error` instance if under 18.

---

##  Technical Blogs

Read the accompanying technical blog posts:

- [Blog 1: Differences Between Type Aliases and Interfaces in TypeScript](type-vs-interface.md) — Explores declaration merging, primitives, union/tuple support, extension vs intersection, and best practices on when to choose each.
- [Blog 2: Understanding Type Narrowing in TypeScript](type-narrowing.md) — Explains runtime type refinement using `typeof`, `instanceof`, and the `in` operator with practical code examples.

---

## How to Compile and Verify

To verify compilation using TypeScript:

```bash
# Verify compilation in strict mode without emitting files
npx tsc --noEmit --strict solutions.ts
```

