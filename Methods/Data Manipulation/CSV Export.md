#### <a name="undefined" href="#wiki-undefined">.csv( )</a>

Downloads a .csv file of the currently displayed data to the user's computer.

If a [[title|Custom Titles#string]] is defined, it will use that for the filename (replacing spaces with hyphens). Otherwise, the file will be called "My-D3plus-App-Data.csv".

A javascript version of the data (an *array* of *arrays*) is also returned to javascript when this method is called.

#### <a name="array" href="#wiki-array">.csv( *string* | *array* )</a>

If an *string* or *array* of keys is passed the method, **D3plus** will return a .csv file with only the key(s) specified as the columns.
