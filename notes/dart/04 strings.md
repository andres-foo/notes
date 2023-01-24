# STRINGS

## STRING LITERALS

```dart
// created with either single or double quotes
var s1 = 'Single quote string';
var s2 = "Double quote string";

// escaping single quote
var s3 = 'Single \'quote\' string';
var s4 = "Single 'quote' string";
```

## INTERPOLATION

```dart
// for an identifier simply use $identifier
var name = 'yui';
print('Welcome $name');

// for an expression use ${expression}
print('Welcome ${name.toUpperCase()}');
```

## CONCATENATION

```dart
var s1 = 'Easiest' ' string' ' concatenation';

var s2 = 'String '
'concatenation '
"on line breaks";

var s3 = 'String' + 'concatenation' + "using +";
```

## MULTI-LINE STRING

```dart
// for an identifier simply use $identifier
var s1 = '''Multiple
line
string''';

var s2 = """Multiple
line
string""";
```
## RAW STRING
```dart
var str = r'First line\nSecond line';
print(str); // First line\nSecond line
```

## COMMON FUNCTIONS
```dart
var str = 'Test string';

print(str.toUpperCase()); // TEST STRING
print(str.toLowerCase()); // test string

print(str.isEmpty); // false
print(str.isNotEmpty); // true

print(str.contains('string')); // true
print(str.split(' ')); // ['Test', 'string']

print(str.replaceAll('string', 'text')); // Test text
print(str.replaceAll(RegExp(r't\s'), 'T ')); // TesT string

print(str.substring(5, 8)); // str
```