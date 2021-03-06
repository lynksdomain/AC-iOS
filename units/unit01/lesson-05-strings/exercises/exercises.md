### Strings Exercises

---

#### Question 1.
Without using string interpolation, print out a string that combines myGreeting and myName.

```swift
let myGreeting = "Hello, "
let myName = "Ben"
```

<details>
<summary><b>Solution</b></summary>

```swift
print(myGreeting, myName, separator: "")
```

</details>

#### Question 2.
Write code that prints out myArray as a single string separated by spaces.

```swift
let myArray = ["Hi", "there,", "how","is","it","going?"]
```
<details>
<summary><b>Solution</b></summary>

```swift
print(myArray.joined(separator: " "))
```

</details>


#### Question 3.
Write code that prints out all the numbers from 1 to 10 as a single string.  (Hint: the String() function can convert an int to a string)

<details>
<summary><b>Solution</b></summary>

```swift
var singleStringThree = ""

for num in 1...10 {
    let numString = String(num)
    singleStringThree.append("\(numString) ")
}

print(singleStringThree)
```

</details>


#### Question 4.
Write code that prints out all the even numbers from 5 to 51 as a single string.

<details>
<summary><b>Solution</b></summary>

```swift
var singleStringFour = ""

for num in 5...51 {
    if num % 2 == 0 {
        let numString = String(num)
        singleStringFour.append("\(numString) ")
    }
}

print(singleStringFour)
```

</details>

#### Question 5.
Write code that prints out every number ending in 4 between 1 and 60 as a single string.

<details>
<summary><b>Solution</b></summary>

```swift
var singleStringFive = ""

for i in 1...60 {
    if i % 10 == 4 {
        let numString = String(i)
        singleStringFive.append("\(numString) ")
    }
}

print(singleStringFive)
```

</details>


#### Question 6.
Print each character in the string ```Hello world!```

<details>
<summary><b>Solution</b></summary>

```swift
var myStringSix = "Hello world!"

for char in myStringSix.characters {
    print(char)
}

```

</details>

#### Question 7.
Using '.characters' and loop, print the last character in the string below
```swift
let myStringSeven = "Hello world!"
```

<details>
<summary><b>Solution</b></summary>

```swift
for char in myStringSeven.characters {
    if let lastChar = myStringSeven.characters.last {
        if char == lastChar {
            print(char)
        }
    }
}
```

</details>


#### Question 8.
Write code that switches on a string.  If the string's length is even, print out every character.  If the string's length is odd, print out every other character

<details>
<summary><b>Solution</b></summary>

```swift
let myStringEight = "Hello Sunshine"

switch myStringEight {
case myStringEight where myStringEight.characters.count % 2 == 0:
    for char in myStringEight.characters {
        print(char)
    }
default:
    for i in 0...myStringEight.characters.count where i % 2 == 0 {
        let index = myStringEight.index(myStringEight.startIndex, offsetBy: i)
        print(myStringEight[index])
    }
}
```

</details>


#### Question 9.
Initialize a String with a character. Show that it is a Character, and not another String, you're using
to initialize it.

<details>
<summary><b>Solution</b></summary>

```swift
let charNine: Character = "C"
print(type(of: charNine)) //.dynamicType is depracated 
let stringFromChar = String(charNine)
print(type(of: stringFromChar))
```

</details>

### Unicode exercises

---

#### Question 10.
Build five pairs of canonically equivalent strings, the first of each being a pre-composed character and
the second being one that uses combinable unicode scalars. Show that they are equivalent.

