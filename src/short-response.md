# Section 2 — Short Response

Write your responses directly in this file. Follow markdown formatting guidelines. Check the rubric.md file to see how your short responses will be graded. 

As a quick guide, check the following before submitting:
- [] Answered all parts of every question
- [] No typos or grammar mistakes (use grammarly!)
- [] Accurately uses relevant technical terminology
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Responses are concise and easy to comprehend

---

## Question 1

In your own words, explain what does _encapsulation_ refer to? Why is this concept beneficial when programming? 

Provide a code snippet to illustrate _encapsulation_.

## Response 2
***Encapsulation*** refers to packing data into a ***class***. Then, controlling the access to that component. It's when the objects we create provide an interface to other code that wants to use them, while maintaining their own internal state.

It's when we keep an object's internal state private and making a clear division between its **public** interface and its **private** internal state, is called encapsulation.

---

## Question 2

Explain what the `this` keyword is. Why is the `this` keyword useful?

In the code snippet below, what does `this` refer to?

```js
class Counter {
	constructor() {
		this.count = 0;
	}
  increment() {
    this.count++;
  }
}

const counterA = new Counter();
const counterB = new Counter();

counterA.increment();
counterA.increment();
counterA.increment();

counterB.increment();

console.log(counterA.count);
console.log(counterB.count);
```

## Response 2

The `this` keyword, usually declared in the constructor and used in methods, refers to the context, or how and where in the function the code is supposed to be run. 

It is mostly used in object methods, where `this` refers to the object that the method is attached to, allowing the same method to be reused on different objects. It depends on how we invoke the function will be the outcome of the `this` keyword. Ex. `this.hand` points to the object method.

In the case of the code snippet, `this` is a reference to the **global** object `count` and set `count = 0`. To start at 0 as an initializer. Count can be used in different forms depending on how it's invoked.

---

## Question 3

In your own words, explain what **polymorphism** means in OOP. Provide an example in code that demonstrates polymorphism.

## Response 3
**Polymorphism** is when code can be used for many types of objects. Each class has its ***own data***. It's when that class with it's own function is called, behaves properly for any object. Usually with polymorphism, it usually uses inheritance first, inheriting properties from a parent class to a subclass. 

We can **override** methods using the same method & properties for subclasses of the same superclass. It's used if you want to perform the same thing on a bunch of different objects. Or if you want a method to be overridden in each subclass to provide something unique to each class.

Here is an example of Polymorphism:
```

class Cat {
  constructor(name, age, isFed) {
this.name = name;
this.age = age;
this.isFed = true;
  }
  feedAnimal() {
    if (isFed === true)
    return `"Are the pets fed? Say true if they have been fed. ${this.isFed}."`
  }
}

class Dog extends Cat {
  constructor(name, age, breed, isFed)
  this.breed = breed;
}

helpPets() {
  return `"Arrange the dogs by their ${this.name}, ${this.age}, ${this.breed}, ${this.isFed} and then let them interact with the cats."`
}

const cat1 = new cat("Jerry", 16, true);
const dog1 = new dog("Lola", 17, "Golden Retreiver" true);
console.log(cat.feedAnimal());
console.log(dog.helpPets());

```

We can use the same method in different classes and invoke it depending on what we want our code to do.

---

## Question 4

You're building a game where players can raise different digital pets: Cats, Dogs, and Birds. All pets have have a `name`, `energy` level, and `happiness` level and can all `sleep`. Cats have the ability to `hunt`, dogs have the ability to `chase`, and birds have the ability to `fly`.

**Part A:** Describe in words how you would use inheritance to organize these classes.

**Part B:** Explain one advantage of using inheritance here instead of creating three completely separate classes.

## Response 4
What I would do is:

Create classes for all 3 animals that share the shared properties of all 3 animals: `dogs`, `cats`, `birds`. They all can have a `name`, `energy level`, `happiness level`, and can all `sleep`. 

I would have that in the **constructor** of the 1st class and ***inherit*** those properties to all the subclasses of the other classes that need those properties. Then I will add specifically to any animal that needs a specific property using the `super()` keyword to add it. In this case, all the animals need to have their own ***methods*** to perform their **unique** abilities. Then, at the end, when I ***invoke*** the function, I can just call on the animal I want with their specific ability to have them perform a certain task. I can also reuse that ability for another animal if I really wanted to.