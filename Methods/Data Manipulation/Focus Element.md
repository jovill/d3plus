#### <a name="value" href="#value">.focus( value )</a>

If the visualization supports it, this defines which data node to focus on. For example, this sets the center node in [[Rings]]. The **value** passed much match a [[Unique ID]] in your data.

#### <a name="object" href="#object">.focus( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| tooltip | Whether or not to show the large tooltip on the right side of the visualization relating to the focus element. | *boolean* | ```true``` |
| value | The key that gets set when you only pass a *value* to the method. | *value*, ```false``` | ```false``` |
