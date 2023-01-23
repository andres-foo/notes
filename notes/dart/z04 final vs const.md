# FINAL VS CONST
Both **final** and **const** represent constant values but have some differences between them:


## FINAL

* Is a runtime constant, therefore sometimes the static analyzer will fail to warn us on some edge cases
* Variables marked as final cannot be reassigned but CAN be modified 

```dart
void main() {
  // CASE 1
  final int a = 1;
  //cannot be reassigned
  // a = 5;

  // CASE 2
  final List<int> b = [1, 2, 3];
  //cannot be reassigned but CAN be modified
  // b = [1, 2, 3, 4];
  b.add(4);

  // CASE 3
  final List<int> c = const [1, 2, 3];
  // the static analyzer doesn't know that because we assigned a constant
  // value to a final variable, it can't be modified
  c.add(4); // will thrown an error when compiling
}
```

## CONSTANT

* Is a compile time constant, therefore its value must be known at compile time
* Variables marked as const cannot be reassigned and also CAN NOT be modified
* Cannot be used for instance variables since it requires to initialize the class first

```dart
void main() {
  // CASE 1
  const int a = 1;
  //cannot be reassigned
  // a = 5;

  // CASE 2
  const List<int> b = [1, 2, 3];
  //cannot be reassigned and CAN NOT be modified
  // b = [1, 2, 3, 4];
  // b.add(4); // doesn't work

  // doesnt work, must be initialized with a constant value
  const int c = myFunction();
}

int myFunction() => 1;
```