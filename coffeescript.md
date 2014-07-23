# Trunk Club CoffeeScript Style Guide

When writing not JavaScript.

- use parens when requiring CommonJS modules, e.g. `require('lib/view-helper')`
- use single quotes for strings unless you're interpolating
- use `$` in identifier names when assigning a jQuery or Zepto wrapped element, e.g. `@$huzzah = @$('[data-spy="huzzah"]')`
- use ECMA Harmony DRY-style pattern matching, e.g. `new View {@collection, @container}` (see also: [destructuring assignments](http://coffeescript.org/#destructuring))
- avoid use of destructuring parameters as [suggested by Jeremy Ashkenas](https://github.com/jashkenas/coffee-script/issues/1607#issuecomment-3341285)
- always pass `evt` as the argument in the method signature when dealing with `event`s, e.g. `doSubmitBtnClicked: (evt) ->`
- achieve multiple inheritance using lo-dash/underscore `extend` method, e.g. `_.extend @prototype Mixin`
- prefer use of `function()` to `do function`, `&&` and `||` to `and` and `or`, and `==` to `is`
- use comprehensions over maps and loops to improve readability, e.g. `values = (encodeURIComponent value for value in list)`
- use double quotes around attribute selector values, e.g. `@$('[data-spy="tbotterson"]')`
- when naming custom events for the `mediator`, use simple `noun:verb` syntax, e.g. `scanner:activate`
- wrap object literals in curly braces when defining on a single line, e.g. `new View {@collection}` and not `new View collection: @collection`
- don't align `key:value` pairs in columns
- use meaningful variable names, e.g. `callback` and not `cb`
- method names should start with a verb denoting the action with which the method takes, e.g. `_getPrices`
