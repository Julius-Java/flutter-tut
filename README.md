# Dart: Data Types - integers, strings, booleans

Variables in dart are assigned specific data type, it helps the comiler determine what type of data it is dealing with and the valid operations that can be performed on that data.

```dart
int age = 18;
String name = 'Pius Patrick';
bool isAdult = false;
```

Dart as a programming language supports a handful of basic/built-in data types, and they're shown in the table below
| Data Type | Representation In Code
| :------------ | :------------------------------------------ |
| Numbers | `(int, double)` |
| Strings | `(String)` |
| Booleans | `(Bool)` |
| Records | `((value1, value2))` |
| Functions | `(Function)` |
| Lists | `(List)` also know as _arrays_ |
| Sets | `(Set)` |
| Maps | `(Map)` |
| Runes | `(Runes)` |
| Symbols | `(Symbols)` |
| The null value | `(Null)` |

## Numbers

Dart numbers come in two flavors:

-   int
-   double

A number without a decimal, is of type `int`. Here are some examples of defining integer literals:

```dart
var x = 1;
```

A number that includes decimal, is of type `double`. Here are some examples of defining double literals:

```dart
var y = 1.1;
var exponents = 1.42e5;
```

You can also declare a variable as a num. If you do this, the variable can have both integer and double values.

```dart
num x = 1; // x can have both int and double values
x += 2.5;
```

Here's how you turn a string into a number, or vice versa:

```dart
// String -> int
var one = int.parse('1');
assert(one == 1);

// String -> double
var onePointOne = double.parse('1.1');
assert(onePointOne == 1.1);

// int -> String
String oneAsString = 1.toString();
assert(oneAsString == '1');

// double -> String
String piAsString = 3.14159.toStringAsFixed(2);
assert(piAsString == '3.14');
```

## Strings

A string is a chain of characters enclosed in quotes. You can use either single or double quotes to create a string:

```dart
var s1 = 'Single quotes work well for string literals.';
var s2 = "Double quotes work just as well.";
var s3 = 'It\'s easy to escape the string delimiter.';
var s4 = "It's even easier to use the other delimiter.";
```

You can put the value of an expression inside a string by using ${expression}. If the expression is an identifier, you can skip the {}. This is also know as `string interpolation`

```dart
var name = 'John Doe';
print('My name is ${name}');
```

You can put add two separate strings together using `adjacent string literals` or the `+` operator

**_ Using adjacent string literals _**:

```dart
var s1 = 'String '
        'concatenation'
                " works even over line breaks.";
print(s1);
// This would output 'String concatenation works even over line breaks.' to the console
```

**_ Using the `+` operator _**:

```dart
var s2 = 'The + operator ' + 'works, as well.';
print(s2);
// This would output 'The + operator works, as well.' to the console
```

To create a multi-line string, use a triple quote with either single or double quotation marks:

```dart
        var s1 = '''
        You can create
        multi-line strings like this one.
        ''';

        var s2 = """This is also a
        multi-line string.""";
```

## Booleans

A boolean in programming is a data type that represents only two possible values: `true` or `false`, and dart has it as a built-in data type.

To represent boolean values in dart, the `bool` keyword is used.

```dart
bool isRaining = true;
bool isSunny = false;
```

### 📝 Exercises!!!

#### 1. Numbers Exercise

Task:
Create a Dart program that takes two numbers (an `int` and a `double`), adds them, and prints the result.

#### 2. Strings Exercise

Task:
Write a Dart program that asks for a student's name and favorite subject, then prints a sentence like:

<details>
  <summary>Solution</summary>

```dart
import 'dart:io'; // Required for reading user input

void main() {
 // Asking for the student's name
 stdout.write("Enter the student's name: ");
 String name = stdin.readLineSync() ?? '';

 // Asking for the favorite subject
 stdout.write("Enter the favorite subject: ");
 String subject = stdin.readLineSync() ?? '';

 // Displaying the message
 print("$name's favorite subject is $subject.");
}
```

</details>

#### 3. Booleans Exercise

Task:
Write a program that checks if a number is greater than 50. If it is, print `true`; otherwise, print `false`.

<br />
<br />
<br />

# Dart: Randomness

The dart:math library provides common math functionality such as sine and cosine, maximum and minimum, and constants such as pi and e, and random number generation. Most of the functionality in the Math library is implemented as top-level functions.

We'll be looking specifically into `randomness` in dart

To leverage the rich functionalites of the math library, first import it at the top-level of your program, like so:

```dart
import 'dart:math';
```

<br />

1. **Create an instance of `Random`**:

    - ```dart
      var random = Random();
      ```

<br />

2. **Generate random numbers**:

    - **Random integer between `0` and an upper limit (exclusive)**:

        ```dart
        int randomNumber = random.nextInt(10); // Generates a number between 0 and 9
        ```

    - **Random `double` between 0.0 and 1.0**:

        ```dart
        double randomDouble = random.nextDouble(); // Generates a number like 0.237
        ```

<br />

3. **Generate random boolean values**:

    - ```dart
      bool randomBool = random.nextBool(); // true or false
      ```

## 📌 Simple Exercise

Let's create a Dart program that generates a random number between 1 and 6 (like rolling a dice).
<br/>
We'll also generate a random true or false value to simulate a coin toss.

### SOLUTION

<details>
  <summary>Solution</summary>