Refer to this [Unicode Table](http://unicode-table.com/en/).

<details>
<summary><b>Solution</b></summary>

```swift
let preComposed1 = "See you ma\u{F1}ana"
let combinableScalars1 = "See you ma\u{6E}\u{303}ana"
let isEqual1 = preComposed1 == combinableScalars1
print(isEqual1)

let preComposed2 = "Apple pie \u{E1} la mode is so delicious!"
let combinableScalars2 = "Apple pie \u{61}\u{301} la mode is so delicious!"
let isEqual2 = preComposed2 == combinableScalars2
print(isEqual2)

let preComposed3 = "Beyonc\u{E9} is my favorite artist"
let combinableScalars3 = "Beyonc\u{65}\u{301} is my favorite artist"
let isEqual3 = preComposed3 == combinableScalars3
print(isEqual3)

let preComposed4 = "Have you ever tried cr\u{E8}me br\u{FB}l\u{E9}e?"
let combinableScalars4 = "Have you ever tried cr\u{65}\u{300}me br\u{75}\u{302}l\u{65}\u{301}e?"
let isEqual4 = preComposed4 == combinableScalars4
print(isEqual4)

let preComposed5 = "Being na\u{EF}ve has its pros and cons."
let combinableScalars5 = "Being na\u{69}\u{308}ve has its pros and cons."
let isEqual5 = preComposed5 == combinableScalars5
print(isEqual5)
```

</details>

#### Question 11.
Using only Unicode, print out "HELLO WORLD!"

<details>
<summary><b>Solution</b></summary>

```swift
print("\u{48}\u{45}\u{4C}\u{4C}\u{4F} \u{57}\u{4f}\u{52}\u{4C}\u{44}\u{21}")
```

</details>


#### Question 12.
Using only Unicode, print out your name.

<details>
<summary><b>Solution</b></summary>

```swift
print("\u{45}\u{72}\u{69}\u{63}\u{61} \u{53}\u{74}\u{65}\u{76}\u{65}\u{6E}\u{73}")
```

</details>

#### Question 13.
Using only Unicode, print "Hello World" in another language.

<details>
<summary><b>Solution</b></summary>

```swift
print("\u{53}\u{61}\u{6C}\u{61}\u{6D}\u{75}\u{2C} \u{44}\u{75}\u{6E}\u{69}\u{61}") //Salamu, Dunia (Swahili)
```

</details>

#### Question 14.
Print the below flower box using the following information.
- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are ```|```
- Use the __terminator__ argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -
```
<details>
<summary><b>Solution</b></summary>

```swift
let horizontalDash = "\u{2d}"
let verticalDash = "\u{7c}"
let flower = "\u{2698}"

for barCount in 0..<10 {
    print(horizontalDash, terminator: " ")
    if barCount == 9 {
        print(horizontalDash)
    }
}

var counter = 0

repeat {
    for i in 0..<5 {
        print(verticalDash, flower, separator: " ", terminator: " ")
        if i == 4 {
            print(verticalDash, terminator: "")
        }
    }
    counter += 1
    print("")
} while counter < 7


for barCount in 0..<10 {
    print(horizontalDash, terminator: " ")
    if barCount == 9 {
        print(horizontalDash)
    }
}
```

</details>


#### Question 15.
Write a program that builds a [chess board using Unicode](https://en.wikipedia.org/wiki/Chess_symbols_in_Unicode).

<details>
<summary><b>Solution</b></summary>

```swift
let whiteKing = "\u{2654}"
let whiteQueen = "\u{2655}"
let whiteRook = "\u{2656}"
let whiteBishop = "\u{2657}"
let whiteKnight = "\u{2658}"
let whitePawn = "\u{2659}"

let blackKing = "\u{265A}"
let blackQueen = "\u{265B}"
let blackRook = "\u{265C}"
let blackBishop = "\u{265D}"
let blackKnight = "\u{265E}"
let blackPawn = "\u{265F}"

print(whiteRook, whiteKnight, whiteBishop, whiteQueen, whiteKing, whiteBishop, whiteKnight, whiteRook)
print(whitePawn, whitePawn, whitePawn, whitePawn, whitePawn, whitePawn, whitePawn, whitePawn)
print()
print()
print()
print()
print(blackPawn, blackPawn, blackPawn, blackPawn, blackPawn, blackPawn, blackPawn, blackPawn)
print(blackRook, blackKnight, blackBishop, blackQueen, blackKing, blackBishop, blackKnight, blackRook)
```

</details>

