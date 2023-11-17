## Generics

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
