#### <a name="array" href="#array">.attrs( *array* )</a>

Defines a set of data points that are associated with the primary [[Data Points]], but that do not change as the data changes.

For example, Attribute Data could include colors and names that are static throughout all [[Time]] while your [[Data Points]] include values that change over time.

The [[Unique ID]] that you set **MUST** be present inside of your attribute array, otherwise **D3plus** will have no way of matching attributes to data.

#### <a name="object" href="#object">.attrs( *object* )</a>

If it suits your needs, you may also pass an object keyed by each [[Unique ID]].

#### <a name="nested" href="#nested">.attrs( *nested attributes* )</a>

If your visualization uses nesting, you may want to pass a different attribute list for each nesting level. This can be achieved by passing an object that is keyed based on the nesting levels supplied to the [[Unique ID]] method.

#### <a name="url" href="#url">.attrs( *URL* )</a>

When passing a *URL* to this method, **D3plus** will use it to load the data dynamically for you.

If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).
