---
ID: 1495
post_title: Positioning
author: GravityBot
post_date: 2015-11-10 05:45:54
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-positioning/
published: true
kodex_post_likes_count:
  - "0"
kodex_post_dislikes_count:
  - "0"
---
### Introduction [#introduction](#introduction){#introduction}

Like [floats](https://gpdfv4.pv/v4-docs/developer-floats/), the PDF software does support `fixed` and `absolute` positioning of block elements in PDFs, but there are specific restrictions. These include:

1. Only block elements can `fixed` or `absolute` positioned (remember, [all HTML is hard-coded as either block or inline](https://gpdfv4.pv/v4-docs/developer-supported-html-and-css/#html-support)).
1. The element you want positioned needs to be a direct child of the `<body>` tag. Positioning won't work if the element is nested.
1. All positioning is relative to the current PDF page
1. You cannot next fixed position elements inside other fixed position elements
1. Positioning is overridden if it would be off the page

### Absolute Positioning [#absolute-positioning](#absolute-positioning){#absolute-positioning}

Absolute positioning treats the whole physical page as the containing element, irrespective of the page margins. That means if we set the top and left CSS attributes to zero your HTML would be at the very top-left corner of the page. 

```{.language-html}
<body>
    <div style="position: absolute; top: 0; left: 0">I'm outside the page margins</div>
    <div style="position: absolute; top: 0; right: 0">I'm outside the page margins</div>
    <div style="position: absolute; bottom: 0; left: 0">I'm outside the page margins</div>
    <div style="position: absolute; bottom: 0; right: 0">I'm outside the page margins</div>
</body>
```

### Fixed Positioning [#fixed-positioning](#fixed-positioning){#fixed-positioning}

As oppose to absolute positioning, fixed positioned elements adhere to the page margins, using it as the container. That means setting the top and left CSS attributes to zero would show your HTML positioned at the very beginning of the page margins.

```{.language-html}
<body>
    <div style="position: fixed; top: 0; left: 0">I'm inside the page margins</div>
    <div style="position: fixed; top: 0; right: 0">I'm inside the page margins</div>
    <div style="position: fixed; bottom: 0; left: 0">I'm inside the page margins</div>
    <div style="position: fixed; bottom: 0; right: 0">I'm inside the page margins</div>
</body>
```

### Rotated Elements [#rotated-elements](#rotated-elements){#rotated-elements}

Like tables, fixed or absolute positioned elements can be rotated 90 degrees clockwise and anti-clockwise:

```{.language-html}
<style>
    #rotated {
        position: absolute;
        top: 50mm;
        left: 100mm;

        width: 30mm;
        height: 40mm;

        background: grey;
        rotate: -90;
    }
</style>
<div id="rotated">Rotated</div>
```

### Auto Fit Text [#auto-fit-text](#auto-fit-text){#auto-fit-text}

One of the great features of positioned elements is the ability to have the text resize to fit the container. This is very useful when working with dynamic data from Gravity Forms.

```{.language-html}
<style>
    #rotated {
        position: absolute;
        top: 50mm;
        left: 100mm;

        font-size: 20pt;

        width: 30mm;
        height: 5mm;
        overflow: visible;
    }
</style>

<div id="rotated">My Very Long Text Too Big For Container</div>

<pagebreak>

<div id="rotated" style="overflow: auto">My Very Long Text Too Big For Container</div>
```

### Example [#example](#example){#example}

[We've put together a sample showing off the positioning support in Gravity PDF](https://gist.github.com/blueliquiddesigns/995559887bbad94b167f).