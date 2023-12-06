## Table of Contents

- [Generics](#generics)

<br>

# Generics

`Generics` in typescript allow you to create `reusable` and `type-safe` components and functions that can work with different data types without sacrificing type information.

```ts
type NumberArray = number[];
type StringArray = string[];
```

These two types is an array of a specific type, the common part is array and the element data type is different. For different data type we have to create similar code and here is `generics` came.

If we use generic, then we don't have to create multiple code for different types.

```ts
type GeneralArray<T> = Array<T>;
```

`<T>` is for define type and the entire structure is common for all.

```ts
const nummArr: GeneralArray<number> = [1, 2, 3];
const strArr: GeneralArray<string> = ["...", "..."];
```

Type `tuple` can be shaped as a generic.

```ts
type GenericTuple1<X, Y> = [X, Y];
type GenericTuple2<X, Y, Z> = [X, Y, Z];

const hobbies: GenericTuple1<string, string> = ["Playing", "Travelling"];
```

Generics can be used in `interface`.

```ts
interface Person<T, X> {
  name: string;
  age: number;
  address: T;
  education: X;
}
```

Generics can be used in `function`.

```ts
const functionaName = <T>(parameter: T): T[] => {
  ...
  ...
  return [parameter]
}
```

generic function used frequently, because we can create a function as a reuseable component for any types.

`Generics` is very important in typescript, first time it takes times to understand how to use and where to use.
