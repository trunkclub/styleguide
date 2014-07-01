# Trunk Club Chaplin Style Guide

While using Chaplin on top of Backbone.

- when used, subviews should use the same model data, as suggested in the [Chaplin docs](http://docs.chaplinjs.org/chaplin.view.html)
- do not pollute the global namespace; instead expose application globals on the `mediator` before it's sealed
- set proper page titles with `@adjustTitle`, e.g. `@adjustTitle 'Shop Departments'`
- when declaring routes, do not use [named routes](http://docs.chaplinjs.org/chaplin.router.html)
- make healthy use of the `CollectionView` (there's a generator for that)
- use absolute `require` paths except when including templates and things that should move together
- use `attach` instead of overriding `render` whenever possible
- leverage the `listen` hash for `model`, `controller` and `mediator` events, use `listenTo` and `delegate` for `attrs` variety objects bound to backbone `initialize` and `ctor`
- when naming views, use `-collection-view`, `-item-view`, `-page-view` and `-subview` suffixes to denote view types
- use `adjustTitle` in controllers to adjust the page subtitle, e.g. `@adjustTitle 'Login'`
- do not modify "base" classes; instead, extend them for app-specific purposes
- when creating region hashes in Views, ensure key names are unique and values begin with `region-`