# Trunk Club Sass Style Guide

While working on style rules.

- follow the [SUIT Naming Conventions](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md) for consistent naming
- use `rem` for defining relative sizes, otherwise use `px`
- style declarations should end with a semicolon, e.g. `opacity: 0;`
- style declarations should use curly braces and not be on one line, ~!e.g. `.mustachy { @extend .cf }`
- use `tc` namespace for SUIT styles in Static and `[app]` for app-specific stuff, e.g. `.count-ItemCard`
- when using decimal precision always ensure there's a number before the decimal point, e.g. `0.75rem`
