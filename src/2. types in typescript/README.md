## Types in Typescript

In TypeScript, it's a good practice to assign a type to each variable by adding a colon after the variable name and specifying the type, enhancing code clarity and type safety.

```ts
let variableName: typeName;
```

> Once you assign a type to a variable in TypeScript, that variable can only store values of the specified type, ensuring strict type enforcement.

### Basic Data Types

Typescript has all javascript types with his own types.

```ts
// number
let num: number = 12;
```

```ts
// string
let str: string = "Adnan";
```

```ts
// boolean
let bol: boolean = true;
```

```ts
// undefined
let x: undefined = undefined;
```

```ts
// null
let y: null = null;
```

### Typescript Own Data Types

- **any**
  `any` is not a specific type, it's for any valid type. So, any type is allow you to store number, string.... etc type value, which is javascript's behavior. It's recomanded to not use `any` type in typescript.

  ```ts
  // any
  let value: any;
  value = "typescript";
  value = 5;
  value = true;
  value = null;
  ```

- **void**
  `void` type is used for as a function return value type, which means that function doesn't return anything.

- **unknown**
  `unknown` type is similar to `any` but enforces type checking before you can use a value in a specific way using `typeof` operator.

- **never**
  If a function throw an error then the function's return type is `never`, because the function is throw an error instead of returning a value.

- **union**
  `union` is very common type used in typescript to create our own types. Such as you need a type which accepts number or string then the unior type is suitable for create these type.

  ```ts
  // union
  let value: number | string; // | is used for union
  value = "Adnan";
  value = 12;
  ```

  union type simply check is the provided value is number or string. But it is little bit different for object type union. For two different object union means the value of object have to either first object type or another or both.

  ```ts
  // union
  let value: { name: string } | { age: number }; // | is used for union
  value = { name: "Adnan" }; // okk
  value = { age: 55 }; // okk
  value = { name: "Adnan", age: 55 }; // okk
  value = { name: "Adnan", email: "demo@gmail.com" }; //  wrong, email is not a valid property in two union objects
  ```

- **intersection**
  `intersection` is oposit of union type, where union accept both or individual intersection allows you to combine multiple types into a single type that includes all the properties and methods of each type.

  ```ts
  // intersection
  let value: { name: string } & { age: number }; // & is used for union
  value = { name: "Adnan" }; // wrong, age is missing
  value = { name: "Adnan", age: 55 }; // okk
  ```

  > :warning: `number & string` is not possible, because any value can't be string and number at the same time

### Non-Primitive Data Types

Type script has few `non-primitive` types

- Object
- Array
- Tuple

In JS array, function they all are end of the day objects, but in typescript array has it's own type. To write these type:

- **object**

  ```ts
  // object
  let obj1: object = {};
  let obj2: {} = {};
  ```

  {} is for any type of object, but you can specify the properties and their types.

  ```ts
  // object
  let obj: { name: string };
  obj = { name: "Adnan" };
  ```

- **array**

  ```ts
  // array
  let arr1: number[] = [1, 2, 3];
  let arr2: string[] = ["a", "b", "c"];
  ```

- tuple

  ```ts
  // tuple
  let arr1: [number, string, boolean] = [1, "a", true];
  let arr2: [string, string] = ["a", "b"];
  ```

  Tuple is similar to an array but with fixed number of elements of different data types. So, If you want to an array with 2 size only and want to specify first element will be number and second element will be string then tuple is perfect choice. Because, it won't allow you to put first element of any data type except number same as second elemnt of any data type except string.<br> <br>

  `[number, string, boolean]` this is a tuple and it has fixed 3 size with specific element type, If you try to insert value like `[123, 15, true]` typescript won't allow you to do that because of second element is number instead of string. Same as size, you can't put 4th element of it.

### Type inference

Type inference is a feature in TypeScript that allows the compiler to automatically determine the type of a variable or expression based on its usage and assignment

```ts
let a = "type inference"; // TypeScript infers the type as string
let b = 5; // TypeScript infers the type as number
```

It can also determines:

- `Function Return Types`,
- `Object Literal Types`,
- `Array Types`,
- `Union and Intersection Types` and more
