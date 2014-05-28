#### <a name="string" href="#wiki-string">.format( *string* )</a>

Passing a *string* to the method changes the current locale used to display text and numbers.

#### <a name="function" href="#wiki-function">.format( *function* )</a>

Passing a *function* overrides the default behavior, which tests whether a value is a *string* or a *number*, and then passes it through the correct formatting function. It is not recommended that you change this *function*, but rather edit the specific text and number functions in the object, as seen below.

#### <a name="object" href="#wiki-object">.format( *object* )</a>

This method also supports passing a keyed *object*. This is what gives you access to the specific text and number formatting functions. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| locale | When passing only a *string* to the method, this is the variable that actually gets set. | *string* | ```"en_US"``` |
| number | The function that formats all *number* values displayed on the screen. <br><br> This is helpful when you would like specific variables to always be formatted a certain way, whether it's to a certain decimal place or replacing commas with periods for international usage. **D3plus** passes 2 variables to the function you provide: the number that needs to be formatted, and the key associated with that number. | *function* | Custom formatting function. |
| text | The function that formats all *string* values displayed on the screen. <br><br> This is helpful for displaying certain short javascript keys as their full capitalized names, and also enables you to implement full localization for your visualizations. **D3plus** passes 2 variables to the function you provide: the *string* that needs to be formatted, and the key associated with that *string*. | *function* | Custom formatting function. |
| value | When passing only a *function* to the method, this is the variable that actually gets set. | *function* | Custom formatting function. |

Say for instance, you wanted all numbers for the key "year" to return as-is, and all other numbers formatted to 2 decimal places. You would pass the following *function* to the "number" key:

```js
.format({ "number" : function( number , key ) {

    if (key === "year") {
      return number;
    }
    else {
      return d3.round(number,2);
    }

  }
})
```

In addition, if you wanted to display the key "export_val" as "Export Value" and capitalize all other strings. You would pass the following function to the text key:

```js
.format({ "text" : function( text , key ) {

    if (key === "export_val") {
      return "Export Value";
    }
    else {
      return text.charAt(0).toUpperCase() + text.substr(1).toLowerCase();
    }

  }
})
```
