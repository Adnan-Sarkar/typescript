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

## Inheritance in Typescript

`Inheritance` is a very useful methodology for reuse classes. For example,

```ts
class Person {
  name: string;
  age: number;

  ...
}
```

We have a `Person` class, let's create more classes.

```ts
// student class
class Student {
  name: string;
  age: number;

  ...
}

// teacher class
class Teacher {
  name: string;
  age: number;

  ...
}
```

These two `Student` and `Teacher` classes and they have common properties such as `name` and `age`. Inheritance give us this feature for reuse common properties from one class to another class.

Now, we can inherit all the properties from one class to another class, this means there is a relation between that two classes. The class get all properties is called `child class` and the class which is gives it's own properties is called `parent class`.

For using inheritance we have to use `extends` keyword.

```ts
class Student extends Person {
  ...
}
```

Now, we don't need to create `name` and `age` properties again, because student class is inherit all the properties and methods from the parent class person.

There is an important thing is, if parent class constructor initialize it's own properties then we have to ensure all that properties have to pass from the child class constructor using `super` keyword.

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

```ts
class Student extends Person {
  constructor(name: string, age: number) {
    super(name, age);
  }
}
```

`super` is a method that actually invoked the parent class constructor for initialize inherited properties.

If parent class constructor does not initialize any properties, then we don't need to call the `super` from the child class constructor.
