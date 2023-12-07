## Table of Contents

- [Utility Types In Typescript](#utility-types-in-typescript)
  - [1. Pick type](#1-pick-type)
  - [2. Omit type](#2-omit-type)
  - [3. Required type](#3-required-type)
  - [4. Partial type](#4-partial-type)
  - [5. Readonly type](#5-readonly-type)
  - [6. Record type](#6-record-type)

<br>

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

## 3. Required type

To pick all the properties of a type and make all the properties required.

```ts
type RequiredInfo = Required<Person>;
// RequiredInfo type is: { name: string; age: number; email: string; }
```

## 4. Partial type

Opposite of Required type, where it makes all properties optional.

```ts
type OptionalInfo = Partial<Person>;
// OptionalInfo type is: { name?: string; age?: number; email?: string; }
```

## 5. Readonly type

To makes all properties `readonly`, so we can't change those properties values which have readonly access modifier. So, we only can get the property value.

```ts
type ReadonlyInfo = Readonly<Person>;
// ReadonlyInfo type is: {
//   readonly name: string;
//   readonly age: number;
//   readonly email: string;
// }
```

## 6. Record type

`Record` is mostly used utility type. Wee can define any object's shape using this type.

```ts
type MyObj = Record<"string", "string">;
```

`<"string", "string">` First string is for `key` type of an object and the second string is for the `value`. So, we can define a type of an object where every keys are string type and every key's values are string type.
