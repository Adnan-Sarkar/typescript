## Table of Contents

- [Interface](#interface)

<br>

# Interface

Interface is similar to the type aliasing, but to create a shape for an object interface is the best choice. So, In typescript, an interface is a way to define a contract for the shape or structure of an object.

For create an interface,

```ts
interface User {
  name: string;
  age: number;
}

const user1 : User = {
  name: "...",
  age: ...
}
```

There are few difference between `interface` and `type aliase`.

Using type aliasing we can aliase primitive types such as `string`, `number` etc, but we can't using interface.

```ts
type Str = string;
// can't do this using interface
```

Merge two interfaces possible if both are same name.

```ts
interface User {
  name: string;
}

interface User {
  age: number;
}

const user1 : User = {
  name: "...",
  age: ...
}
```

Interface provides better error messages than type aliasing.

Interface is not mutable. So they can't be used to create new types through `union` or `intersection` type, but type aliase can allow these.

```ts
type Name = {
  name: string;
};

type User = Name & { age: number }; // using intersection
```

But we can `extends` one to another interface, also possible to extends type aliase too.

```ts
interface Name {
  name: string;
}

interface User extends Name {
  age: number;
}
```

```ts
type Name = {
  name: string;
};

interface User extends Name {
  age: number;
}
```

Interface is usefull while use `Class` or `object`.
