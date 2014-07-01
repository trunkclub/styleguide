# Trunk Club Backbone Style Guide

During usage of Backbone library.

- use the identifier `attrs` when passing in custom properties to classes, e.g. `initialize: (attrs) ->`
- ...with the exception of automatically bound properties, e.g. `model` and `collection` in `View`
- ensure prototype properties are passed in the options hash when creating new `model`s. For example: `elem = new Backbone.Model {}, { key: 'value' }` will let you do `elem.key # 'value'`. See the [Backbone docs](http://backbonejs.org/#Model-constructor) for more details.
- always return `@` (`this`) from `render` for chainability