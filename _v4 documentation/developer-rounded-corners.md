---
ID: 1500
post_title: Rounded Corners
author: GravityBot
post_date: 2015-11-09 04:49:51
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/documentation/v4/developer-rounded-corners/
published: true
kodex_post_likes_count:
  - "0"
kodex_post_dislikes_count:
  - "0"
---
### Introduction [#introduction](#introduction){#introduction}

The CSS3 `border-radius` property can be applied to all block elements to easily enhance the look and feel of your PDFs. The software is configured to automatically add appropriate padding to the container when rounded corners are enabled.

### CSS Format [#css-format](#css-format){#css-format}

Rounded corners can be enabled using both the CSS3-spec short and long-hand properties:

```{.language-css}
//short-hand
border-radius: 4em;

//long-hand
border-top-left-radius: 4em;
border-top-right-radius: 4em;
border-bottom-right-radius: 4em;
border-bottom-left-radius: 4em;
```

You can also control both the horizontal and vertical radius using short and long-hand CSS:

```{.language-css}
//short-hand
border-radius: 2em 1em 4em / 0.5em 3em;

//long-hand
border-top-left-radius: 2em 0.5em;
border-top-right-radius: 1em 3em;
border-bottom-right-radius: 4em 0.5em;
border-bottom-left-radius: 1em 3em;
```

### Examples [#examples](#examples){#examples}

```{.language-html}
<!-- Standard Border Radius -->
<div style="border-radius: 5px; height: 30mm; background: grey;"></div>

<!-- Standard Border Radius with larger corners -->
<div style="border-radius: 20px; height: 30mm; background: grey;"></div>

<!-- Only round one corner on the container -->
<div style="border-top-left-radius: 60px; height: 30mm; background: grey;"></div>

<!-- Create a circle using percentages and a square container -->
<div style="border-radius: 50%; height: 40mm; width: 40mm; background: grey;"></div>

<!-- Control the horizontal and vertical corner radius -->
<div style="border-radius: 2em 1em 4em / 0.5em 3em; height: 40mm; width: 40mm; background: grey;"></div>

<!-- Border Radius with 2px border -->
<div style="border-radius: 10px; height: 30mm; border: 2px solid black;"></div>
```

[Download example PDF template file showing off rounded corners](https://gist.github.com/blueliquiddesigns/c3b8202c29b768741ea7).