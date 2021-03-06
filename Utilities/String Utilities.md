**d3plus** features Utilities that can be used to help with some common javascript *String* processes.

### <a name="format" href="#format">d3plus.string.format( *String* , parameters )</a>

Formats a string similar to how Python string formatting works. For example:

```js
d3plus.string.format( "Hi {0}, what is your favorite {1}?" , "Dave" , "food" )
```

This will return:

```js
"Hi Dave, what is your favorite food?"
```

### <a name="list" href="#list">d3plus.string.list( *Array* [, and, max, more] )</a>

Takes an array of strings and formats them into a list, separated by commas and the word "and". For example:

`````js
d3plus.string.list( [ "red" , "blue" , "green" ] )
`````

This returns:

`````js
"red, blue, and green"
`````

While this:

```js
d3plus.string.list( [ "red" , "blue" ] )
```

Returns this:

```js
"red and blue"
```

Optionally, you can specify your own *String* to be used as the "and" separator. This is useful when formatting text for localization.

Additionally, if you want the list to be truncated after a certain amount of items, with the addendum "and ### more", you can specificy both a max *integer* and a custom *String* for "more".

### <a name="strip" href="#strip">d3plus.string.strip( *String* )</a>

Returns the given *String* with all accented characters and punctuation removed. Great for creating file names. Take this example:

```js
var str = d3plus.util.strip("Nós amamos D3plus!")
```

The utility removes the accent mark over the "o", the exclamation point at the end, and replaces the spaces with underscores. The returned "str" variable looks like this:

```js
Nos_amamos_D3plus
```

### <a name="title" href="#title">d3plus.string.title( *String* [, key] )</a>

Formats the given string to titlecase if it is a phrase, or just capitalizes the first word if it is a sentence. It also accounts for "small" words, which are words (like "a" and "the") that should not be capitalized if they are not at the beginning of a sentence. Take this example:

```js
d3plus.string.title("click here for more info")
```

This would return the following string:

```js
"Click Here for More Info"
```
