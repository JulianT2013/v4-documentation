---
ID: 1498
post_title: Images
author: GravityBot
post_date: 2015-11-07 09:09:49
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-images/
published: true
kodex_post_likes_count:
  - "1"
kodex_post_dislikes_count:
  - "1"
---
### Introduction [#introduction](#introduction){#introduction}

The PDF engine Gravity PDF uses, [mPDF](http://mpdf1.com/manual/index.php), supports the following image formats:

* `png` with transparency or alpha channel
* `jpg` or `jpeg`
* `gif` with transparency
* `svg`
* `bmp`
* `wmf`

To display images use the standard `<img src="" />` HTML tag. The software will accept a URL or absolute path to the image file – we've found using an absolute path to the image ([use a path constant](https://gpdfv4.pv/v4-docs/development-helper-parameters/#useful-paths-and-urls)) offers better cross-host compatibility and it's the recommended way to display images. 

![Sample of mPDF image support](https://gpdfv4.pv/app/uploads/2015/11/image-support.png)

### Performance [#performance](#performance){#performance}

Images can slow the PDF generation time. If you are rendering an image heavy document and it is taking considerable time to generate you can optimise the process by:

1. Run your images through a compression service like [TinyPNG](https://tinypng.com/) and/or resize the image to a smaller format.
1. Use absolute paths to the images
1. Use JPG images over the other file types as they are quicker to process
1. PNGs with no alpha channel or transparency come in a close second to JPGs. 

### Float Support [#float-support](#float-support){#float-support}

There is partial support for floating images in mPDF however the following limitations apply:

* You can only have one floated image left and one floated right per container.
* Unlike your browser (which will overflow the image out of the container), the containing HTML element is extended at the bottom if necessary to enclose the floated image.
* Floats are ignored if the image is too wide for the container, inside a table, or div page-break-inside: avoid is set.

### Samples and Further Reading [#samples-and-further-reading](#samples-and-further-reading){#samples-and-further-reading}

[We've put together a sample showing off the image capabilities in Gravity PDF](https://gist.github.com/blueliquiddesigns/74216f846bbaeefeb29e).

[View the mPDF documentation](http://mpdf1.com/manual/index.php?tid=245) for more information about image support.