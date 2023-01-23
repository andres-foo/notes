# NUMBERS
Numbers are dividing into **int** for integers and **double** for comma separated values. They are both a subclass of **num** which includes the basic operations like _+,-,/,*,abs(),ceil()_ and _floor()_, for more functions, the library dart:math may contain them.

```
    num
  /     \
int   double
```

## DECLARING
```dart
// can only contain int
int a = 1;
// a = 10.8; // throws an error

// can only contain double
double b = 2.5;
b = 3; // stored as 3.0

// variables declared as num can contain both
num c = 3;
c = 3.5;
```

## TRANSFORMING
You can convert from and to Strings using the following:
```dart
// string to int
String aStr = '15';
int aNum = int.parse(aStr);

// string to double
String bStr = '10.3';
double bNum = double.parse(bStr);

// either to string
int cNum = 15;
String cStr = cNum.toString();
```


## COMMON FUNCTIONS
```dart
int a = 10;
a.isEven; // true
a.isOdd; // false
a.isNegative; // false
// returns number clamped between given limits
a.clamp(1, 5); // 5
// returns -1 if a is smaller, 0 if equal, 1 if bigger
print(a.compareTo(15)); // -1

double b = 4.2;
b.ceil(); // 5
b.floor(); // 4
b.remainder(2); // 0.2
b.round(); // 4

// notice that any division returns a double
print(10 / 2); // 5.0
// to avoid that, use the truncating integer division ~/ instead
print(10 ~/ 2); // 5
```

## OPERATIONS
```dart
// operations with a double return a double
print(3 + 5.0); // prints 8.0

// any division even among two ints returns a double
print(10 / 2); // 5.0
// to avoid that, use the truncating integer division ~/ instead
print(10 ~/ 2); // 5

// you can also operate on itself
int a = 5;
a += 10;

// there's also the increment and decrement operator
int b = 5;
print(b++); // prints 5, then adds 1 to b
int c = 5;
print(--c); // substracts 1 from b, then prints 4

```
