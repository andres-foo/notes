# DYNAMIC VS VAR

## VAR KEYWORD
Its type gets assigned with its first value and can't be changed
```dart
// gets initialized as int
var a = 10; 

// prints int
print(a.runtimeType);

// not allowed, it can only contain int
//a = "test";
```

## DYNAMIC KEYWORD
Its type will dynamically be infered at runtime and can be changed
```dart
// gets initialized as int
dynamic a = 10;

// prints int
print(a.runtimeType);

// is allowed
a = "test";

// prints String
print(a.runtimeType);
```

## VAR IS DYNAMIC

When a local variable gets declared with **var** but left uninitialized, the static analyzer will consider it **dynamic** and it will asign the value of *Null* to it.

```dart
void main() {
    // local therefore null
    // the static analyzer considers it a dynamic
    var a;

    // prints Null
    print(a.runtimeType);
}
```
