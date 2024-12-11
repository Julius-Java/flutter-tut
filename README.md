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
