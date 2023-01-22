
# MARKDOWN

A small reference to markdown

## COMMON

```
_text in italic_
```

```
**text in bold**
```

```
**_Text in both, doesn't matter the order_**
```

## Link and image

```
[Link text](www.link-address.com)
```

```
![Text for the image](https://link-to-image.jpg)
```

## Block quote
```
> This is a block quote
```
### Blockquote with empty lines
```
> Add the "greater than" caret symbol
to empty lines in order to make
>
> the text be part of the same block quote
```
## HEADERS

```
# This is an h1
## This is an h2
### This is an h3
#### This is an h4
##### This is an h5
###### This is an h6
```
## LISTS

### Unordered list
```
* Element 1

* Element 2
```

### Ordered list
```
1. Element 1

2. Element 2
```
### Nested list
```
* Group 1

    * Element 1 in group 1

* Group 2
```

## CODE

### Inline code

```
This is some `inline code`
```
### Block code
```
```javascript
// this is some block code 
\```
```
The last backslash is not part of it.

## Hard break versus soft break
To break text into two lines, you can do a **hard break** by skipping a line:
```
First line

Second line
```
or a **soft break** by adding two spaces at the end of a line:
```
First line__
Second line
```

## Tables
To create tables, use **pipes (|)** to divide each column and at least **three hypens (---)** to define the headers. The extra hypens or spaces don't affect the result
```
Header 1 | Header 2
-------- | --------
Text     | Text
```
### Aligning tables
You can use a **colon (:)** to indicate the alignment
```
|A very long header 1|A very long header 2|A very long header 3|
|:---|:---:|---:|
|Left aligned|Centered|Right aligned|
```




