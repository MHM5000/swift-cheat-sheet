# Control Flow

```js
// for loop (array)
let myArray = [1, 1, 2, 3, 5]
for value in myArray {
    if value == 1 {
        println("One!")
    } else {
        println("Not one!")
    }
}

// for loop (dictionary)
var dict = [
    "name": "Steve Jobs",
    "title": "CEO",
    "company": "Apple"
]
for (key, value) in dict {
    println("\(key): \(value)")
}

// for loop (range)
for i in -1...1 { // [-1, 0, 1]
    println(i)
}
// use .. to exclude the last number

// for loop (ignoring the current value of the range on each iteration of the loop)
for _ in 1...3 {
    // Do something three times.
}

// while loop
var i = 1
while i < 1000 {
    i *= 2
}

// do-while loop
do {
    println("hello")
} while 1 == 2

// Switch
let vegetable = "red pepper"
switch vegetable {
case "celery":
    let vegetableComment = "Add some raisins and make ants on a log."
case "cucumber", "watercress":
    let vegetableComment = "That would make a good tea sandwich."
case let x where x.hasSuffix("pepper"):
    let vegetableComment = "Is it a spicy \(x)?"
default: // required (in order to cover all possible input)
    let vegetableComment = "Everything tastes good in soup."
}

// Switch to validate plist content
let city:Dictionary<String, AnyObject> = [
    "name" : "Qingdao",
    "population" : 2_721_000,
    "abbr" : "QD"
]
switch (city["name"], city["population"], city["abbr"]) {
    case (.Some(let cityName as NSString),
        .Some(let pop as NSNumber),
        .Some(let abbr as NSString))
    where abbr.length == 2:
        println("City Name: \(cityName) | Abbr.:\(abbr) Population: \(pop)")
    default:
        println("Not a valid city")
}
```
