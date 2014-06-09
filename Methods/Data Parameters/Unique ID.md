#### <a name="string" href="#string">.id( *string* )</a>

Defines the accessor key to be used as each data point's unique identifier. This is the key that **D3plus** will use when cross-referencing the data with all sources of data, such as [[Attribute Data]] and [[Geography Data]].

#### <a name="array" href="#array">.id( *array* )</a>

When passing an *array* to this method, **D3plus** will use each item in the *array* as a different level of nesting for the data. For example, if you were using data on cities, you could pass the following array of keys (given these keys are present in your data somewhere):

```js
.id( [ "state" , "county" , "city" ] )
```

In this case, if the current visualization supports nesting, the shapes in the visualization would be nested first by State, then by County, and finally by City. Each *string* in the *array* has to match a key in one of the defined data methods, usually the main [[Data Points]].

#### <a name="object" href="#object">.id( *object* )</a>

As with some of the other methods, an *object* can be passed to this method. Here are the keys accessible by the user:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | ```[]``` |
| value | Defines the accessor key to be used as each data point's unique identifier. When passing only a *string* or *array* to this method, this is the variable that actually gets set. | *string*, *array* | **visualization**:```"id"``` <br> **form**:```"value"``` |
