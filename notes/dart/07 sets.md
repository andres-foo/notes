# SETS

Sets are unordered collections of unique items

## CREATING A SET

```dart
// from a set literal
var set1 = {1, 2, 3};
print(set1.runtimeType);

// specifying the type int for its elements
Set<int> set2 = {1, 2, 3};
print(set2.runtimeType);

// specifying this other way
var set3 = <int>{};

// without any hint, dart by default assumes {} is a map 
var set4 = {};
print(set4.runtimeType); // _InternalLinkedHashMap<dynamic, dynamic>

// because the items are unique, the final "2" gets discarded
var set5 = {1, 2, 3, 2};
print(set5); // {1, 2, 3}

// sets can also have trailing commas
var set6 = {
    'Yui',
    'Keane',
};
```

## SIMILARITIES TO LISTS
There're a lot of similar features between lists and sets:

```dart
var set1 = {1, 2, 3};

// adding
set1.add(4);
set1.addAll({5, 6});

// spread operator
var set2 = {...set1, 7};
print(set2);

// collection if and collection for
var set4 = {
    'a',
    for (var i in set1)
        if (i.isEven) i,
};
print(set4); // {'a', 2, 4, 6}
```

## SET OPERATIONS
```dart
var list1 = {'a', 'b', 'c'};
var list2 = {'a', 'd', 'e'};

// operations
print(list1.union(list2)); // {'a', 'b', 'c', 'd', 'e'}
print(list1.intersection(list2)); // {'a'}
print(list1.difference(list2)); // {'b', 'c'}
```