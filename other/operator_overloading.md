# Operator Overloading

You can overwrite existing operators or define new operators for existing or custom types.

```js
// Overwrite existing types
@infix func + (a: Int, b: Int) -> Int {
    return a - b
}
var x = 5 + 4 // x is 1
```

You can't overwrite the = operator

Add operators for new types

```js
struct Vector2D {
    var x = 0.0, y = 0.0
}
@infix func + (left: Vector2D, right: Vector2D) -> Vector2D {
    return Vector2D(x: left.x + right.x, y: left.y + right.y)
}
```
Operators can be `prefix`, `infix`, or `postfix`.

You have to add `@assignment` if you wish to define compound assignment operators like +=, ++ or -=

```js
@assignment func += (inout left: Vector2D, right: Vector2D) {
    left = left + right
}
```

Operator overloading is limited to the following symbols: / = - + * % < > ! & | ^ . ~
