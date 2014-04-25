# Trunk Club Sass Style Guide

- use [SUIT code style](https://github.com/suitcss/suit/blob/master/doc/code-style.md#4-css) and refactor from `application.scss` into [Static](https://github.com/trunkclub/static) when it makes sense (i.e. almost always)
- use `rem` for defining relative sizes, otherwise use `px`
- style declarations should end with a semicolon, e.g. `opacity: 0;`
- style declarations should use curly braces and not be on one line, ~!e.g. `.mustachy { @extend .cf }`
- use `tc` namespace for SUIT styles in Static and `[app]` for app-specific stuff, e.g. `.count-ItemCard`
- when using decimal precision always ensure there's a number before the decimal point, e.g. `0.75rem`