```dart
import 'dart:math';

void main() {
  var random = Random();

  // Simulate rolling a dice (number between 1 and 6)
  int diceRoll = random.nextInt(6) + 1;
  print("You rolled a: $diceRoll");

  // Simulate a coin toss (true = Heads, false = Tails)
  bool coinToss = random.nextBool();
  print("Coin toss result: ${coinToss ? 'Heads' : 'Tails'}");
}
```

</details>

<br />
<br />
<br />

# Dart: List, Maps & Control Flow.

## List

Arrays in programming also known as `List` is perherps the most common collection in nearly every programming language, it is an `ordered` group of objects.

<br/>

In Dart, arrays are `List` objects, so most people just call them _lists_.

Dart list literals/items are denoted by a comma separated list of expressions or values, enclosed in square brackets (`[]`). Here's a simple Dart list:

```dart
var list = [1, 2, 3];
```

<br/>

You can add a comma after the last item in a Dart collection literal. This trailing comma doesn't affect the collection, but it can help prevent copy-paste errors.

```dart
var list = [
  'Car',
  'Boat',
  'Plane',
];
```

Lists use `zero-based indexing,` where `0` is the index of the first value and `list.length - 1` is the index of the last value. You can get a list's length using the `.length` property and access a list's values using the subscript operator (`[]`):

```dart
var list = [1, 2, 3];

list[1] = 1;
```

<br/>
<br/>

## Maps

In general, a map is an object that associates keys and values. Both keys and values can be any type of object. Each key occurs only once, but you can use the same value multiple times. Dart support for maps is provided by map literals and the Map type.

Here are a couple of simple Dart maps, created using map literals:

```dart
var gifts = {
  // Key:    Value
  'first': 'partridge',
  'second': 'turtledoves',
  'fifth': 'golden rings'
};

var nobleGases = {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};
```

You can create the same objects using a Map constructor:

```dart
var gifts = Map<String, String>();
gifts['first'] = 'partridge';
gifts['second'] = 'turtledoves';
gifts['fifth'] = 'golden rings';

var nobleGases = Map<int, String>();
nobleGases[2] = 'helium';
nobleGases[10] = 'neon';
nobleGases[18] = 'argon';
```

Add a new key-value pair to an existing map using the subscript assignment operator ([]=):

```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds'; // Add a key-value pair
```

Retrieve a value from a map using the subscript operator ([]):

```dart
var gifts = {'first': 'partridge'};
print(gifts['first']); // This will output 'partridge' to the console
```

If you look for a key that isn't in a map, you get null in return:

```dart
var gifts = {'first': 'partridge'};
print(gifts['fifth']); // This will output null to the console because the key 'fifth' doesn't exist in the map
```

Use `.length` to get the number of key-value pairs in the map:

```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds';
print(gifts.length); // This will output 2 to the console because the number of key-value pairs in the map is -> 2
```

<br/>
<br/>

## 🧑‍🏫 Control Flow in Dart

### Control Flow in Dart

Control flow refers to the order in which the statements or instructions are executed in a program. Dart offers several control flow statements to handle conditional operations, loops, and exceptions.

---

### Control Flow Statements in Dart

#### 1. **if / else Statement**

The `if` statement allows you to execute code only if a certain condition is true. You can also use `else` to specify a block of code to execute when the condition is false.

```dart
int age = 20;

if (age >= 18) {
  print("You are an adult.");
} else {
  print("You are a minor.");
}
```

<br/>

#### 2. **if / else if / else Statement**

If you need to check multiple conditions, you can use else if to chain multiple conditions.

```dart
int score = 85;

if (score >= 90) {
  print("Grade: A");
} else if (score >= 80) {
  print("Grade: B");
} else if (score >= 70) {
  print("Grade: C");
} else {
  print("Grade: F");
}
```

#### 3. **Switch Statement**

The `switch` statement allows you to test a variable against a list of values and execute different blocks of code based on the match.

```dart
String day = "Monday";

switch (day) {
  case "Monday":
    print("Start of the work week!");
    break;
  case "Friday":
    print("End of the work week!");
    break;
  default:
    print("Midweek days!");
}
```

#### 4. **For Loop**

A `for` loop is used to repeat a block of code a specified number of times.

```dart
for (int i = 0; i < 5; i++) {
  print("Iteration $i");
}
```

#### 5. **While Loop**
A `while` loop executes a block of code as long as a condition is true.
```dart
int count = 0;

while (count < 5) {
  print("Count: $count");
  count++;
}
```

#### 6. **Do-While Loop**

The `do-while` loop is similar to the while loop, but it guarantees that the code will run at least once before checking the condition.

```dart
int count = 0;

do {
  print("Count: $count");
  count++;
} while (count < 5);
```

#### 7. **Break Statement**

The `break` statement is used to exit a loop or `switch` statement prematurely.

```dart
for (int i = 0; i < 10; i++) {
  if (i == 5) {
    break; // Exit the loop when i equals 5
  }
  print(i);
}
```

#### 8. **Continue Statement**

The `continue` statement skips the current iteration of a loop and proceeds to the next one.

```dart
for (int i = 0; i < 5; i++) {
  if (i == 2) {
    continue; // Skip the iteration when i equals 2
  }
  print(i);
}
```

### 📌 Simple Exercise
Here are some exercises to help reinforce the concepts of control flow:

1. Write a program that checks whether a number is even or odd. The program should output "Even" if the number is divisible by 2, otherwise output "Odd".

2. Create a program that checks the day of the week using a switch statement and outputs a different message for each day.






