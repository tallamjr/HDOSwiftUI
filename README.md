# 100 Days of `SwiftUI`

Attempting `#100DaysOfSwiftUI` by following Paul Hudson's ([@twostraws](https://twitter.com/twostraws)) [guide](https://www.hackingwithswift.com/100/swiftui/)

<img src="https://img.icons8.com/color/452/swiftui.png" alt="drawing" width="400"/>

### [Day 1](https://www.hackingwithswift.com/100/swiftui/1) : Simple Data Types

**Strings and Integers**

```bash
 15> var age = 38
age: Int = 38
 16> var population = 8_000_000
population: Int = 8000000

```

**Doubles and Booleans**

```bash
 17> var pi = 3.141
pi: Double = 3.141
 18> var awesome = true
awesome: Bool = true
```

**String Interpolation**

```bash
  1> var score = 85
score: Int = 85
  2> var str = "Your score was \(score)"
str: String = "Your score was 85"
  3> var results = "The test results are here: \(str)"
results: String = "The test results are here: Your score was 85"
```

**Constants**

> When you write your own Swift code, you should always use let unless you specifically want to
> change a value. In fact, Xcode will warn you if you use var then don’t change the variable.

```bash
 19> let taylor = "swift"
taylor: String = "swift"
```

**Type Annotations**

```bash
 20> let album: String = "Reputation"
 21. let year: Int = 1989
 22. let height: Double = 1.78
 23. let taylorRocks: Bool = true
album: String = "Reputation"
year: Int = 1989
height: Double = 1.78
taylorRocks: Bool = true
```

**Summary**

> 1. You make variables using var and constants using let. It’s preferable to use constants as often
>    as possible.
> 2. Strings start and end with double quotes, but if you want them to run across multiple lines you
>    should use three sets of double quotes.
> 3. Integers hold whole numbers, doubles hold fractional numbers, and booleans hold true or false.
> 4. String interpolation allows you to create strings from other variables and constants, placing
>    their values inside your string.
> 5. Swift uses type inference to assign each variable or constant a type, but you can provide
>    explicit types if you want.

### [Day 2](https://www.hackingwithswift.com/100/swiftui/2) : Complex Data Types

**Arrays**

```bash
 25> let john = "John Lennon"
 26. let paul = "Paul McCartney"
 27. let george = "George Harrison"
 28. let ringo = "Ringo Starr"
 30. let beatles = [john, paul, george, ringo]
john: String = "John Lennon"
paul: String = "Paul McCartney"
george: String = "George Harrison"
ringo: String = "Ringo Starr"
beatles: [String] = 4 values {
  [0] = "John Lennon"
  [1] = "Paul McCartney"
  [2] = "George Harrison"
  [3] = "Ringo Starr"
}

```

```bash
 31> beatles[1]
$R1: String = "Paul McCartney"

```

> Note: If you’re using type annotations, arrays are written in brackets: [String], [Int], [Double],
> and [Bool].

**Sets**

> Sets are collections of values just like arrays, except they have two differences:
> 1. Items aren’t stored in any order; they are stored in what is effectively a random order.
> 2. No item can appear twice in a set; all items must be unique.

```bash
 32> let colors = Set(["red", "green", "blue"])
colors: Set<String> = 3 values {
  [0] = "green"
  [1] = "red"
  [2] = "blue"
}
 33> let colors2 = Set(["red", "green", "blue", "red", "blue"])
colors2: Set<String> = 3 values {
  [0] = "blue"
  [1] = "red"
  [2] = "green"
}

```

**Tuples**

> Tuples allow you to store several values together in a single value. That might sound like arrays,
> but tuples are different:
> 1. You can’t add or remove items from a tuple; they are fixed in size.
> 2. You can’t change the type of items in a tuple; they always have the same types they were
>    created with.
> 3. You can access items in a tuple using numerical positions or by naming them, but Swift won’t
>    let you read numbers or names that don’t exist.

