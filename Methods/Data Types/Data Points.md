#### <a name="array" href="#array">.data( *array* )</a>

Sets the data associated with your visualization. Each item in the array needs to be an object with keys that match what you have defined using other methods. Here is a simple example of what your data array could look like:

```js
.data([
  { "id": "alpha", "size": 52 },
  { "id": "beta", "size": 23 }
])
```

#### <a name="object" href="#object">.data( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| donut | Sets styling for "donut" shapes. Currently supports passing a keyed *object* with a "size" parameter. | *object* | ```{ "size": 0.35 }``` |
| large | If the number of data nodes drawn on the screen exceeds this number, all transitions animations will be disabled. This is prevents lag and stuttering with large datasets. | *integer* | ```400``` |
| opacity | Sets default shape opacity. Currently supports passing a *float* between  ```0``` and ```1```. | *float* | ```0.9``` |
| stroke | Sets styling for a shape's outer stroke. Currently supports passing a keyed *object* with a "width" parameter. | *object* | ```{ "width": 1 }``` |
| value | When passing only an *array* to this method, this is the variable that actually gets set. | *array* | ```[]``` |

#### <a name="d3selection" href="#d3selection">.data( *D3 selection* | *DOM element* )</a>&nbsp;<sup>***new***</sup>

When passing a *D3 selection* or *DOM element* to the data method, **D3plus** will extract data from the element. This is currently only used when creating [[Forms]].

#### <a name="url" href="#url">.data( *URL* )</a>

When passing a *URL* to the data method, **D3plus** will use it to load the data dynamically for you.

If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).
