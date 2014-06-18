#### <a name="boolean" href="#boolean">.messages( *boolean* )</a>

Displays status messages, telling the user what is happening behind the scenes as the visualization is being drawn/redrawn. Defaults to `true`.

#### <a name="string" href="#string">.messages( *string* )</a>

When passed a *string*, the specified *string* will be used for all messages. In this example, we want all messages displayed as `"Loading..."`:

`js
.messages( "Loading..." )
`

#### <a name="object" href="#object">.messages( *object* )</a>

This method supports passing a keyed *object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default Value |
| --- | --- | --- | --- |
| font | Sets information pertaining to the font used to render links. The following values can be set: "color", "decoration", "family", "size", "transform", "weight". | *object* | Default style |
| value | The key that gets set when you pass a *string* or *boolean* to the method. | *string*, *boolean* | `true` |
