Style Guide for R Code
======================
A coding standard for the [R programming language](http://www.r-project.org/), 
based on the [Style Guide for Python Code (PEP8)](http://www.python.org/dev/peps/pep-0008/Style Guide for Python Code).
The *structure* of this guide is based, in part, on [Google's style guide for R code](http://google-styleguide.googlecode.com/svn/trunk/Rguide.xml).

Overview
--------

* [Identifiers](#identifiers): var_name, fxn_name, and ClassName
* [White-space](#whitespace): Indent = 4 spaces
* [Layout](#layout): Don't try and cram too many things on one line.
* [Line-width](#linewidth): 80 characters
* [Assignment](#assignment): "=" and not "<-"
* [Semicolons](#semicolons): Don't use them.
* [File names](#filenames): .r, .rmd, etc.

<a id="identifiers">Identifiers</a>
-----------------------------------
### Variable names
Lowercase characters with words separated by underscores, e.g. "my_var".

### Function names
Same as above...

### Class names
CamelCase -- No underscores, first letter of each word capitalized.

<a id="whitespace">White-space</a>
----------------------------------
### Indentation
Each level of indentation should be separated by four spaces. Never use tabs.

### Assignment
Include one space before and after the equality sign.

```
# Good
foo_bar = 5.9

# Bad
foo_bar=5.9
```

### Default Parameters
Default parameters for functions, on the other hand, should have no spacing 
before or after the equality sign.

```
#Good
foo_bar = function(x=TRUE, y=1.5) {
    ...
}

#Bad
foo_bar = function(x = FALSE, y= 1.4) {
    ...
}
```

### Brackets and Parens
Always include space between expressions and brackets; Add a single space
on outside of parentheses, but no extra space on the inside.

```
# Good
if (x == 5) {
    ...
} else {
    ...
}

# Bad
if( x == 5 ){
    ...
}
```

### Commas
Add one space after each comma.

```
# Good
foo(x, y)

# Bad
foo(x,y)
foo(x , y)
```

### Aligning variable assignments
Feel free to add extra indentation during indentifier assignment, when it
increases readability (PEP8 differs here).

```
# Good
x = 5.3
foobar = 2.9

# Also Good
x      = 5.3
foobar = 2.9
```

<a href='layout'>Layout</a>
---------------------------
Some more things not discussed in the whitespace section above.

### Conditional statements
If statements should always include brackets, the first of which should appear
on the same line. If an else statement is used, it should have a bracket on
either side. The closing bracket should be placed on a line of it's own.

```
# Good
if (x) {
    ....
} else {
    ....
}

# Bad
if (x)
{
    ....
}
else
{
    ....
}
```

### Single-line function declarations and conditional statements

Do not use them.

```
# Bad
if (x) print('hi')
if (x) { print('hi') }
foo = function() { print('bye') }
```



<a href='linewidth'>Line Width</a>
-----------------------------------
Lines should be 80 characters or less.

```
# Good
example = function(this, is, a, function, with, many, arguments, that, would,
                   go, over, eighty, characters)
```

<a href='assignment'>Assignment</a>
-----------------------------------
Always use equals signs for assignment.

```
# Good
x = 5

# Bad
x <- 5
```

<a href='semicolons'>Semicolons</a>
-----------------------------------
Do not use semicolons at the end of statements.

```r
# Good
x = 5

# Bad
x = 5;
```

<a href='filenames'>Filenames</a>
---------------------------------
Try and stick to lowercase filenames (.r, .rmd, .rdata, etc) and not their
capitalized counterparts (.R, .Rmd, .Rdata, etc).
