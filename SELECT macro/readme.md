# SELECT Macro

***

A replacement for the native <<choice>> macro which runs code and appends content instead of navigating to passages.

## Default Behavior: 
Clicking a link produced by the <<select>> macro replaces the link with its contents. It then removes all other links in the same group. The default group is 'default' but you can optionally specify a group as a second argument. Links in a group only remove other links in the same group as itself.

***

### Examples:

```html
<<select 'Turn left'>>
    You turned left.
<</select>>
<<select 'Turn right'>>
    You turned right.
<</select>>
```

```html
<<times 5 '_var'>>
	_var : <<= setup.item.name>>
	<<set $inventory.push(setup.item)>>
<</times>>
```