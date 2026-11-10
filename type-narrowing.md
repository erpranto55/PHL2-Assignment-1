# Understanding Type Narrowing in TypeScript

Type narrowing is a core TypeScript that refines broad types into more specific types. It works within conditional execution paths. When we are working with union types, values can hold multiple possibilities.

The most common is the `typeof` operator. It inspects primitive types including string, number, and boolean at the time of execution. TypeScript can automatically narrows the variable within that scope. Also we can safely invoke primitive-specific methods without compilation errors.

```typescript
function printId(id: string | number): string {
  if (typeof id === "string") {
    return id.toUpperCase();
  }
  return id.toFixed(2);
}
```

Another one is the `instanceof` operator. It determines if a value is an instance of a specific class constructor or not. This check evaluates prototype chains. It is especially useful in the custom class instances or native objects like `Date`.

```typescript
function getTimestamp(input: Date | string): number {
  if (input instanceof Date) {
    return input.getTime();
  }
  return new Date(input).getTime();
}
```

Also `in` operator is another type. It checks that an expected property exists on a given object or not. By checking the unique property names, TypeScript narrows the object unions reliably.

```typescript
type Admin = { privileges: string[] };
type User = { email: string };

function inspectAccount(user: Admin | User): string {
  if ("privileges" in user) {
    return user.privileges.join(", ");
  }
  return user.email;
}
```

Type narrowing enables static types with the dynamic JavaScript execution. Guards like `typeof`, `instanceof`, and `in` disable the runtime mismatches. They helps the developers to write safer, predictable code.

