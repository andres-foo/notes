# MAPS

Maps are objets that associate keys and values. Each key must be unique and occurs only once.

## CREATING A MAP

```dart
// from a literal
var map1 = {1: 'a', 2: 'b', 3: 'c'};

// an empty map, {} is assumed to be a map and not a set
var map2 = {};

// defyning the type
Map<int, String> map3 = {1: 'a', 2: 'b'};

// or like this
var map4 = <int, String>{1: 'a', 2: 'b'};
```

## ADDING ITEMS TO A MAP
```dart
var map = {1: 'a', 2: 'b'};

// defining value by the key
map[3] = 'c';

// using add entries
map.addEntries([MapEntry(4, 'd')]);
```
## SIMILARITIES TO LIST AND SETS
```dart
var map1 = {1: 'a', 2: 'b'};

// spread operator
var map2 = {...map1, 3: 'c'};

// collection if and collection for
var list = [3, 4];
var map3 = {
    1: 'a',
    if (true) 2: 'b',
    for (var i in [3, 4]) i: 'c',
    5: 'd', // trailing comma
};
print(map3); // {1: a, 2: b, 3: c, 4: c, 5: d}
```