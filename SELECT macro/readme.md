# SELECT Macro

A replacement for the native `<<choice>>` macro which runs code and appends content instead of navigating to passages.

&nbsp;

### Default behavior:
Clicking a link produced by the `<<select>>` macro replaces the link with its contents. It then removes all other links in the same group. The default group is 'default' but you can optionally specify a group as a second argument. Links in a group only remove other links in the same group as itself.

### Usage:
```html
<<select 'link text here' 'optional_group'>>
    ...link content here
<</select>>
<!-- Link text MUST be specified.
     optional_group is optional, defaults to 'default'. Only valid CSS characters accepted. -->
```
    
&nbsp;    

### Examples:
```html
:: Example_1
<!-- Selecting any one of these will remove the rest -->

<<select 'Take the left path.'>>
    You turned left.
<</select>>
<<select 'Take the right path.'>>
    You turned right.
<</select>>
<<select 'Take the center path.'>>
    You stayed the course.
<</select>>



:: Example_2
<!-- Selecting the 1st or 2nd link will remove ONLY the first two links,
     Selecting the 3rd or 4th link will remove ONLY the latter two links -->

<!-- Entree selection -->
<<select 'Order a burger.' 'entree'>>
    A savory burger. Normal, but delicious.
<</select>>
<<select 'Order the steak.' 'entree'>>
    A dry steak. Expensive because it wasn't you who cooked it.
<</select>>

<!-- Dessert selection -->
<<select 'Order a crème brûlée.' 'dessert'>>
    The thing you can't even spell properly. It was yummy nonetheless.
<</select>>
<<select 'Order ice cream.' 'dessert'>>
    Creamy ice cream. It's never a bad time for ice cream.
<</select>>

```
