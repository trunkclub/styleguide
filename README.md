Trunk Club Code Style Guide
==========

## Table of Contents

1. [The Golden Rule](#golden-rule)
2. [In General](#in-general)
3. [Whitespace](#whitespace)
4. [Guides by Language](#guides-by-language)
5. [CSS](#css)
  * [Whitespace](#css-whitespace)
  * [Comments](#css-comments)
  * [Format](#css-format)
  * [Practical Example](#css-example)
6. [HTML](#html)
  * [Whitespace](#html-whitespace)
  * [Format](#html-format)
  * [Naming](#html-naming)
  * [Practical Example](#html-example)
8. [License](#license)

<a name="golden-rule"></a>
## 1. The Golden Rule

All code in the codebase should look like a single person typed it, no matter how many people contribute.

<a name="in-general"></a>
## 2. In General

- do not commit commented-out code to master
- don’t leave `TODO`s, `FIXME`s or `BUG`s in the code, but if you do use `TODO`, `FIXME` or `BUG` in your comment
- comments left in the code should be timeless, e.g. always applicable until they’re removed

<a name="whitespace"></a>
## 3. Whitespace

* Use whitespace to improve readability.
* Use two spaces for indentation.
* In general, don’t use more than one blank line as a separator.
* Strip all end-of-line whitespace.
* Ensure file ends with one line-break.

<a name="guides-by-language"></a>
## 4. Guides by Language

- [CoffeeScript](coffeescript.md)
- [JavaScript](javascript.md)
- [Backbone](backbone.md)
- [Chaplin](chaplin.md)
- [Sass](sass.md)

<a name="css"></a>
## 5. CSS

<a name="css-whitespace"></a>
### 5.1 CSS Whitespace

* Use whitespace to improve readability.
* Use two spaces for indentation.
* Don’t use more than one blank line as a separator.
* Strip all end-of-line whitespace.
* Ensure file ends with one line-break.

<a name="css-comments"></a>
### 5.2. CSS Comments

Well commented code is extremely important. Take time to describe components,
how they work, their limitations, and the way they are constructed. Don’t leave
others in the team guessing as to the purpose of uncommon or non-obvious
code.

Comment style should be simple and consistent within a single code base.

* Place comments on a new line above their subject.
* Keep line-length to a sensible maximum, e.g., 80 columns.
* Make liberal use of comments to break CSS code into discrete sections.
* Use “sentence case” comments and consistent text indentation.
* Use numeric end-of-line comments to reference documentation for individual declarations.

Tip: configure your editor to provide you with shortcuts to output agreed-upon
comment patterns.

Example:

```css
/* Section comment block
   ========================================================================== */

/**
 * Short description using Doxygen-style comment format
 *
 * The first sentence of the long description starts here and continues on this
 * line for a while finally concluding here at the end of this paragraph.
 *
 * The long description is ideal for more detailed explanations and
 * documentation. It can include example HTML, URLs, or any other information
 * that is deemed necessary or useful.
 *
 * TODO: This is a todo statement that describes an atomic task to be completed
 *   at a later date. It wraps after 80 characters and following lines are
 *   indented by two spaces.
 *
 * @tag This is a tag named ‘tag’
 *
 * 1. A helpful description of a declaration’s purpose.
 * 2. Another declaration or collection of declarations can reference this
 *    comment with an inline comment corresponding to the lists number.
 */

/* Basic comment */
```

<a name="css-format"></a>
### 5.3. CSS Format

The chosen code format ensures that code is: easy to read; easy to clearly
comment; minimizes the chance of accidentally introducing errors; and results
in useful diffs and blames.

* Use one discrete selector per line in multi-selector rulesets.
* Include a single space before the opening brace of a ruleset.
* Include one declaration per line in a declaration block.
* Use one level of indentation for each declaration.
* Include a single space after the colon of a declaration.
* Use lowercase and shorthand hex values, e.g., `#aaa`.
* Use single or double quotes consistently. Preference is for double quotes,
  e.g., `content: ""`.
* Quote attribute values in selectors, e.g., `input[type="checkbox"]`.
* _Where allowed_, avoid specifying units for zero-values, e.g., `margin: 0`.
* Include a space after each comma in comma-separated property or function
  values.
* Include a semi-colon at the end of the last declaration in a declaration
  block.
* Place the closing brace of a ruleset in the same column as the first
  character of the ruleset.
* Separate each ruleset by a blank line.

```css
.selector-1,
.selector-2,
.selector-3[type="text"] {
  background: #fff;
  background: linear-gradient(#fff, rgba(0, 0, 0, 0.8));
  box-sizing: border-box;
  color: #333;
  display: block;
  font-family: helvetica, arial, sans-serif;
}

.selector-a,
.selector-b {
  padding: 10px;
}
```

#### Declaration order

Use alphabetical ordering of declarations unless the cascade absolutely
requires otherwise.

```css
.selector {
  background: #000;
  border: 10px solid #333;
  box-sizing: border-box;
  color: #fff;
  display: inline-block;
  font-family: sans-serif;
  font-size: 16px;
  text-align: right;
  width: 100%;
}
```

#### Exceptions and slight deviations

Large blocks of single declarations can use a slightly different, single-line
format. In this case, a space should be included after the opening brace and
before the closing brace.

```css
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Long, comma-separated property values - such as collections of gradients or
shadows - can be arranged across multiple lines in an effort to improve
readability and produce more useful diffs.

```css
.selector {
  background-image:
    linear-gradient(#fff, #ccc),
    linear-gradient(#f3c, #4ec);
  box-shadow:
    1px 1px 1px #000,
    2px 2px 1px 1px #ccc inset;
}
```

<a name="css-example"></a>
### 5.4. CSS Practical example

An example of various conventions.

```css
/** @define Grid */

/**
 * Column layout with horizontal scroll.
 *
 * This creates a single row of full-height, non-wrapping columns that can
 * be browsed horizontally within their parent.
 *
 * Example HTML:
 *
 * <div class="Grid">
 *   <div class="Grid-cell Grid-cell--3"></div>
 *   <div class="Grid-cell Grid-cell--3"></div>
 *   <div class="Grid-cell Grid-cell--3"></div>
 * </div>
 */

/**
 * Grid container
 *
 * Must only contain `.Grid-cell` children.
 *
 * 1. Remove inter-cell whitespace
 * 2. Prevent inline-block cells wrapping
 */

.Grid {
  font-size: 0; /* 1 */
  height: 100%;
  white-space: nowrap; /* 2 */
}

/**
 * Grid cells
 *
 * No explicit width by default. Extend with `.Grid-cell--n` classes.
 *
 * 1. Reset font-size inherited from `.Grid`
 * 2. Set the inter-cell spacing
 * 3. Reset white-space inherited from `.Grid`
 */

.Grid-cell {
  border: 2px solid #333;
  box-sizing: border-box;
  display: inline-block;
  font-size: 1rem; /* 1 */
  height: 100%;
  overflow: hidden;
  padding: 0 10px; /* 2 */
  position: relative;
  vertical-align: top;
  white-space: normal; /* 3 */
}

/* Cell states */

.Grid-cell.is-animating {
  background-color: #fffdec;
}

/* Cell dimension modifiers
   ========================================================================== */

.Grid-cell--1 { width: 10%; }
.Grid-cell--2 { width: 20%; }
.Grid-cell--3 { width: 30%; }
.Grid-cell--4 { width: 40%; }
.Grid-cell--5 { width: 50%; }

/* Cell modifiers
   ========================================================================== */

.Grid-cell--detail,
.Grid-cell--important {
  border-width: 4px;
}
```

Based extensively on work at [github.com/suitcss/suit](https://github.com/suitcss/suit/blob/master/doc/STYLE.md) and [github.com/necolas/idiomatic-css](https://github.com/necolas/idiomatic-css/blob/master/README.md).

<a name="html"></a>
## 6. HTML

<a name="html-whitespace"></a>
### 6.1. HTML Whitespace

* Use whitespace to improve readability.
* Use two spaces for indentation.
* Don’t use more than one blank line as a separator.
* Strip all end-of-line whitespace.
* Ensure file ends with one line-break.

<a name="html-format"></a>
### 6.2. HTML Format

* Use semantic markup, e.g. use `button` and not `href` for “Close” links; see
  also [content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories).
* Always use lowercase tag and attribute names.
* Write one discrete, block-level element per line.
* Use one additional level of indentation for each nested block-level element.
* Use valueless boolean attributes (e.g. `checked` rather than `checked="checked"`).
* Always use double quotes to quote attribute values.
* Use the `id` attribute only for the DOM-insertion of content containers (e.g. layout areas, regions), form controls.
* Use the [`alt` text decision tree](http://dev.w3.org/html5/alt-techniques/#tree) when adding `img` elements.
* Include the `type` attribute for all `button` elements, using a value of `button`, `reset`, or `submit` where appropriate.
* Omit the `type` attributes from `link` stylesheet, `style` and `script` elements.
* Omit the `/` on [void elements](http://www.456bereastreet.com/archive/201005/void_empty_elements_and_self-closing_start_tags_in_html/), e.g. `<hr>` and not `<hr />` ([further reading](http://www.colorglare.com/2014/02/03/to-close-or-not-to-close.html)).
* Avoid use of the `<br>` tag; consider possible use of other semantic markup instead.
* Do not use classless `span` or `div` tags wrapped around content.
* Do not use the `style` attribute; use `class` instead.
* Always include closing tags.

(Keep line-length to a sensible maximum, e.g., 80 columns.)

Example:

```html
<div class="Tweet">
  <a href="{{url}}">
    <img src="{{avatar}}" alt="">
  </a>
  <p>{{text}}</p>
  <button disabled type="button">Reply</button>
</div>
```

<a name="html-naming"></a>
### 6.4. HTML Naming

Naming is hard, but very important. It's a crucial part of the process of
developing a maintainable code base. Don't be afraid to rename components.

* Use clear, thoughtful, and appropriate names for HTML classes. The names
  should be informative both within HTML and CSS files.
* Avoid _systematic_ use of abbreviated class names. Don't make things
  difficult to understand.

Example with “bad” names:

```html
<div class="cb s-scr"></div>
```

```css
.cb {
  background: #000;
}

.cb.s-scr {
  overflow: auto;
}
```

Example with better names:

```html
<div class="ColumnBody is-scrollable"></div>
```

```css
.ColumnBody {
    background: #000;
}

.ColumnBody.is-scrollable {
    overflow: auto;
}
```

<a name="html-example"></a>
### 6.5. HTML Practical Example

An example of various conventions.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Document</title>
    <link rel="stylesheet" href="main.css">
    <script src="main.js"></script>
  </head>
  <body>
    <article class="Post" id="1234">
      <time class="Post-timestamp">{{date}}</time>
      <a data-analytics-action="{{action}}"
       data-analytics-category="{{category}}"
       data-id="1234"
       href="{{url}}">{{text}}</a>
      <ul>
        <li>
          <a href="{{url}}">{{text}}</a>
          <img src="{{src}}" alt="">
        </li>
        <li>
          <a href="{{url}}">{{text}}</a>
        </li>
      </ul>

      <a class="u-linkComplex" href="{{url}}">
        <span class="u-linkComplex-target">{{text}}</span>
        {{text}}
      </a>

      <input value="text" readonly>
    </article>
  </body>
</html>
```

Based extensively on work at [github.com/suitcss/suit](https://github.com/suitcss/suit/blob/master/doc/STYLE.md) and [github.com/necolas/idiomatic-html](https://github.com/necolas/idiomatic-html/blob/master/README.md).

<a name="license"></a>
## 8. License

_Trunk Club Coding Style Guide_ is licensed under the [Creative Commons
Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/).
This applies to all documents and translations in this repository.
