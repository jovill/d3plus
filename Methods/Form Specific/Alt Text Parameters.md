#### <a name="string" href="#wiki-string">.alt( *string* )</a>

Defines the value in your data associated with the alternative text of each element.

#### <a name="object" href="#wiki-object">.alt( *object* )</a>

As with some of the other methods, an *object* can be passed to this method. Here are the keys accessible by the user:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo). | **value**, *function*, *array* | ```[]``` |
| value | When passing only a *string* to this method, this is the variable that actually gets set. | *string*, *array* | ```"alt"``` |