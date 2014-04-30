# Trunk Club HTML Style Guide

When working with markup in templates.

- use semantic markup, e.g. use `button` and not `href` for close links; see also [content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories)
- use `id` only for the dom-insertion of content containers (i.e. layout areas, regions), named anchors and form controls
- use [SUIT-style naming](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md#js-someName) for script hooks along with an indication of the element type, e.g. `class="js-widgetBtn"`
- apply and remove class names to affect style, rather than writing JavaScript to do the same
- do not use the `style` attribute; use `class` instead
- skip the `/` on [void elements](http://www.456bereastreet.com/archive/201005/void_empty_elements_and_self-closing_start_tags_in_html/), e.g. `<hr>` and not `<hr />` ([further reading](http://www.colorglare.com/2014/02/03/to-close-or-not-to-close.html))
- avoid use of the `<br>` tag; consider possible use of other semantic markup instead
- do not use classless `span` or `div` tags wrapped around content
- add a `type="button"` to all button elements other than `type="submit"` or `type="reset"`
- use the [`alt` text decision tree](http://dev.w3.org/html5/alt-techniques/#tree) when adding `img` elements
