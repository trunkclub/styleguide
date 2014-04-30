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
7. [License](#license)

<a name="golden-rule"></a>
## 1. The Golden Rule

All code in the codebase should look like a single person typed it, no matter how many people contribute.

<a name="in-general"></a>
## 2. In General

- do not commit commented-out code to master
- don't leave `TODO`s, `FIXME`s or `BUG`s in the code, but if you do use `TODO`, `FIXME` or `BUG` in your comment
- comments left in the code should be timeless, e.g. always applicable until they're removed

<a name="whitespace"></a>
## 3. Whitespace

* Use whitespace to improve readability.
* Use two spaces for indentation.
* In general, don't use more than one blank line as a separator.
* Strip all end-of-line whitespace.
* Ensure file ends with one line-break.

<a name="guides-by-language"></a>
## 4. Guides by Language

- [CoffeeScript](coffeescript.md)
- [HTML](html.md)
- [JavaScript](javascript.md)
- [Sass](sass.md)

<a name="css"></a>
## 5. CSS

<a name="css-whitespace"></a>
### 5.1 CSS Whitespace

* Use whitespace to improve readability.
* Use two spaces for indentation.
* Don't use more than one blank line as a separator.
* Strip all end-of-line whitespace.
* Ensure file ends with one line-break.

<a name="css-comments"></a>
### 5.2. CSS Comments

Well commented code is extremely important. Take time to describe components,
how they work, their limitations, and the way they are constructed. Don't leave
others in the team guessing as to the purpose of uncommon or non-obvious
code.

Comment style should be simple and consistent within a single code base.

* Place comments on a new line above their subject.
* Keep line-length to a sensible maximum, e.g., 80 columns.
* Make liberal use of comments to break CSS code into discrete sections.
* Use "sentence case" comments and consistent text indentation.
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
 * @tag This is a tag named 'tag'
 *
 * 1. A helpful description of a declaration's purpose.
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

Based extensively on work at [github.com/suitcss/suit](https://github.com/suitcss/suit/blob/master/doc/STYLE.md) and [github.com/necolas/idiomatic-html](https://github.com/necolas/idiomatic-html/blob/master/README.md).

<a name="license"></a>
## 6. License

The MIT License (MIT)

Copyright (c) 2014 Trunk Club, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
