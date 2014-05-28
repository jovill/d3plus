#### <a name="array" href="#wiki-array">.nodes( *array* )</a>

Sets a lookup object that contains "x" and "y" coordinates for each data point to be used in the [[Network]]. The *array* passed must be in the following format, with each node containing a key/value pair that matches our [[Unique ID]]. In this example, our [[Unique ID]] is set to ```"city"```.

```js
.nodes([
  {
    "x": 255.3,
    "y": 365.7,
    "city": 1
  },
  {
    "x": 954.2,
    "y": 476.5,
    "city": 2
  }
])
```

#### <a name="object" href="#wiki-object">.nodes( *object* )</a>

This method also supports passing an *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| overlap&nbsp;<sup>***new***</sup> | A value, between ```0``` and ```1``` which dictates the percentage between the closest nodes that a node's radius shold extent. <br><br>For example, to insure that all nodes never overlap, this value should be set to ```0.5```. The default value is slightly higher than this, because when sizing nodes, the 2 closest nodes usually do not share the largest radius. | *number* | ```0.6``` |
| value | When passing only an *array* to this method, this is the variable that actually gets set. | *array* | ```false``` |

#### <a name="url" href="#wiki-url">.nodes( *URL* )</a>

When passing a *URL* to this method, **D3plus** will use it to load the data dynamically for you.

If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).
