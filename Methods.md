Visualizations, Forms, and Text Wrapping all have numerous methods that allow you to tweak values to get the perfect output that suits your needs.

Every method supports the following global behaviors in addition to their specific modifiers. In these examples, you would replace "**method**" with the specific name of the method you are invoking, such as "**id**" or "**data**".

---

### <a name="value" href="#value">.method( value )</a>

When passing a value to a method, the method's main value will be set as the value passed (if accepted by the method). The returned object will always be the **d3plus** element. This means that, when used correctly, every method is chainable.

---

### <a name="callback" href="#callback">.method( value , *Function* )</a>

Regardless of the type of data passed for the value, every method supports passing a *Function* as the second variable. This *Function* will be called whenever that method's value is set, whether internally by **d3plus** or externally by a user.

The *Function* will be passed the proposed new value for the method, and it is up to the *Function* to process the information.

If the *Function* returns a value, **d3plus** will use that new value instead of the one it had originally passed to the *Function*.

---

### <a name="undefined" href="#undefined">.method( )</a>

Without passing anything to a method, the return object will be the method's current value (unless the method supports an *undefined* value, such as [.draw()](Visualizations#draw)).

This is helpful when you need to extract data from the visualization, such as the [.focus( )](Visualizations#focus) of a [rings visualizations](Rings).

---

### <a name="Object" href="#Object">.method( Object )</a>

When you pass a method the literal constructor element for an *Object*, **d3plus** will return a keyed object with everything it is storing for that specific method.

This is helpful when needing to debug **d3plus**, as well as to give a better understanding of what's going on under the hood.
