**d3plus** features a set of utilities that relate to various array properties. These methods may be used outside of the normal constraints of the visualizations.

### <a name="comparator" href="#comparator">d3plus.array.comparator( *a* , *b* , *keys* [, *sort* , *colors*] )</a>

An advanced sort comparator that evaluates objects using specified *keys*. *a* and *b* should both be objects, and *keys* is either a single key to compare, or an array of *keys* to use as fallbacks.

In addition, a *sort* order can be supplied (`"asc"` or `"desc"`), along with any keys that might be color values, which would allow rainbow sorting of their values.

### <a name="contains" href="#contains">d3plus.array.contains( *Array* , *value* )</a>

Returns a *Boolean* whether or not the *value* exists inside of the *Array*. In addition to just testing equality, the *Array* passed may contain *constructors* to evaluate against. That means that the following would return true:

```js
d3plus.array.contains([Array, Number], 13)
```

### <a name="sort" href="#sort">d3plus.array.sort( *Array* , *keys* [, *sort* , *colors*] )</a>

An advanced array sorter that evaluates an array of objects using specified *keys*. *keys* is either a single key to compare, or an array of *keys* to use as fallbacks.

In addition, a *sort* order can be supplied (`"asc"` or `"desc"`), along with any keys that might be color values, which would allow rainbow sorting of their values.

### <a name="update" href="#update">d3plus.array.update( *Array* , *value* )</a>

This function will check to see if the *value* passed is present in the *Array* passed, remove it if it is present and append it if it is not present. If the *value* passed is an *Array*, the *value* will completely overwrite the *Array* passed.

The return object is the new, updated *Array*.
