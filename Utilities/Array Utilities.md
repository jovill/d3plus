**D3plus** features a set of methods that relate to various array properties. These methods may be used outside of the normal constraints of the visualizations.

#### <a name="update" href="#update">d3plus.array.update( *array* , *value* )</a>

This function will check to see if the *value* passed is present in the *array* passed, remove it if it is present and append it if it is not present.

If the *value* passed is an *array*, the *value* will completely overwrite the *array* passed.

The return object is the new, updated *array*.
