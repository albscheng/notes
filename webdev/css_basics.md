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

### Padding
```
Padding is the space between the border and content
padding: TP RP BP LP;
```

### Float
```
Positions element, avoiding collision with other floating elements
float: right
```

### Clear
```
Moves element clear of any floating elements
clear: right/left/both
```

### Absolute Positioning
``` 
Position relative to an element that doesn't have position: static
Otherwise, relative to <html>
```

### Relative Positioning
```
Moves from where it would normally be
position: relative
```

### Fixed Positioning
```
Anchors to page, even with scrolling
```

### Z-Index
```
The higher the z-index, the higher the priority (overlap others)
```

### Grouping Selectors
```
h2, .class1, .class2 {
    ...
}
```

### Shorthand Border
```
border: 1px red solid
```

### Shorthand Font
```
font: italic bold 12px/2 courier;
```

### Shorthand Background
```
background: background-color -image -repeat -position
```


