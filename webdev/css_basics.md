# CSS

Under <head> of your HTML file, add:
```
<link type="text/css" rel="stylesheet" href="stylesheet.css" />
```

### Syntax for CSS
```
selector {
    property: value;
}

CSS can apply style to all tags of the same kind.  

span {
    color: red;
}
```

### Comments
```
/* this is a comment */
```

### Backup font values
```
p {
    font-family: Tahoma, Verdana, sans-serif;
}
```

### Multiple selectors
```
div div h3 { } - selects any h3 with 2 divs above it
* { } - universal selector
div > p { } - any p with a direct parent div
```

### Class
Assign a class to HTML elements with
```
<div class="square">
```
and identify in CSS with a dot (.)  
```
.square { }
```

### ID
ID is good for one-ofs
```
<div id="first">

#first { }
```

### Pseudo-class selectors
A pseudo class is used to define a special state of an element
```
selector:pseudo-class {
    property: value;
}

/* visited link */
a:visited {
    color: #00FF00;
}
```

### Children
```
p:first-child { } - selects the first child
p:nth-child(n) { } - selects the nth child
```

### Display
```
block - element takes full width
inline-block - allows other elements next to it
inline - takes as much width as needed
none - content disappears
```

### Margin
```
auto - Equal left, right margins (centers element)
margin-top
margin-bottom
margin-right
margin-left

or: margin: TM RM BM LM
```

