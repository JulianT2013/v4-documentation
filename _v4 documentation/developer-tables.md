---
ID: 1502
post_title: Tables
author: GravityBot
post_date: 2015-11-10 04:17:45
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-tables/
published: true
kodex_post_likes_count:
  - "1"
kodex_post_dislikes_count:
  - "1"
---
### Introduction [#introduction](#introduction){#introduction}

There is quite good support for HTML tables in [mPDF](http://www.mpdf1.com/mpdf/index.php), but it does have its quirks. The two biggest issues you might face when using tables are:

1. **Unsupported Block Elements**. All block elements included in table cells are ignored. The content will still be displayed but you won't be able to directly style the elements using CSS (you can still apply styles to the table cell directly).

1. **Autosizing.** On a website if a table is too large for its container it might overflow outside it, or use a horizontal scroll bar. Because PDFs cannot do those things it instead alters the column widths and font sizes. Basically, mPDF places more priority on producing a pleasing, efficiently laid out table than it does respecting defined widths and sizes. [But there are ways to minimise this effect](#table-rendering).

Because of those two issues tables have limited use when designing your PDF layout. We've found [carefully calculated floats](#) is the better option for producing more complex designs. Use tables for tabular data and you'll find them a treat. 

![Example of Tables rendered in mPDF](https://gpdfv4.pv/app/uploads/2015/11/table-preview.png)

### Table Rendering [#table-rendering](#table-rendering){#table-rendering}

The table autosizing feature can sometimes cause issues with your layouts. One way to prevent unnessisary font resizing is to set a special `autosize` attribute to `1` when defining the table:

```{.language-html}
<table autosize="1">
</table>
```

Other problems with cell width can occur when you have fixed widths applied to `<td>` or `<th>` tags. To prevent problems you should follow these notes:

1. Instead of using pixels or millimetres for cell widths, use percentages instead. 

1. We recommend you apply the width to every row – either inline, or using CSS classes. Remember, each row's cell width must be the same as the last rows. If you do need to change cell width at some point you could either:
     * Add extra columns and use `colspan` to create a more robust structure
     * Use a `<table>` inside your table cell – the HTML becomes complex very quickly so try steer clear.

1. Ensure the column width percentages add up to 100%. Keep in mind the [standard box-model applies](https://css-tricks.com/the-css-box-model/) so left and right padding on your cells should be included in your width calculations.

```{.language-html}
<table autosize="1">
   <tr>
        <td width="30%">Cell 1</td>
        <td width="70%">Cell 2</td>
   </tr>

   <tr>
        <td width="30%">Cell 1</td>
        <td width="70%">Cell 2</td>
   </tr>
</table>
```

### Repeating Header and Footers [#repeating-header-and-footer](#repeating-header-and-footer){#repeating-header-and-footer}

If a table extends across multiple pages the `<thead></thead>` and `<tfoot></tfoot>` elements will be automatically appended and prepended to the table for each new page.

### Rotating Table [#rotating-table](#rotating-table){#rotating-table}

Tables can be rotated 90 degrees clockwise or counter-clockwise so they fit nicely on portrait documents. This feature can be applied using the CSS `rotate` property.

```{.language-css}
table#clockwise {
   rotate: 90;
}

table#counterclockwise {
   rotate: -90;
}
```

### Example [#example](#example){#example}
[We’ve put together a sample showing off the table support in Gravity PDF](https://gist.github.com/blueliquiddesigns/de009962d7ec776d223c).

For more information about the methods discussed we recommend reviewing the mPDF documentation:

* [Tables](http://mpdf1.com/manual/index.php?tid=77)
* [Table Layout](http://mpdf1.com/manual/index.php?tid=319)
* [Auto Table Layout](http://mpdf1.com/manual/index.php?tid=292)
* [Border Collapse](http://mpdf1.com/manual/index.php?tid=291)
* [Supported HTML](http://mpdf1.com/manual/index.php?tid=256)
* [Supported CSS](http://mpdf1.com/manual/index.php?tid=34)