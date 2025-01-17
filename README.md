# Enumerations lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

a) Define an enumeration called `iOSDeviceType` with member values `iPhone`, `iPad`, `iWatch`. Create a variable called `myDevice` and assign it one member value.

```swift
enum iOSDeviceType {
case iPhone
case iPad
case iWatch
}

var myDevice = iOSDeviceType.iPhone
```

b) Adjust your code above so that `iPhone` and `iPad` have associated values of type String which represents the model number, eg: `iPhone("6 Plus")`. Use a switch case and let syntax to print out the model number of each device.

```swift
enum iOSDeviceType {
case iPhone(String)
case iPad(String)
case iWatch


func model() {
switch self {
case .iPhone(let x):
print("This is an iPhone \(x)")
case .iPad(let x):
print("This is and iPad \(x)")
default:
print("This is an iWatch")
}
}
}

let myDevice = iOSDeviceType.iPhone("6 Plus")
myDevice.model()

```

## Question 2

a) Write an enum called `Shape` and give it cases for `triangle`, `rectangle`, `square`, `pentagon`, and `hexagon`.

```swift
enum Shape {
case triangle
case rectangle
case square
case pentagon
case hexagon
}
```
b) Write a method inside `Shape` that returns how many sides the shape has. Create a variable called `myFavoritePolygon` and assign it to one of the shapes above, then print out how many sides it has.

```swift
enum Shape {
case triangle
case rectangle
case square
case pentagon
case hexagon
func sidesOfShape() -> Int {
switch myFavoritePolygon {
case .triangle:
return 3
case .rectangle:
return 4
case .square:
return 4
case .pentagon:
return 5
case .hexagon:
return 6
}
}
}

var myFavoritePolygon = Shape.pentagon
print(myFavoritePolygon.sidesOfShape())
```

c) Re-write `Shape` so that each case has an associated value of type Int that will represent the length of the sides (assume the shapes are regular polygons so all the sides are the same length) and write a method inside that returns the perimeter of the shape.

```swift
enum Shape {
case triangle(Int)
case rectangle(Int)
case square(Int)
case pentagon(Int)
case hexagon(Int)

func perimeterOfShape() -> Int {
switch self {
case .triangle(let length):
return 3 * length
case .rectangle(let length):
return 4 * length
case .square(let length):
return 4 * length
case .pentagon(let length):
return 5 * length
case .hexagon(let length):
return 6 * length
}
}
}

var myFavoritePolygon = Shape.pentagon(3).perimeterOfShape()
```


## Question 3

Write an enum called `OperatingSystem` and give it cases for `windows`, `mac`, and `linux`. Create an array of 10 `OperatingSystem` objects where each one is set to a random operating system. Then, iterate through the array and print out a message depending on the operating system.

```swift

enum OperatingSystem {
case windows
case mac
case linux

}

var arrayOfOS = [OperatingSystem.windows, OperatingSystem.mac, OperatingSystem.windows, OperatingSystem.windows, OperatingSystem.linux, OperatingSystem.mac, OperatingSystem.mac, OperatingSystem.linux, OperatingSystem.linux, OperatingSystem.mac]

for oS in arrayOfOS {
switch oS {
case .windows:
print("This is a Windows operating system")
case .mac:
print("This is a mac operating system")
case .linux:
print("This is a linux operating system")
}
}

```
## Question 4

You are working on a game in which your character is exploring a grid-like map. You get the original location of the character and the steps he will take.

- A step .up will increase the y coordinate by 1.
- A step .down will decrease the y coordinate by 1.
- A step .right will increase the x coordinate by 1.
- A step .left will decrease the x coordinate by 1.
- Print the final location of the character after all the steps have been taken.

```swift
enum Direction {
    case up
    case down
    case left
    case right
}

var location = (x: 0, y: 0)
var steps: [Direction] = [.up, .up, .left, .down, .left]

// your code here

```


## Question 5

a) Define an enumeration named `HandShape` with three members: `.rock`, `.paper`, `.scissors`.

b) Define an enumeration named `MatchResult` with three members: `.win`, `.draw`, `.lose`.

c) Write a function called `match` that takes two `HandShapes` and returns a `MatchResult`. It should return the outcome for the first player (the one with the first hand shape).

Hint: Rock beats scissors, paper beats rock, scissor beats paper


## Question 6

a) You are given a `CoinType` enumeration which describes different coin values. Print the total value of the coins in the array `moneyArray` which contains tuples of type (`quantity`, `CoinType`).

```swift
enum CoinType: Int {
    case penny = 1
    case nickle = 5
    case dime = 10
    case quarter = 25
}

var moneyArray:[(Int,CoinType)] = [(10,.penny),
                                   (15,.nickle),
                                   (3,.quarter),
                                   (20,.penny),
                                   (3,.dime),
                                   (7,.quarter)]

// your code here
```

b) Write a method in the `CoinType` enum that returns an Int representing how many coins of that type you need to have a dollar. Then, create an instance of `CoinType` set to `.nickle` and use your method to print out how many nickels you need to have to make a dollar.


## Question 7

a) Write an enum called `DayOfWeek` to represent the days of the week with a raw value of type String.

```swift
enum DayOfWeek: (String) {
case sunday = "Sunday"
case monday = "Monday"
case tuesday = "Tuesday"
case wednesday = "Wednesday"
case thursday = "Thursday"
case friday = "Friday"
case sauturday = "Saturday"
}
```

b) Given the array `poorlyFormattedDays`, write code that will produce an array of enums that match the days.

`let poorlyFormattedDays = ["MONDAY", "wednesday", "Sunday", "monday", "Tuesday", "WEDNESDAY", "thursday", "SATURDAY", "tuesday", "FRIDAy", "Wednesday", "Monday", "Friday", "sunday"]`

c) Write a method in `DayOfWeek` called `isWeekend` that determines whether a day is part of the weekend or not and write code to calculate how many week days appear in `poorlyFormattedDays`.

```swift
// I didn't finish working on this one.

enum DayOfWeek: (String) {
case sunday = "Sunday"
case monday = "Monday"
case tuesday = "Tuesday"
case wednesday = "Wednesday"
case thursday = "Thursday"
case friday = "Friday"
case saturday = "Saturday"

func isWeekend() {
switch self {
case .saturday:
print("\(DayOfWeek.saturday) is on the weekend")
case .sunday:
print("\(DayOfWeek.sunday) is on the weekend")
default:
print("This is a weekday")
}
}
}
```

## Question 8

a) Create an enum called `MetroLine` with cases for the colors of the metro train lines. Create an instance of `MetroLine`.

b) Modify your enum so that each case has an associated value of either Character or Int that will represent the train on that line. Create a new instance of `MetroLine` and give it an appropriate train letter or number.

c) Write code that prints the train letter or number of your instance of `MetroLine`.


## Question 9

a) Think of your own example of something that can be modeled as an enum and write it. Remember that enums allow you to create instances of a defined list of cases.

b) Add a method to your enum.... try to have the method make sense.
