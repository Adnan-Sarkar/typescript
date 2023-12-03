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

## Access Modifiers in Class

There are few access modifiers for a property such as: `public`, `private`, `protected` and `readonly`. These access modifiers give us a restriction between accessing properties of a class.

- **public**
  The public access modifier is used implicitly by default. We can access that public property any time directly.

  ```ts
  class Student  {
    public name: string;
    ...
    ...
  }

  const student1: Student = new Student(...);

  // we can access public property name directly
  console.log(student1.name);
  ```

- **private**

  The private access modifier is opposite of the public, it can not give us to access private property dirrectly. So, we can't access private property outside of the class.

  ```ts
  class Student  {
    private name: string;
    ...
    ...
  }

  const student1: Student = new Student(...);

  // we can't access private property name directly
  console.log(student1.name); // error
  ```

- **protected**
  This access modifier almost similat to the private, but the difference is we can get all the protected property in the child class that we can't get the private properties.

  ```ts
  class Person  {
    protected name: string;
    ...
    ...
  }

  class Student extends Person  {
    ...
    ...
  }



  const student1: Student = new Student(...);

  // we can access protected property name from the child class
  console.log(student1.name);
  ```

- **readonly**
  The readonle access modifier gives us the limitation that we can only read the property's value and can not update the value.

  ```ts
  class Student  {
   readonly name: string;
   ...
   ...
  }

  const student1: Student = new Student(...);

  // we can access readonly property name
  console.log(student1.name);

  // but can't update the value
  student1.name = "..."; // error
  ```

Access modifiers are useful in different scenario.

## Type Guard

Sometimes we might get unexpected output for multiple types operation. For example.

```ts
type NumberOrString = number | string;

const add = (a: NumberOrString, b: NumberOrString): NumberOrString => {
  return a + b;
};
```

In this function, we can give number and string arguments for the parameters `a` and `b`, but it will causes unexpected output.

Now, we can use `typeof` operator to ensure the type and the operation, this is actually type guard. We guard the type for unexpected operations.

- **Type guard using typeof**

  ```ts
  type NumberOrString = number | string;

  const add = (a: NumberOrString, b: NumberOrString): NumberOrString => {
    if (typeof a === "number" && typeof b === "number") {
      return a + b;
    } else {
      return a.toString() + b.toString();
    }
  };
  ```

  After using typeof we sure that there is 2 possible way to get the output by `addition` or `concatenation`.
