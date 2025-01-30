```js
// Class Definitions (ES6)

// Basic class definition
class Person {
  constructor(name, age) { // The constructor is called when a new object is created
    this.name = name;
    this.age = age;
  }

  greet() { // Method definition
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }

  getBirthYear() {
    const currentYear = new Date().getFullYear();
    return currentYear - this.age;
  }
}

// Creating an instance (object) of the class
const person1 = new Person("Alice", 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
console.log(person1.getBirthYear()); // Output: current year - 30

const person2 = new Person("Bob", 25);
person2.greet(); // Output: Hello, my name is Bob and I am 25 years old.
console.log(person2.getBirthYear()); // Output: current year - 25

// Class with methods and properties
class Car {
    constructor(make, model, year) {
        this.make = make;
        this.model = model;
        this.year = year;
        this.speed = 0; // Instance property initialized in the constructor
    }

    accelerate(increment) {
        this.speed += increment;
    }

    brake(decrement) {
        this.speed -= decrement;
        if (this.speed < 0) {
            this.speed = 0;
        }
    }

    getCurrentSpeed() {
        return this.speed;
    }
}

const myCar = new Car("Toyota", "Camry", 2020);
myCar.accelerate(50);
console.log(myCar.getCurrentSpeed()); // Output: 50
myCar.brake(25);
console.log(myCar.getCurrentSpeed()); // Output: 25
myCar.brake(30);
console.log(myCar.getCurrentSpeed()); // Output: 0

// Class Inheritance (extends keyword)
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(`${this.name} makes a generic sound.`);
    }
}

class Dog extends Animal {
    constructor(name, breed) {
        super(name); // Call the parent class constructor
        this.breed = breed;
    }

    speak() { // Overriding the parent class method
        console.log(`${this.name} barks!`);
    }

    bark() {
        console.log("Woof!");
    }
}

const myDog = new Dog("Buddy", "Golden Retriever");
myDog.speak(); // Output: Buddy barks!
myDog.bark(); // Output: Woof!

const myAnimal = new Animal("Generic animal");
myAnimal.speak(); // Output: Generic animal makes a generic sound.

// Getters and Setters
class Circle {
    constructor(radius) {
        this._radius = radius; // Use an underscore to indicate a "private" property (convention only)
    }

    get radius() { // Getter method
        return this._radius;
    }

    set radius(value) { // Setter method
        if (value < 0) {
            throw new Error("Radius cannot be negative.");
        }
        this._radius = value;
    }

    get area() {
        return Math.PI * this._radius * this._radius;
    }
}

const myCircle = new Circle(5);
console.log(myCircle.radius); // Output: 5 (using the getter)
myCircle.radius = 10; // Using the setter
console.log(myCircle.radius); // Output: 10
console.log(myCircle.area); // Output: 314.159... (using the getter)

// Static methods
class MathUtils {
    static add(a, b) {
        return a + b;
    }
}

console.log(MathUtils.add(5, 3)); // Output: 8 (calling a static method directly on the class)
```
