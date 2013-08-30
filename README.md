Style Guide for R Code
======================
A coding standard for the [R programming language](http://www.r-project.org/), 
based on the [Style Guide for Python Code (PEP8)](http://www.python.org/dev/peps/pep-0008/Style Guide for Python Code).
The *structure* of this guide is based, in part, on [Google's style guide for R code](http://google-styleguide.googlecode.com/svn/trunk/Rguide.xml).

Overview
--------

* [Identifiers](#identifiers): var_name, fxn_name, ClassName
* [Indentation](#indentation): 4 spaces
* [Spacing](#spacing)
* [Layout](#layout)
* [Line-width](#linewidth): 80 characters
* [Assignment](#assignment): "=" and not "<-"
* [Semicolons](#semicolons): Don't.
* [File names](#filenames)
* [Comments](#comments)
* [Everything else...](#misc)

<a id="identifiers">Identifiers</a>
-----------------------------------
### Variable names
Lowercase characters with words separated by underscores. For all identifiers,
descriptive names should be used when possible.

```
# Good
read_length = 50

# Bad
readLength = 50
x = 50

### Function names
Same as above...

### Class names
CamelCase -- No underscores, first letter of each word capitalized.

### Constants
R doesn't have support for constants, but sometimes I like to pretend that it
does and THOSE_IDENTIFIERS_LOOK_LIKE_THIS.

<a id="indentation">Indentation</a>
----------------------------------
Each level of indentation should be separated by four spaces. Never use tabs.

<a href='spacing'>Spacing</a>
---------------------------

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

### Math expression
Include spaces before and after math operators.

```
# Good
(5 + 10) / 2.3 * pi

# Bad
(5+10)/2.3*pi
```

<a href='layout'>Layout</a>
---------------------------
Below are other general layout issues not discussed in the spacing section
above.

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
# Good
if (x) {
    print('hi')
}

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

```
# Good
x = 5

# Bad
x = 5;
```

<a href='filenames'>Filenames</a>
---------------------------------
Try and stick to lowercase filenames (.r, .rmd, .rdata, etc) and not their
capitalized counterparts (.R, .Rmd, .Rdata, etc).

<a href='comments'>Comments</a>
### Inline comments
Inline comments should always include a space after the pound sign.

```
# Good
x = 5 # Also Good

# You can also break up longer inline comments over multiple lines to make it
# more readable, and always do so when it would excede the 80-character limit
# otherwise.

#Bad
x = 5# Really bad
```
### File comments
File comments are strongly encouraged, and should include some information
about the contents of the file, the author(s) of the file, along with
contact information and possible external references.

Example file comment:

```
#
# Short Description
# Author: [Keith Hughitt](khughitt@umd.edu)
#  
# A longer description goes here. This may be a couple sentences, or a several
# paragraphs, depending on how complex the code is.
#
# See Also:
#   1. http://www.r-project.org/
#   2. https://github.com/khughitt/r-style-guide
#
```

### Function comments
I think [Google's description of R function comments](http://google-styleguide.googlecode.com/svn/trunk/Rguide.xml#comments)
is pretty good, and is fairly close to Python docstring comments combined 
geared towards parsing by [Sphinx](http://sphinx-doc.org/tutorial.html).

At a minimum, the **Arguments** and **Returns** fields should be included.
Additional fields which can be included when relevant include "Examples", 
"References" and "See Also".

Example function comment:

```
ones = function(m, n) {
    # Generates an mxn matrix filled with ones.
    #
    # A Longer description spanning multiple lines can be placed here when
    # appropriate...
    #
    # Parameters
    # ----------
    # m: numeric
    #   Number of rows to include
    # n: numeric
    #   Number of columns to include
    #
    # Examples
    # --------
    # x = ones(5, 5)
    #
    # See Also
    # --------
    # 1. http://docs.scipy.org/doc/numpy/reference/generated/numpy.ones.html
    # 2. http://rss.acs.unt.edu/Rdoc/library/calibrate/html/ones.html
    #
    # Returns
    # -------
    # An mxn matrix filled with ones.
    return(matrix(1, m, n))
}
```

<a href='misc'>Everything else...</a>
-------------------------------------
### Attach
Don't use attach() -- it can make the code less clear.

### .Rprofile
Don't use function aliases in your profile: they will reduce the portability
of your code.

Do specify (in comments, etc) any other profile tweaks which may affect the
output of your code.
