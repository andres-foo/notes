# UNINITIALIZED VARIABLES


## NULLABLE VARIABLES
Nullable variables can be left un-initialized for all scopes (top-level, static, instance and local) in which case they'll be assigned the value of null.

```dart
int? a;

print(a); // Null
```
## NON-NULLABLE VARIABLES
For non-nullable it depends on the scope

### Top-level
```dart
// throws an error
int a; 

// the late keyword allows to postpone the inizialitation
late int b;
```

### Static 
```dart
class A {
    // throws an error
    static int a;

    // the late keyword allows to postpone the initialization
    static late int b;
}
```

## Instance
  
```dart
class A {
    // must be initialized before it reaches the constructor or throws an error
    int a;

    // the late keywowrd allows to postpone the initialization
    late int b;

    // here "a" is being initialized before the constructor
    A({required this.a}) {}  
}
```

## Local
```dart
void myFunction() {
    // must be initialized before use or throws an error
    int b;  
}
```






