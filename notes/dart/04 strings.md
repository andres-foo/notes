# STRINGS

A Dart string is a sequence of UTF 16 code units, more on this at the end.

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

## UNICODE
As mentioned above, strings are a sequence of UTF 16 code units, we can manually insert any UTF 16 code unit into our strings, for example:

```dart
  // the code unit for the ghost emoji is U+1F47B
  print('Hello \u{1F47B}'); //Hello 👻
```
If we want to find out the code unit for a character we can do:
```dart
// example word
var word = '日本語';

// find out a specific code unit or unicode code point
print('Code Unit for 本 is: ${word.codeUnitAt(1)}'); // 26412

// print the code units for each character
print(word.codeUnits); // [26085, 26412, 35486]
```
To get back the character from the unicode code point we need to use the function `fromCharCode` or convert the code points to hexadecimal:
```dart
// find out a specific code unit
var codeUnit = '日'.codeUnitAt(0); // 26085

// Using the decimal code unit directly
print('Sun is ${String.fromCharCode(codeUnit)}'); // Sun is 日

// obtaining the hexadecimal value from the code point
print(codeUnit.toRadixString(16)); // 65e5

// now we use the decimal
print('Sun is \u{65e5}'); // Sun is 日
```