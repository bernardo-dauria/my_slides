---
title: "A brief Markdown reference"
author: Bernardo D'Auria
date: February 20, 2019
variant: markdown+native_divs
---

% A brief Markdown reference
% Bernardo D'Auria
% February 20, 2019

# Headers

##  Setext-style headers

```markdown
A level-one header
==================

A level-two header
------------------
```

## ATX-style headers

```markdown
## A level-two header 

### A level-three header ###
```

# Block quotations

------------------

```markdown
> this is a block quote
> made of many lines
```
. . .

This _lazy_ way to write it gives the same result
```markdown
>  this is a block quote
   made of many lines
```

# Verbatim (code) blocks

------------------

Use 4 spaces or a tab to include a block text as it is.

```markdown
    > this is a block quote  
      made of many lines
```

. . .

Begin with a row of three or more tildes (`~`) and you get a _fenced_ code block.

```markdown
~~~~~~~
> this is a block quote  
  made of many lines
~~~~~~~
```

------------------

To highlight specific code formatting use:

````markdown
```r
x <- 1:10;
print("hello");
```
````

. . .

this is the result

```r
x <- 1:10;
print("hello");
```

# Columns

##  Lists

:::::::::::::: {.columns}
::: {.column width="40%"}
### Bullet list
* one
* two
* three
:::
::: {.column width="60%"}
### Ordered list
1. one
5. five
7. seven
:::
::::::::::::::