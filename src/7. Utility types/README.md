# Utility Types In Typescript

## 1. Pick type

```ts
type Person = {
  name: string;
  age: number;
  email?: string;
};
```

Now, using `Pick` type we can pick any property of specified type.

```ts
type Name = Pick<Person, "name">;
// Name type is: { name: string; }
```

We can pick multiple properties using `Pick` utility type.

```ts
type NameAge = Pick<Person, "name" | "age">;
// NameAge type is: { name: string; age: number; }
```

## 2. Omit type

Opposite of pick type. We can omit few properties using this `Omit` utility type and rest of the properties will be the new type.

```ts
type Email = Omit<Person, "name" | "age">;
// Email type is: { email?: string; }
```

```ts
type NameAge = Omit<Person, "email">;
// NameAge type is: { name: string; age: number; }
```
