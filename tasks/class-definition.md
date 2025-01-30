```js
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  getArea() {
    return this.width * this.height;
  }

  getPerimeter() {
    return 2 * (this.width + this.height);
  }

  isSquare() {
    return this.width === this.height;
  }
}

// Example usage:

const rectangle1 = new Rectangle(5, 10);
console.log("Rectangle 1 Area:", rectangle1.getArea()); // Output: 50
console.log("Rectangle 1 Perimeter:", rectangle1.getPerimeter()); // Output: 30
console.log("Rectangle 1 is square:", rectangle1.isSquare()); // Output: false

const rectangle2 = new Rectangle(7, 7);
console.log("Rectangle 2 Area:", rectangle2.getArea()); // Output: 49
console.log("Rectangle 2 Perimeter:", rectangle2.getPerimeter()); // Output: 28
console.log("Rectangle 2 is square:", rectangle2.isSquare()); // Output: true
```
