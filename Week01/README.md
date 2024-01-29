# Homework #1

## 100 Day of SwiftUI - Day 1,2

```swift
// var for variable
var age = 24
// let for constant & double quote for string
let name = "Alan Ren"

// quote mark in string
var school =  " NYU /"New York University/" "

// multiple lines string
var action = """
run
away
"""

// string properties & function
let nameLength = name.count
print(nameLength)
print(action.uppercase())
print(school.hasPrefix(" NYU"))
print(name.hasSuffix("Ren"))

// for number, Swift does not care about the underscore in the value
let reallyBig = 1_00__00___00____00 // Same as let reallyBig = 100000000

// number function isMultiple(of: )
print(reallyBig.isMultiple(of:10) // true

// Int & Double can't mix together unless type casting
let a = 1
let b = 2.0
let c = a + b //Error

let c = a + Int(b) // or let c = Double(a) + b

// And the same variable name must store the same datatype


// Boolean have toggle() function
var gameOver = false
gameOver.toggle() // true


// Two ways to join string together
// #1
let people = "Haters"
let action = "hate"
let lyric = people + " gonna " + action
print(lyric)

// #2 String interpolation!!!!!
let name = "Taylor"
let age = 26
let message = "Hello, my name is \(name) and I'm \(age) years old."
print(message)




```

