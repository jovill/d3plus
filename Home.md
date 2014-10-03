# <img src="http://d3plus.org/assets/img/d3plus-icon.png" width="50px"> Documentation

**d3plus** is an extension to the **D3** library that allows fast and easy creation of data visualizations. [Click here](http://www.d3plus.org/examples/) to view live examples of all of the various things **d3plus** can do.

## [Visualizations](Visualizations)

The crux of **d3plus** is it's easy-to-use visualizations. By passing your data and setting a few methods that describe your data, **d3plus** effortlessly creates interactive visualizations to help your explore your data. You get a lot for free here: nesting, tooltips, timelines, legends, just to name a few. Here are the visualizations currently supported by **d3plus**:

| Tree Map | Scatter Plot | Stacked Area | Line Plot |
| :-: | :-: | :-: | :-: |
| <a href="http://d3plus.org/examples/basic/9029130/"><img src="https://gist.githubusercontent.com/davelandry/9029130/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9029781/"><img src="https://gist.githubusercontent.com/davelandry/9029781/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9029462/"><img src="https://gist.githubusercontent.com/davelandry/9029462/raw/thumbnail.png" width="100px"><br>Example</a> |<a href="http://d3plus.org/examples/basic/9037371/"><img src="https://gist.githubusercontent.com/davelandry/9037371/raw/thumbnail.png" width="100px"><br>Example</a> |
| [Documentation](Tree Map) | [Documentation](Scatter Plot) | [Documentation](Stacked Area) | [Documentation](Line Plot) |

| Network | Rings | Geo Map |
| :-: | :-: | :-: |
| <a href="http://d3plus.org/examples/basic/9042919/"><img src="https://gist.githubusercontent.com/davelandry/9042919/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9034389/"><img src="https://gist.githubusercontent.com/davelandry/9034389/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9042807/"><img src="https://gist.githubusercontent.com/davelandry/9042807/raw/thumbnail.png" width="100px"><br>Example</a> |
| [Documentation](Network) | [Documentation](Rings) | [Documentation](Geo Map) |

## [SVG Text Wrapping](Text Wrapping)

SVG does not natively support wrapping text. Because of this, we created our own solution to break lines of SVG text at appropriate points, while also allowing the text to resize to fit the available space (if desired). Here is an example page showing how to wrap and resize SVG text in both rectangles and circles:

| SVG Text Wrapping |
| :-: |
| <a href="http://d3plus.org/examples/utilities/a39f0c3fc52804ee859a/"><img src="https://gist.githubusercontent.com/davelandry/a39f0c3fc52804ee859a/raw/thumbnail.png" width="100px"></a> |

#### Available Methods
* [.resize( )](Text Wrapping#resize)
* [.shape( )](Text Wrapping#shape)
* [.text( )](Text Wrapping#text)
* [*...and 6 more*](Text Wrapping)

## [Forms](Forms)

**d3plus** includes advanced, cross-browser form styling and behavior that helps make normal HTML forms beautiful and reliable. Here are the supported form types:

* Buttons
* Dropdown Menus
* Radio Toggles
* Auto Detect

[Click here](Forms) to learn more about forms, and to see all of the available methods. Here are some example usages:

| Converting Existing HTML Forms | Creating Forms from Javascript | Using Forms in Visualizations | Forms with Nested Data |
| :-: | :-: | :-: | :-: |
| <a href="http://d3plus.org/examples/forms/62d1df2506fd7c73b4c6/"><img src="https://gist.githubusercontent.com/davelandry/62d1df2506fd7c73b4c6/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/forms/8ea69aa2266c39d35380/"><img src="https://gist.githubusercontent.com/davelandry/8ea69aa2266c39d35380/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/basic/2ce67895efd23771943b/"><img src="https://gist.githubusercontent.com/davelandry/2ce67895efd23771943b/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/forms/55bbd9665eb1a8019c68/"><img src="https://gist.githubusercontent.com/davelandry/55bbd9665eb1a8019c68/raw/thumbnail.png" width="100px"></a> |

## [Utilities](Utilities)

As **d3plus** is developed, any simple functions that could be used publicly are made available for everyone to use. They are grouped into categories based on the type of data that they manipulate, and here are the categories:

* [Arrays](Array Utilities)
* [Client Browser](Client Utilities)
* [Colors](Color Utilities)
* [Fonts](Font Utilities)
* [Geometry](Geometry Utilities)
* [Miscellaneous](Basic Utilities)
* [Networks](Network Utilities)
* [Numbers](Number Utilities)
* [Objects](Color Utilities)
* [Strings](String Utilities)

Here are some `d3plus.color` examples:

| Legible Text on<br>Colored Backgrounds | Legible Text on<br>White Backgrounds | Lighten Colors |
| :-: | :-: | :-: |
| <a href="http://d3plus.org/examples/utilities/20a9042a60d87616e9ea/"><img src="https://gist.githubusercontent.com/davelandry/20a9042a60d87616e9ea/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/utilities/b3063df74711f4e69166/"><img src="https://gist.githubusercontent.com/davelandry/b3063df74711f4e69166/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/utilities/53696917e5fd0964f91e/"><img src="https://gist.githubusercontent.com/davelandry/53696917e5fd0964f91e/raw/thumbnail.png" width="100px"></a> |