```bash
 34> var name = (first: "Taylor", last: "Swift")
name: (first: String, last: String) = {
  first = "Taylor"
  last = "Swift"
}
 35> name.0
$R2: String = "Taylor"
 36> name.first
$R3: String = "Taylor"

```
> Remember, you can change the values inside a tuple after you create it, but not the types of
> values. So, if you tried to change name to be (first: "Justin", age: 25) you would get an error.

**Arrays vs Tuples vs Sets**

> If you need a specific, fixed collection of related values where each item has a precise position
> or name, you should use a tuple:

```bash
 37> let address = (house: 555, street: "Taylor Swift Avenue", city: "Nashville")
address: (house: Int, street: String, city: String) = {
  house = 555
  street = "Taylor Swift Avenue"
  city = "Nashville"
}
```
> If you need a collection of values that must be unique or you need to be able to check whether a
> specific item is in there extremely quickly, you should use a set:

```bash
 38> let set = Set(["aardvark", "astronaut", "azalea"])
set: Set<String> = 3 values {
  [0] = "astronaut"
  [1] = "azalea"
  [2] = "aardvark"
}
```
> If you need a collection of values that can contain duplicates, or the order of your items
> matters, you should use an array:

```bash
 39> let pythons = ["Eric", "Graham", "John", "Michael", "Terry", "Terry"]
pythons: [String] = 6 values {
  [0] = "Eric"
  [1] = "Graham"
  [2] = "John"
  [3] = "Michael"
  [4] = "Terry"
  [5] = "Terry"
}

```

**Dictionaries**

```bash
 40> let heights = [
 41.     "Taylor Swift": 1.78,
    "Ed Sheeran": 1.73
 41.     "Taylor Swift": 1.78,
 42.     "Ed Sheeran": 1.73
 42.     "Ed Sheeran": 1.73
 43. ]
heights: [String : Double] = 2 key/value pairs {
  [0] = {
    key = "Taylor Swift"
    value = 1.78
  }
  [1] = {
    key = "Ed Sheeran"
    value = 1.73
  }
}

```

**Dictionary Defaults**

```bash
 44> let favoriteIceCream = [
 45.    "Paul": "Chocolate",
    "Sophie": "Vanilla"
 45.     "Paul": "Chocolate",
 46.     "Sophie": "Vanilla"
 46.     "Sophie": "Vanilla"
 47. ]
favoriteIceCream: [String : String] = 2 key/value pairs {
  [0] = {
    key = "Sophie"
    value = "Vanilla"
  }
  [1] = {
    key = "Paul"
    value = "Chocolate"
  }
}
 48> favoriteIceCream["Charlotte", default: "Unknown"]
$R4: String = "Unknown"

```

**Collections**

```python
var teams = [String: String]()
teams["Paul"] = "Red"
```
```python
var results = [Int]()
var words = Set<String>()
var numbers = Set<Int>()
var scores = Dictionary<String, Int>()
var results = Array<Int>()
```

**Enumerations**

```python
enum Result {
    case success
    case failure
}
let result4 = Result.failure
```

```python
enum Activity {
    case bored
    case running(destination: String)
    case talking(topic: String)
    case singing(volume: Int)
}
let talking = Activity.talking(topic: "football")
```

```python
enum Planet: Int {
    case mercury
    case venus
    case earth
    case mars
}
let earth = Planet(rawValue: 2)
```

```python
enum Planet: Int {
    case mercury = 1
    case venus
    case earth
    case mars
}
```

**Summary**

> 1. Arrays, sets, tuples, and dictionaries let you store a group of items under a single value.
>    They each do this in different ways, so which you use depends on the behavior you want.
> 2. Arrays store items in the order you add them, and you access them using numerical positions.
> 3. Sets store items without any order, so you can’t access them using numerical positions.
> 4. Tuples are fixed in size, and you can attach names to each of their items. You can read items
>    using numerical positions or using your names.
> 5. Dictionaries store items according to a key, and you can read items using those keys.
> 6. Enums are a way of grouping related values so you can use them without spelling mistakes.
> 7. You can attach raw values to enums so they can be created from integers or strings, or you can
>    add associated values to store additional information about each case.
