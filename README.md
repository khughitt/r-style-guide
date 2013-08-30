Keith's Style Guide for R Code
==============================
A coding standard for the [R programming language](http://www.r-project.org/), 
based on the [Style Guide for Python Code (PEP8)](http://www.python.org/dev/peps/pep-0008/Style Guide for Python Code).

Overview
--------

* [Identifiers](#identifiers): var_name, fxn_name, and ClassName
* [White-space](#whitespace): Indent = 4 spaces
* Line-width:  80 characters
* Assignment:  "=" and not "<-"
* No semi-colans
* Lower-case file names: .r, .rmd, etc.

<a id="identifiers">Identifiers</a>
-----------------------------------
**Variable names**
Lowercase characters with words separated by underscores, e.g. "my_var".

**Function names**
Same as above...

**Class names**
CamelCase -- No underscores, first letter of each word capitalized.

<a id="whitespace">White-space</a>
----------------------------------
**Indentation**
Each level of indentation should be separated by four spaces. Never use tabs.

**Assignment**
Include one space before and after the equality sign.

```
# Good
foo_bar = 5.9

# Bad
foo_bar=5.9
```

**Default Parameters**
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

**Brackets and Parens**
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

**Commas**
Add one space after each comma.

```
# Good
foo(x, y)

# Bad
foo(x,y)
foo(x , y)
```

**Aligning variable assignments**
Feel free to add extra indentation during indentifier assignment, when it
increases readability (PEP8 differs here).

```
# Good
x = 5.3
foo = 'bar'

# Also Good
x   = 5.3
foo = 'bar'
```
