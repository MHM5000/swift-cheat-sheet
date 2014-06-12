# Extensions

Add extra functionality to an already created type

``` js
// adds the methods first and rest to the array type
extension Array {
    func first () -> Any? {
        return self[0]
    }
    func rest () -> Array {
        if self.count >= 1 {
            return Array(self[1..self.endIndex])
        } else {
            return []
        }
    }
}
```
