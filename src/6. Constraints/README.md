## Table of Contents

- [Constraints in Typescript](#constraints-in-typescript)

<br>

# Constraints in Typescript

Basically constraints is used with generics. Before understand the constraints let's see an example.

```ts
<{ name: string; age: number; }>
```

In this case assume we pass an object type as a generic, So we must ensure that our object should same as our provided generic type object. If we try to add an extra property to the object then typescript will give us error.

So, sometimes we might need to ensure minimum requirement of object with allow extra properties, then `constraints` help us.

```ts
<T extends { name: string; age: number; } >
```

Using extends keyword we ensure the generic type object should have that minimum properties. Now we can add extra properties.

There is another keyword commonly used with constraint is `keyof`.

```ts
type Person = {
  name: string;
  age: number;
};

// without using keyof
type PersonKeys1 = "name" | "age";

// with using keyof
type PersonKeys2 = keyof Person;
```

`keyof` is basically give us all the key name of any object with union operator.

Let's see an example,

```ts
const getPropertyValue = (obj: object, key: string) => {
  return obj[key];
};
```

If we provide the wrong key name then our function will return `undefined`. Using constraint and keyof we can fix that issue.

```ts
const getPropertyValue = <T, Y extends keyof T>(obj: T, key: Y) => {
  return obj[key];
};
```

Now, generic `Y` is key of object `T`. So, if we provide wrong key name then it won't allow me because of typescript.

`Y` is string literal type, so we must ensure that our provided value is present in `Y`.

```ts
type Languages = "Javascript" | "Python" | "Java";

const skillLanguage: Languages = "C"; // error
const skillLanguage: Languages = "java"; // error
const skillLanguage: Languages = "Java"; // OK
```

`Y` is working like these string literals.
