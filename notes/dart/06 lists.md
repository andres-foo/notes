# LISTS

## CREATING A LIST

### Basic ways
```dart
// from a list literal, dart infers its type to int
var list1 = [1, 2, 3];

// specifying the type int for its elements
List<int> list2 = [1, 2, 3];

// specifying this other way
var list3 = <int>[];

// allowing for multiple types
List<dynamic> list4 = [1, 2.0, 'three'];

// lists can have trailing commands
var list5 = [
    'Soap',
    'Shampoo',
] ;

// creates list of 3 items filled with 10's
List<int> list6 = List.filled(3, 10);
print(list6); // [10, 10, 10]

// creates empty list, similar to list = [];
List<int> list7 = List.empty();
print(list7); // []

// creates a list of 3 items filled using the index
List<int> list8 = List.generate(3, (i) => (i + 1) * 3);
print(list8); // [3, 6, 9]

```

### Spread operator
```dart
// the spread operator (...) allows to insert a list into another
var list = [1, 2, 3];
var list2 = [0, ...list];
print(list2.length == 4); // true


// the null aware spread operator (...?) helps in case the list might be null
var list4 = null;
var list3 = [0, ...?list4];
print(list3); // [0]
```


### Collection if
```dart
var loggedIn = true;

// add one item
var nav = ['Home', 'Furniture', if (loggedIn) 'Profile'];

// add several items using the spread operator
var nav = [
	'Home',
	'Furniture',
	if (loggedIn) ...['Profile', 'Logout'],
];
```

### Collection for
```dart
var list1 = [1, 2, 3];
var list2 = ['#0', for(var i in list1) '#$i'];
print(list2); // ['#0', '#1', '#2', '#3',]
```

### Cascade operator
The cascade operator `..` allows to return the resulting array in operations that are void, which allows to chain multiple operations.
```dart
  var list = [3, 1, 2];
  // sort() sorts the list and returns void,
  // therefore it's normally not possible to do this:
  // print(list.sort());
  // by using the cascade we can now inmediately print the result
  print(list..sort()); // [1, 2, 3]

// with this we can chain both addAll and sort which are void
list = [3, 1, 2];
var list3 = list
  ..addAll([4, 6, 5])
  ..sort();
print(list3); // [1, 2, 3, 4, 5, 6]

// to apply map we must surround the previous operations in ()
// also notice the toList() at the end since map returns an iterable
list = [3, 1, 2];
var list4 = (list
      ..addAll([4, 6, 5])
      ..sort())
    .map(
      (e) => e * 2,
    )
    .toList();
print(list4); // [2, 4, 6, 8, 10, 12]
```

### Null
```dart
// a list that can be null
List<int>? list1 = [1, 2, 3];
list1 = null;
//list1.add(null);

// a list that can be null and accepts null items
List<int?>? list2 = [1, 2, 3];
list2.add(null);
```


### Constant and lists
```dart
// to create a list that holds a compile-time constant list of values
var constantList = const [1, 2, 3];
// constantList[0] = 4; // canont modify items
// constantList.add(4); // cannot add items
constantList = [4, 5, 6]; // CAN be redefined
// after being redefined, items can be added/changed
constantList.add(7);

// to create a compile-time constant list
const constantList2 = [1, 2, 3];
// constantList2[0] = 4; // cannot modify items
// constantList2.add(4); // cannot add items
// constantList2 = [4, 5, 6]; // cannot be redifined

//  to create a runtime constant list
final finalList = [1, 2, 3];
finalList[0] = 4; // CAN modify items
finalList.add(4); // CAN add items
// finalList = [4, 5, 6]; // cannot be redifined
```


## ACCESSING SINGLE ITEMS
```dart
var list = [1, 2, 3];
print(list[0]); // 1
print(list[list.length-1]); // 3
print(list.first); // 1
print(list.last); // 3
print(list.firstWhere((ele) => ele.isEven)); // 2
```

## LOOPING THROUGH ITEMS
All of these achieve the same result, but two of them give the following warning: [avoid_function_literals_in_foreach_calls](https://dart-lang.github.io/linter/lints/avoid_function_literals_in_foreach_calls.html
). 
```dart
var list = [1, 2, 3];

list.forEach(print);

// (warning: avoid_function_literals_in_foreach_calls)
list.forEach((ele) => print(ele));

// (warning: avoid_function_literals_in_foreach_calls)
list.forEach((ele) {
    print(ele);
});

// recommended instead
for (var ele in list) {
    print(ele);
}
```
As an example of the difference between `forEach` and `for`:
```dart
var list = [1, 2, 3, 4];

// prints 1 & 3
list.forEach((ele) {
    if (ele.isEven) {
        return; // returns from this iteration
    } else {
        print(ele);
    }
});

// prints 1
for (var ele in list) {
    if (ele.isEven) {
        return; // returns from the for loop
    } else {
        print(ele);
    }
}
```

## LISTS SHENANIGANS
```dart
var list = [1, 2, 3];

print(list.reversed); // [3, 2, 1]

// check if any item satisfies the test
dynamic res = list.any((ele) => ele.isOdd);
print(res); // true

// checks if every item satisfies the test
res = list.every((ele) => ele.isOdd);
print(res); // false

// reduces collection to single item
res = list.fold(0, (sum, ele) => sum + ele);
print(res); // 6

// modify list by calling function on every element
res = list.map((e) => e * 2);
print(res); // [2, 4, 6]

// similar to fold, starts with the first element
// because it automatically defines value as the first
// element, it's more restrictive than fold
res = list.reduce((value, element) => value + element);
print(res); // 6

// takes the first n elements from the list
print(list.take(2)); // [1, 2]

// skips the first 2
print(list.skip(2)); // 3

// returns list with elements that satisfy test
res = list.where((ele) => ele.isOdd);
print(res); // [1, 3]
```