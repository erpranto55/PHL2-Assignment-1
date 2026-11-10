# Differences Between Type Aliases and Interfaces in TypeScript

TypeScript provides us two primary ways to define custom data shapes: type aliases and interfaces. Both can describe object structures. Architectural differences helps us to choose which one we should use.

An interface defines the structure of an object and supports declaration merging. When multiple interface declarations share the same identifier then TypeScript automatically merges them.

```typescript
interface User {
  name: string;
}
interface User {
  age: number;
}
```

On the other hand, type aliases do not support declaration merging. If we want to redeclare a type alias in the same scope it produces an immediate compile time error. But type aliases provide a huge capabilities across the type system. They can define primitive aliases, union types, intersection types, and fixed-length tuples directly.

```typescript
type Status = "active" | "inactive";
type Coordinate = [number, number];
```

Inheritance may also differ between this two constructs. Interfaces can extend other shapes using the `extends` keyword, which allows the compiler to extend the layouts efficiently. But, type aliases achieve composition through intersection operators (`&`).

We should choose an interface when designing object-oriented models, class contracts, or public libraries. But we will choose a type alias when modeling union types, function signatures, primitive wrappers, or complex mapped types.