[Summary](https://www.hackingwithswift.com/quick-start/beginners/summary-simple-data)

## Day 3

```swift
// Array
// Like other operation, only one datatype will one array hold
var beatles = ["John", "Paul", "George", "Ringo"]
let numbers = [4, 8, 15, 16, 23, 42]
var temperatures = [25.3, 28.2, 26.4]
// array.append() to add element

//empty array
var scores = Array<Int>()
var albums = [String]() // var albums = Array<String>()

//count
scores.count // return how many elements in the array

//removeAt & removeAll
beatles.remove(at: 2) //remove "George"
temperatures.removeAll()

// contains()
let bondMovies = ["Casino Royale", "Spectre", "No Time To Die"]
print(bondMovies.contains("Frozen"))

// sorted()
let cities = ["London", "Tokyo", "Rome", "Budapest"]
print(cities.sorted()) // return a new array in ascending order alphabetically.

// reversed()
let presidents = ["Bush", "Obama", "Trump", "Biden"]
let reversedPresidents = presidents.reversed()
print(reversedPresidents)


// Dictionary
let employee2 = [
    "name": "Taylor Swift",
    "job": "Singer",
    "location": "Nashville"
]
// Access
// Add Default value if the key does not exist
print(employee2["name", default: "Unknown"])
print(employee2["job", default: "Unknown"])
print(employee2["location", default: "Unknown"])



var heights = [String: Int]()
heights["Yao Ming"] = 229
heights["Shaquille O'Neal"] = 216
heights["LeBron James"] = 206


// Set
let people = Set(["Denzel Washington", "Tom Cruise", "Nicolas Cage", "Samuel L Jackson"]) // Create array first, then put it into an array
// instead of append(), use insert() for set
var people = Set<String>()
people.insert("Denzel Washington")
people.insert("Tom Cruise")
people.insert("Nicolas Cage")
people.insert("Samuel L Jackson")
// !!! Set will not save duplicate data !!!


// enumeration/enum
// enum let us define a new data type with a handful of specific values that it can have.
enum Weekday {
    case monday
    case tuesday
    case wednesday
    case thursday
    case friday
}

var day = Weekday.monday
day = Weekday.tuesday
day = Weekday.friday

// Simpler version
enum Weekday {
    case monday, tuesday, wednesday, thursday, friday
}
var day = Weekday.monday
day = .tuesday
day = .friday
```

## Day 4

```swift
// type annotations

// type inference
let surname: String = "Lasso"
var score: Int = 0

// type annotation for array
let beatles: [String] = ["John", "Paul", "George", "Ringo"]
let numbers: [Int] = [4, 8, 15, 16, 23, 42]
let temperatures: [Double] = [25.3, 28.2, 26.4]

// type annotation for dictionary
let employee2: [String: String] = [
    "name": "Taylor Swift",
    "job": "Singer",
    "location": "Nashville"
]

// type annotation for set
let people: Set<String> = ["Denzel Washington", "Tom Cruise", "Nicolas Cage", "Samuel L Jackson"]

// type annotation for empty array
var teams: [String] = [String]()
// var cities: [String] = []
// var clues = [String]()

```

[Summary](https://www.hackingwithswift.com/quick-start/beginners/summary-complex-data)

## Day 5

```swift
// if statement

// comparing String will compare the first letter of the string
let ourName = "Dave Lister"
let friendName = "Arnold Rimmer"

if ourName < friendName {
    print("It's \(ourName) vs \(friendName)")
}

if ourName > friendName {
    print("It's \(friendName) vs \(ourName)")
}

// isEmpty for string, array, set, dictionary
if username.isEmpty {
    username = "Anonymous"
}


// if/else if/else
let a = false
let b = true

if a {
    print("Code to run if a is true")
} else if b {
    print("Code to run if a is false but b is true")
} else {
    print("Code to run if both a and b are false")
}

// && "and"
if temp > 20 && temp < 30 {
    print("It's a nice day.")
}
// || "or"
let userAge = 14
let hasParentalConsent = true

if userAge >= 18 || hasParentalConsent == true {
    print("You can buy the game")
}

// Example
enum TransportOption {
    case airplane, helicopter, bicycle, car, scooter
}

let transport = TransportOption.airplane

if transport == .airplane || transport == .helicopter {
    print("Let's fly!")
} else if transport == .bicycle {
    print("I hope there's a bike path…")
} else if transport == .car {
    print("Time to get stuck in traffic.")
} else {
    print("I'm going to hire a scooter now!")
}



// Switch
enum Weather {
    case sun, rain, wind, snow, unknown
}

let forecast = Weather.sun
switch forecast {
case .sun:
    print("It should be a nice day.")
case .rain:
    print("Pack an umbrella.")
case .wind:
    print("Wear something warm")
case .snow:
    print("School is cancelled.")
case .unknown:
    print("Our forecast generator is broken!")
}


let place = "Metropolis"

switch place {
case "Gotham":
    print("You're Batman!")
case "Mega-City One":
    print("You're Judge Dredd!")
case "Wakanda":
    print("You're Black Panther!")
default:
    print("Who are you?")
}

// That default: at the end is the default case, which will be run if all cases have failed to match.


// if you explicitly want Swift to carry on executing subsequent cases, use fallthrough
let day = 5
print("My true love gave to me…")

switch day {
case 5:
    print("5 golden rings")
    fallthrough
case 4:
    print("4 calling birds")
    fallthrough
case 3:
    print("3 French hens")
    fallthrough
case 2:
    print("2 turtle doves")
    fallthrough
default:
    print("A partridge in a pear tree")
}

// the Int for the case does not need to be in order


// ternary conditional operator for quick tests
let names = ["Jayne", "Kaylee", "Mal"]
let crewCount = names.isEmpty ? "No one" : "\(names.count) people"
print(crewCount)

enum Theme {
    case light, dark
}

let theme = Theme.dark

let background = theme == .dark ? "black" : "white"
print(background)
```

## Day 6

```swift
// For Loop
let platforms = ["iOS", "macOS", "tvOS", "watchOS"]

for os in platforms {
    print("Swift works great on \(os).")
}

for i in 1...12 {
    print("5 x \(i) is \(5 * i)")
}

// Nested For loop
for i in 1...12 {
    print("The \(i) times table:")

    for j in 1...12 {
        print("  \(j) x \(i) is \(j * i)")
    }

    print()
}

// Using print() by itself, with no text or value being passed in, will just start a new line. This helps break up our output so it looks nicer on the screen.


// Condition in the loop over range
// 5 times
for i in 1...5 {
    print("Counting from 1 through 5: \(i)")
}

print()

// 4 times
for i in 1..<5 {
    print("Counting 1 up to 5: \(i)")
}

```
