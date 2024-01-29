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

Summary  
[](https://www.hackingwithswift.com/quick-start/beginners/summary-simple-data)

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
