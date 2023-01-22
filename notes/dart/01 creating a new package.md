# CREATING A NEW PACKAGE

## AVAILABLE COMMANDS AND FLAGS
To check what's available type:
```
dart
```
It will show commands like **compile**, **create**, **pub**, **run** and others.

## CREATING A NEW PACKAGE
To see the available options type:
```
dart help create
```
You can create a package based in different templates, for example typing:
```
dart create my_package
```

Will create a package based on the default **console** template with the following structure:
```
my_package
 |- /bin
    |- my_package.dart
 |- /lib
    |- my_package.dart
 |- /test
    |- my_package.dart
 |- pubspec.yaml
 |- pubspec.lock
 |- analysis_options.yaml
 |- .gitignore
 |- README.md
 |- CHANGELOG.md
 |- /.dartool

```

## RUNNING THE PACKAGE

### Default

By default using the command `run` will execute a file with the same name as the package located in the **bin** folder. 
```
dart run
```
would execute:
```
/bin/<name_of_the_package>.dart
```
### With arguments
If you need to pass arguments, pass the name of the package:
```
dart run <name_of_the_package> 1 2 3
```
### Running a file
You can also point dart to run a specific file:
```
dart run ./name_of_a_file.dart 1 2 3
```