# Type Aliases

Type aliasing is a most useful tool which reduces redundant type declaration. This is uses for big custom type.

```ts
let person1: {
  id: number;
  name: string;
  email: string;
  address: string;
  contactNumber: string;
} = {
  id: 123,
  name: "...",
  email: "...",
  address: "...",
  contactNumber: "01.....",
};

let person2: {
  id: number;
  name: string;
  email: string;
  address: string;
  contactNumber: string;
} = {
  id: 456,
  name: "...",
  email: "...",
  address: "...",
  contactNumber: "01.....",
};
```

You see the big custom object type is repeated two times which also reduces code readability also break `DRY - Dont Repeat Yourself`.
Now, what if we declare type once with a name and use this name where the type is need? This is type aliasing.

```ts
type Person = {
  id: number;
  name: string;
  email: string;
  address: string;
  contactNumber: string;
};

let person1: Person = {
  id: 123,
  name: "...",
  email: "...",
  address: "...",
  contactNumber: "01.....",
};
```

Type aliasing make code more readable, centralizes the type declaration and reduce code redundancy.<br><br>
For type aliasing,

- use `type` keyword
- type alias should be `capitalize`.

We can alias any primitive type also but it's not recommanded.

```ts
type str = String;
type num = number;
```

Most of the time, type alias is used for custom types such as `union`, `intersection`, `tuple`, `custom object` etc.

```ts
// union
type StrOrNum = string | number;

// tuple
type CustomTuple = [number, string];
```
