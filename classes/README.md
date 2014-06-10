# Classes

All methods and properties of a class are public. If you just need to store data
in a structured object, you should use a `struct`

```js
// A parent class of Square
class Shape {
  init() {
  }

  func getArea() -> Int {
    return 0;
  }
}

// A simple class `Square` extends `Shape`
class Square: Shape {
  var sideLength: Int

  // Custom getter and setter property
  var perimeter: Int {
    get {
      return 4 * sideLength
    }
    set {
      sideLength = newValue / 4
    }
  }

  init(sideLength: Int) {
    self.sideLength = sideLength
    super.init()
  }

  func shrink() {
    if sideLength > 0 {
      --sideLength
    }
  }

  override func getArea() -> Int {
    return sideLength * sideLength
  }
}
var mySquare = Square(sideLength: 5)
print(mySquare.getArea()) // 25
mySquare.shrink()
print(mySquare.sideLength) // 4

// Access the Square class object,
// equivalent to [Square class] in Objective-C.
Square.self

// If you don't need a custom getter and setter, but still want to run code
// before an after getting or setting a property, you can use `willSet` and `didSet`
```
