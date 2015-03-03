# Trunk Club React Styleguide

This guide assumes that you are writing in the coffeescript-flavor of [JSX](https://github.com/jsdf/coffee-react-transform). It also assumes that you have a cursory understanding of what JSX is and why React uses it. See the [docs](http://facebook.github.io/react/docs/jsx-in-depth.html) for more details.

## Structure of React Components
You should structure your React Components like this to ensure consistency. Whether you're using ECMAScript 6 syntax, plain Javascript, or Coffeescript, it should be ordered like this

1. Attributes
  1. If you are using a mixin that requires you to specify an attribute on the Component's prototype (and not on the instance itself), do that here as well

  ```Coffeescript
  ComponentName = React.createClass
    displayName: 'ComponentName'
    mixins: []
    statics: {}
    propTypes: {}
    listen: {} # Custom attribute needed by a mixin
  ```

2. React lifecycle hooks

  ```Coffeescript
  getInitialState: -> {}
  componentWillMount: ->
  componentDidMount: ->
  componentWillReceiveProps: (nextProps) ->
  shouldComponentUpdate: (nextProps, nextState) -> true
  componentWillUpdate: (nextProps, nextState) ->
  componentDidUpdate: (prevProps, prevState) ->
  ```

3. Event handlers

  ```Coffeescript
  handleClickBtn: (evt) -> # handle(EventType)(SourceItem)
  ```

4. Helper methods for making chunks of UI

  ```CoffeeScript
  makeListOfItems: ->
    @state.items.map (item, index) -> <li key={index}>{item}</li>
  ```

5. `render()`

  ```CoffeeScript
  render: ->
    <span>{@makeListOfItems()}</span>
  ```

## Code style
1. Make sure that you are returning a single root element inside of `render()`

  ```CoffeeScript
  ###
  BAD EXAMPLE:
  -----------
  This example will function as expected due to the way that coffeescript compiles.
  
  The last token in a scope will be returned, which means that the last compiled JSX
  node (the `<div>`) will be returned, and the first one will not.
  ###
  render: ->
    <div>Here is some content</div>
    <div>
      <p>Here is some more</p>
    </div>

  # GOOD EXAMPLE:
  render: ->
    <section>
      <header>
        <nav>Here is the navigation</nav>
      </header>
      <div>
        <p>Here is the first text on the page!</p>
      </div>
    </section>
  ```

2. If your component looks untidy OR has >5 props defined on it, move each prop to a new line

  ```CoffeeScript
  # Good
  render: ->
    <span>
      <ComponentName a={@state.a} b={@state.b} />
    </span>

  # Good-ish. It's getting messy. Consider breaking them into different lines
  render: ->
    <span>
      <ComponentName a={@state.a} b={@state.b} c={@state.c} d={@state.d} />
    </span>

  # Good; note how the termination of the null component is on its own line
  render: ->
    <span>
      <ComponentName
        a={@state.a}
        b={@state.b}
        c={@state.c}
        d={@state.d}
        e={@state.e}
        f={@state.f}
      />
    </span>

  # Good; note how the termination of the component with `children` is on the same line
  # as the last prop
  render: ->
    <span>
      <ComponentName
        someLongVariableNameThatNeedsToBeThisLong={@props.someLongVariableNameThatNeedsToBeThisLong}
        otherStuff={@props.otherStuff}
        thing={@state.thing}>
        <span>Inner content!</span>
      </ComponentName>
    </span>
  ```

3. Keep one space before the termination of a void component (one that does not have `children`)

  ```CoffeeScript
  <ComponentName x={@state.x} /> # Good
  <ComponentName x={@state.x}/> # Bad
  ```

4. Wrap all inline object literals in curly braces

  ```CoffeeScript
  <ComponentName x={y: 5} /> # Bad
  <ComponentName x={{y: 5}} /> # Good
  ```

5. If you are implicitly passing down `props` or `state`, use the Spread operator:

  ```CoffeeScript
  # @state = {x: 5, y: 6, z: 7}
  <ComponentName {...@state} /> # Then you can call `@prop.x` inside of `ComponentName`
  ```

6. Use multi-line if-statements wherever possible

  ```CoffeeScript
  render: ->
    text =
      if @state.isVisible
        <span>Or this is alright, too</span>
    <span>
      {text} 
      {if @state.isVisible then <h1>Show this</h1>} # Good, since it's short
      {if @state.isVisible then <p><strong>Bold first word</strong> and regular 
       elsewhere</p>} # Bad, because it's not short
      {if @state.isVisible then {@state.text}} # Good, since it's short (and a variable)
      {if @state.isVisible
        <p><strong>Bold first word</strong> and regular stuff elsewhere</p>
      } # Good, since it's long
    </span>
  ```

7. If you have multiple mixins, define each one on a new line:

  ```CoffeeScript
  SomeComponent = React.createClass
    mixins: [
      MixinOne
      MixinTwo
    ]

  OtherComponent = React.createClass
    mixins: [OnlyMixin] # this is fine, since there is only one mixin here
  ```

8. Remember to `key` like elements that appear in arrays
  1. Any adjacent React Components are represented by arrays of elements.
  2. This is to provide React with the information to hueristically optimize UI reconciliation (figuring out what to re-render and what not to)

  ```CoffeeScript
  render: ->
    <div>
      <p key={1}>Some text</p>
      <p key={2}>Some other text</p>
      <p key={3}>Some more text</p>
    </div>

  makeItem: (item, index) ->
    <p key={index}>{item}</p> # `map`-ing over the elements
                              # lets you use the index of the item
                              # in the array as a key.
                              # 
                              # `key` just has to be unique in the array,
                              # it doesn't have to be unique across the page.
                              #
                              # If you are constantly re-sorting items in the
                              # array, try to use the resource's ID. If not,
                              # using the index of the element in the source array works
  render: ->
    <div>
      {@state.items.map(@makeItem)}
    </div>
  ```

9. Use expressions to iterate over datasets & render components
  1. `map`, `filter`, `concat`, etc.
  2. Lodash/underscore methods work as well (`where`, `reject`, `pluck`, etc.)

  ```Coffeescript
  ###
  @props.items = [1,2,3,4,5]
  ###

  # Good example
  showEvenItems: (item, index) ->
    item % 2 == 0
  makeItem: (item, index) ->
    <li key={item.database_id}>{item}</li>
  render: ->
    <ul>
      {@props.items.filter(@showEvenItems).map(@makeItem)}
    </ul>

  # Bad example
  # This works, and is actually faster, but using functional expressions helps
  # to abstract the idea of iteration. Most paradigms in JS applications can be expressed
  # and manipulated with `map` or `filter`, so these functions help to ensure a common
  # "language" for dealing with sets of information
  makeItems: ->
    for item in @props.items
      if item % 2 == 0
        <li key={item.database_id}>{item}</li>
  render: ->
    <ul>
      {@makeItems()}
    </ul>
  ```
  
10. Don't use `class` when setting classes on an element
  1. Use `className` instead. React will warn you about this one
  2. You can also use `React.addons`'s `classSet` to conditionally set classes
  3. `itemClasses = classSet({'ComponentName': true, 'is-disabled': @state.isDisabled})`
11. Always use `setState` to change the value of a Component's `state`
12. No need to define Component-private methods with `_` prefixes.
  1. Methods attached to the Component are private by default (and auto-bound to `this`)