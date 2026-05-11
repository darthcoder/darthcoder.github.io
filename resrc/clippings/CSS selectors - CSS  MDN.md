---
title: "CSS selectors - CSS | MDN"
source: "https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors"
author:
published: 2026-01-08
created: 2026-03-16
description: "CSS selectors are patterns used in CSS rules to target and select specific elements for styling."
tags:
  - "clippings"
  - "css"
  - "selectors"
---
## CSS selectors

**CSS selectors** are patterns used in [CSS rules](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Syntax/Introduction#css_rulesets) to target and select specific elements for styling.

**Note:** This page is an index of all selectors in CSS. The [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Selectors) page introduces the module that defines some, but not all, of these selectors.

For example, to style paragraphs, you will use the `p` [type selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Type_selectors) to select all [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/p) elements and apply a style to them:

```
/* Set font size on all <p> elements */
p {
  font-size: 12px;
  color: rebeccapurple;
}
```

## Syntax

```
/* Select elements and apply styles */
selector {
  property: value;
}
```

## Index of selectors

- [& nesting selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Nesting_selector)
- [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Attribute_selectors)
- [Class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Class_selectors)
- [ID selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/ID_selectors)
- [Keyframe selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Keyframe_selectors)
- [Namespace separator (`|`)](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Namespace_separator)
- [Pseudo-class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Pseudo-classes)
- [Pseudo-element selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Pseudo-elements)
- [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Selector_list)
- [Type selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Type_selectors)
- [Universal selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Universal_selectors)

## Specifications

| Specification |
| --- |
| [Selectors Level 4](https://drafts.csswg.org/selectors/) |

Check the [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Pseudo-classes#specifications) and [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Pseudo-elements#specifications) pages for their respective specification tables.

## See also

- [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Selectors) module
- [CSS selector structure](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Selectors/Selector_structure)
- [CSS combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Combinators)
- [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/Selector_list)
- [Selectors and combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Selectors/Selectors_and_combinators)
- [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Pseudo-elements) module
- [CSS nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Nesting) module
- [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cascade/Specificity)