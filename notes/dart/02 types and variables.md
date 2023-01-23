# TYPES AND VARIABLES

## BUILT-IN TYPES

Basic types:
* Numbers (int, double)
* Strings (String)
* Booleans (bool)
* Lists (List)
* Sets (Set)
* Maps (Map)
* Runes (Runes)
* Symbols (Symbol)
* The value null (Null)

Other types:
* Object: The superclass of all Dart classes except Null.
* Enum: The superclass of all enums.
* Future & Stream: Used in asynchrony support.
* Iterable: Used in for-in loops and in synchronous generator functions.
* Never: Indicates that an expression can never successfully finish evaluating. Most often used for functions that always throw an exception.
* dynamic: Indicates that you want to disable static checking. Usually you should use Object or Object? instead.
* void: Indicates that an expression can never successfully finish evaluating. Most often used for functions that always throw an exception.

A rough diagram of the basic types is:

```
       Object
     /        \
    /          \
Iterable       num
    |        /     \
  List     int   double
     \      |      /
      \     |     /
       \    |    /   
        \   |   /
          Null
```

## VARIABLE DECLARATION

The full declaration looks like this:
```dart
String? day_of_week = 'Tuesday';
```
Where:
* **String**: is the type
* **?**: indicates that this variable can be nullable
* **day_of_the_week**: is the name of the variable
* **'Tuesday'**: is the value, in this case a String literal


## INFERENCE: VAR VS DYNAMIC
Besides strictly defining the type of a variable as int, double, String, etc... there are two keywords that can be used to let Dart infer the type:

```dart
// infered to be int at compile time
var a = 10;

// infered to be int at runtime
dynamic b = 10;
```

## SCOPE
There're four kinds of variables depending on where they're declared:

* **Top-level**: not associated with any class or object. Can be accessed directly from other files
* **Static**: associated with a class
* **Instance**: associated with an instance of a class, also refered as field/property
* **Local**: variables with local scope (e.g inside a function or a loop)

```dart
// top-level
int a = 1;

class A {
    // static
    static int b = 2;
    // instance
    int c = 3;
}

void main() {
    // local
    int d = 4;
}
```




