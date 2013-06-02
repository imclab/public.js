### Public.js


This library analyzes JavaScript code and returns all the public interfaces exposed at runtime.


##Install

`npm install public.js`

Browser-based version may be available in the future.


##Example

```
var backboneStr = <string representation of backbone.js source>;
var underscoreStr = <string representation of underscore.js source>;

var output = publicjs.getPublic(backboneStr,{
        dependencies: [underscoreStr],
        tree: true
      });
```

In this example, publicjs will return a tree representing the global `Backbone` object exposed when Backbone.js is used.  This tree will list all the properties and functions exposed by the `Backbone` object.


##Applications

1. Automated unit test scaffolding: The tree returned by publicjs could be parsed and used to automatically create unit test cases based on the publically exposed functions.

2. Code security: Add publicjs to your build process to ensure that only the functionality that should be exposed publically by your code is, and that private functions are not accessible.

3. Code documentation: The interface tree could be parsed to automatically generate documentation for public methods.