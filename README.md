# 100 Days of `SwiftUI`

Attempting `#100DaysOfSwiftUI` by following Paul Hudson's ([@twostraws](https://twitter.com/twostraws)) [guide](https://www.hackingwithswift.com/100/swiftui/)

<img src="https://img.icons8.com/color/452/swiftui.png" alt="drawing" width="400"/>

[***Test Yourself***](https://www.hackingwithswift.com/review#start)

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

### [Day 3](https://www.hackingwithswift.com/100/swiftui/3) : Operators and Conditions

> Remember, Swift is a type-safe language, which means it won’t let you mix types. For example, you
> can’t add an integer to a string because it doesn’t make any sense.


```python
if firstCard + secondCard == 2 {
    print("Aces – lucky!")
} else if firstCard + secondCard == 21 {
    print("Blackjack!")
} else {
    print("Regular cards")
}
```

**Combining conditions**

```python
let age1 = 12
let age2 = 21

if age1 > 18 && age2 > 18 {
    print("Both are over 18")
}
```

> That print() call will only happen if both ages are over 18, which they aren’t. In fact, Swift
> won’t even bother checking the value of age2 because it can see that age1 already failed the test.

> The alternative to && is ||, which evaluates as true if either item passes the test. For example we
> could print a message if either age is over 18:

```python
if age1 > 18 || age2 > 18 {
    print("At least one is over 18")
}
```

**The ternary operator**

> Swift has a rarely used operator called the ternary operator. It works with three values at once,
> which is where its name comes from: it checks a condition specified in the first value, and if
> it’s true returns the second value, but if it’s false returns the third value.

> The ternary operator is a condition plus true or false blocks all in one, split up by a question
> mark and a colon, all of which which makes it rather hard to read. Here’s an example:

```python
let firstCard = 11
let secondCard = 10
print(firstCard == secondCard ? "Cards are the same" : "Cards are different")
```

> That checks whether the two cards are the same, then prints “Cards are the same” if the condition
> is true, or “Cards are different” if it’s false. We could write the same code using a regular
> condition:

```python
if firstCard == secondCard {
    print("Cards are the same")
} else {
    print("Cards are different")
}
```

**Switch statements**

```python
let weather = "sunny"

switch weather {
case "rain":
    print("Bring an umbrella")
case "snow":
    print("Wrap up warm")
case "sunny":
    print("Wear sunscreen")
default:
    print("Enjoy your day!")
}
```
> Swift will only run the code inside each case. If you want execution to continue on to the next
> case, use the fallthrough keyword like this:

```python
switch weather {
case "rain":
    print("Bring an umbrella")
case "snow":
    print("Wrap up warm")
case "sunny":
    print("Wear sunscreen")
    fallthrough
default:
    print("Enjoy your day!")
}
```

**Summary**

1. Swift has operators for doing arithmetic and for comparison; they mostly work like you already
   know.
2. There are compound variants of arithmetic operators that modify their variables in place: +=, -=,
   and so on.
3. You can use if, else, and else if to run code based on the result of a condition.
4. Swift has a ternary operator that combines a check with true and false code blocks. Although you
   might see it in other code, I wouldn’t recommend using it yourself.
5. If you have multiple conditions using the same value, it’s often clearer to use switch instead.
6. You can make ranges using ..< >and ... depending on whether the last number should be excluded or
   included

### [Day 4](https://www.hackingwithswift.com/100/swiftui/4) : Loops

**For loops**

```python
let count = 1...10
for number in count {
    print("Number is \(number)")
}
let albums = ["Red", "1989", "Reputation"]

for album in albums {
    print("\(album) is on Apple Music")
}
```
> If you don’t use the constant that for loops give you, you should use an underscore instead so
> that Swift doesn’t create needless values:

```python
print("Players gonna ")

for _ in 1...5 {
    print("play")
}
```

**While loops**

```python
var number = 1

while number <= 20 {
    print(number)
    number += 1
}

print("Ready or not, here I come!")
```

**Repeat loops**

```python
var number = 1

repeat {
    print(number)
    number += 1
} while number <= 20

print("Ready or not, here I come!")
```

**Exiting loops**

Use `break` keyword

```python
while countDown >= 0 {
    print(countDown)

    if countDown == 4 {
        print("I'm bored. Let's go now!")
        break
    }

    countDown -= 1
}
```
**Exiting multiple loops**

```python
for i in 1...10 {
    for j in 1...10 {
        let product = i * j
        print ("\(i) * \(j) is \(product)")
    }
}
```
> If we wanted to exit part-way through we need to do two things. First, we give the outside loop a
> label, like this:

```python
outerLoop: for i in 1...10 {
    for j in 1...10 {
        let product = i * j
        print ("\(i) * \(j) is \(product)")

        if product == 50 {
            print("It's a bullseye!")
            break outerLoop
        }
    }
}
```
> With a regular break, only the inner loop would be exited – the outer loop would continue where it
> left off.

**Skipping items**

Use `coontinue` keyword

```python
for i in 1...10 {
    if i % 2 == 1 {
        continue
    }

    print(i)
}
```
**Summary**

1. Loops let us repeat code until a condition is false.
2. The most common loop is for, which assigns each item inside the loop to a temporary constant.
3. If you don’t need the temporary constant that for loops give you, use an underscore instead so
   Swift can skip that work.
4. There are while loops, which you provide with an explicit condition to check
5. Although they are similar to while loops, repeat loops always run the body of their loop at least
   once.
6. You can exit a single loop using break, but if you have nested loops you need to use break
   followed by whatever label you placed before your outer loop.
7. You can skip items in a loop using continue.
8. Infinite loops don’t end until you ask them to, and are made using while true. Make sure you have a
   condition somewhere to end your infinite loops!

