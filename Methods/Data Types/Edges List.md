#### <a name="array" href="#wiki-array">.edges( *array* )</a>

Sets the list of edges between objects for visualizations that require edges (such as [[Network]] and [[Rings]]). The *array* passed to this method must be in the following format, with the "source" and "target" matching the [[Unique ID]] value.

```js
.edges([
  {
    "source": 1,
    "target": 2
  },
  {
    "source": 3,
    "target": 1
  }
])
```

#### <a name="object" href="#wiki-object">.edges( *object* )</a>

This method also supports passing an *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| arrows | Determines whether or not arrows should be drawn at the end of each link.<br><br>When passing a *boolean*, the arrows will be toggled on/off with a default width of ```10``` pixels.<br><br>When passing a *number*, that number will be used as the width of the arrow.<br><br>When passing an *object*, the user can define both the "value" (which is what gets set when not passing an *object*) and the "direction" of the arrows, which is either ```"source"``` or ```"target"``` (defaults to ```"target"```) | *boolean*, *number*, *object* | ```false``` |
| color | The color of each edge. | *color* | ```"#d0d0d0"``` |
| label | Value within each edge object to be used as a label for the connection. | *string*, ```false``` | ```false``` |
| large | The cutoff for a "large" network. When there are more than this number of edges displayed on screen, certain transitions and styles will be disabled because it becomes too computationally heavy to modify the large amount of edges on the fly (for example, when highlighting specific connections on hover). | *integer* | ```100``` |
| limit | Limits the number of primary connections to be shown. | *integer*, ```false``` | ```false``` |
| opacity | Sets default link opacity. Currently supports passing a *float* between  ```0``` and ```1```. | *float* | ```1``` |
| size | Value within each link object to be used to size the stroke width of the connection. | *string*, ```false``` | ```false``` |
| source | Sets the key associated with the edge "source". | *string* | ```"source"``` |
| target | Sets the key associated with the edge "target". | *string* | ```"target"``` |
| value | When passing only an *array* to this method, this is the variable that actually gets set. | *array* | ```false``` |
| width | *number* that represents the stroke-width of each link. | *number* | ```1``` |

#### <a name="url" href="#wiki-url">.edges( *URL* )</a>

When passing a *URL* to this method, **D3plus** will use it to load the data dynamically for you.

If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).
