# OOP In Typescript

Typescript supports 4 principles of Object Oriented Programming.

## Class and Object

Class is like a blueprint of some shape (Object).

```ts
class Person {
  ...
}
```

At first we have to use `class` keyword to create a class in typescript, and the class name should be `capitalize`.

```ts
class Person {
  name: string;
  age: number;
}
```

Then we have to declare the properties and their types inside the class.

Now, we actually create an object from class, so we need to construct a class so that we can easily assign the values of the properties. `Constructor` did this work for the initialization of the properties.

```ts
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}
```

Let's create an object from the class.

```ts
const person: Person = new Person("...", 50);
```

SO, we create an object from a class using the keyword `new`. and we call the class name like a function. This is actually invoking the class constructor.
