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
dart create -h
```
You can create a package based in different templates, for example typing:
```
dart create -t console-full my_package
```

Will create the following sctructure:
```
my_package
 |- bin
    |- my_package.dart
 |- lib
    |- my_package.dart
 |- test
    |- my_package.dart
 |- pubspec.yaml
 |- analysis_options.yaml
 |- .gitignore
 |- README.md
 |- CHANGELOG.md

```
The default template **console-simple** omits the _test_ and _lib_ folders.

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

### Running with vscode

If the default file is selected, going to the **Run** menu or pressing the corresponding key will work. If a different file is selected, vscode will create a file called *launch.json* in which we can define two values to make it work properly.

Under _configurations_ add:
```
"program": "path_to_file_to_run",
"args": ["1", "2", "3"]
```
Now go to the **Run** menu or press the corresponding shortcut.