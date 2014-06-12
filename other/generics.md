# Generics

Generic code enables you to write flexible, reusable functions and types that can work with any type.

```js
// Generic function, which swaps two any values.
func swapTwoValues<T>(inout a: T, inout b: T) {
    let temporaryA = a
    a = b
    b = temporaryA
}
```

```js
// Generic collection type called `Stack`.
struct Stack<T> {
    var elements = T[]()

    mutating func push(element: T) {
        elements.append(element)
    }

    mutating func pop() -> T {
        return elements.removeLast()
    }
}
```

We can use certain type constraints on the types with generic functions and generic types.
Use `where` after the type name to specify a list of requirements.

```js
// Generic function, which checks that the sequence contains a specified value.
func containsValue<
    T where T: Sequence, T.GeneratorType.Element: Equatable>
    (sequence: T, valueToFind: T.GeneratorType.Element) -> Bool {

    for value in sequence {
        if value == valueToFind {
            return true
        }
    }

    return false
}
```

In the simple cases, you can omit `where` and simply write the protocol or class name after a colon. Writing `<T: Sequence>` is the same as writing `<T where T: Sequence>`.
