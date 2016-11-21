# jQuery

In HTML file:
```
<script type="text/javascript" src="script.js"></script>
```

A jQuery element looks like $(   ).  

Begin your script with
```
$(document).ready(function(){    });
```

### Actions
```
$('div').slideDown('slow');
$('div').mouseenter(function());
$('div').hide();
$('div').fadeTo('fast', 0.25);
$('div').mouseleave(function());
$('div').click();
```

### Variables 
```
var $p = $('p');
$('p, li').fadeTo('slow', 0);
```

### This
Refers to jQuery object you're currently interacting with
```
$('div').click(function {
    $(this).fadeOut('slow');});
```

### Creating HTML Elements
```
$p = $("<p>blah</p>");

$('a').append(e)
$('a').prepend(e)

$('target').after('<tag>To add</tag>');
$('target').before($('div') content );
$('target').empty();
$('target').remove();

$('selector').addClass('className');
$('selector').removeClass('className');
$('selector').toggleClass('className');
$('selector').height("50px");
$('selector').width("50px");

$('div').css('element': 'value');


$('div').hover(
    function() {
        $(this).addClass('highlight');
    };
    function() {
        $(this).removeClass('highlight');
    });
```
