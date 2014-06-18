#### <a name="integer" href="#integer">.depth( *integer* )</a>

If you have specified nesting while setting your [[Unique ID]], then this method allows you to switch between those nesting levels. It accepts integer values that match the desired position in the nesting array.

For example, given the following nesting:

```js
.id( [ "country" , "state" , "city" ] )
```

You would show `"state"` aggregations by setting the depth as follows:

```js
.depth( 1 )
```
