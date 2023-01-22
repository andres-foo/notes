# TYPES

## THE TYPE SYSTEM

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
String day_of_week = "Tuesday";
```


## INFERENCE: VAR VS DYNAMIC
Besides strictly defining the type of a variable as int, double, String, etc... two more keywords can be used to let Dart infer the type:

```dart
// infered to be int at compile time
var a = 10;

// infered to be int at runtime
dynamic b = 10;
```

## VARIABLES ACCORDING TO SCOPE
There're four kinds of variables depending on where they're declared:

* **Top-level**: not associated with any class or object. Can be accessed directly from other files.
* **Static**: associated with a class.
* **Instance**: associated with an instance of a class, also refered as field/property.
* **Local**: variables with local scope (e.g inside a function or a loop).

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




