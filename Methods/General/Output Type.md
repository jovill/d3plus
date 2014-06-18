#### <a name="string" href="#string">.type( *string* )</a>

Sets the current output type.

#### <a name="object" href="#object">.type( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mode | Sets the "mode" for the current visualization. Currently only used in [[Tree Map]]. | `"squarify"`, `"slice"`, `"dice"`, `"slice-dice"` | `"squarify"`|
| value | What actually gets set when you only pass a *string* to the method. | **visualizations**:`"bubbles"`, `"chart"`, `"geo_map"`, `"line"`, `"network"`, `"rings"`, `"scatter"`, `"stacked"`, `"tree_map"` <br> **forms**:`"auto"`, `"button"`, `"drop"`, `"toggle"` | **visualization**:`"tree_map"` <br> **form**:`"auto"` |
