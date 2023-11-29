# Utility Types In Typescript

## 1. Pick type

```ts
type Person = {
  name: string;
  age: number;
  email?;
  string;
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
