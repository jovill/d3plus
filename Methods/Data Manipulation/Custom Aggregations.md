#### <a name="object" href="#object">.aggs( *object* )</a>

Defines how specific values should be aggregated when the **D3plus** aggregates your data. The *object* passed should contain key/value pairs that match the keys in your data with the aggreagation value requested.

For example, if you wanted all values of the key "wage" to use D3's "mean" copmarator, then you would pass the following:

```js
.aggs( { "wage": "mean" } )
```

The *string* value passed with each key needs to be one of D3's predefined [array comparators](https://github.com/mbostock/d3/Arrays#d3_min), such as "mean", "median", "min", or "max". By default, all keys use [d3.sum()](https://github.com/mbostock/d3/Arrays#d3_sum).

Additionally, you can also pass a *function* as an aggregation method for a key. D3plus will pass the *function* the array of data objects needing aggregation, and the *function* should return the final aggregated value.
