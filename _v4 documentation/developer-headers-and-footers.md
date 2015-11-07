---
ID: 1497
post_title: Headers and Footers
author: GravityBot
post_date: 2015-11-04 03:58:34
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-headers-and-footers/
published: true
---
### Introduction [#introduction](#introduction){#introduction}

Headers and footers are a powerful feature of the PDF rendering software, mPDF. They aren't just limited to every page either, you have granular control over which pages your headers and footers display on.

![Example of PDF header and footer](https://gpdfv4.pv/app/uploads/2015/11/header-footer-support.png)

### Defining Headers/Footers [#defining-headers-and-footers](#defining-headers-and-footers){#defining-headers-and-footers}

The first thing you need to do is define a header/footer in your PDF template, then you tell the software when to display it. The two tags to define headers/footers are `<htmlpageheader name="">` and `<htmlpagefooter name="">`. 

The headers/footers HTML tags can be included anywhere inside the `<body>` tag, but recommend including it right after the `<body>` tag is opened.

#### Headers [#headers](#headers){#headers}

The `<htmlpageheader>` tag allows you to define a header template and everything inside the tag will be rendered at the top of your page. The tag has one required attribute `name` which acts as an ID for your header. Just ensure you don't use a name that begins with `html_` as that prefix is reserved.

```{.language-html}
<htmlpageheader name="MyCustomHeader">
    <table style="border-bottom: 1px solid #000000; vertical-align: bottom; font-family: serif; font-size: 9pt; color: #000088;" width="100%">
        <tbody>
            <tr>
                <td width="50%">Title</td>
                <td style="text-align: right; font-weight: bold;" width="50%">Logo</td>
            </tr>
        </tbody>
    </table>
</htmlpageheader>
```

#### Footers [#footers](#footers){#footers}

The `<htmlpagefooter>` tag allows you to define a footer template and everything inside the tag will be rendered at the bottom of your page. The tag has one required attribute `name` which acts as an ID for your footer. Just ensure you don't use a name that begins with `html_` as that prefix is reserved.

```{.language-html}
<htmlpagefooter name="MyCustomFooter">
    <table style="vertical-align: bottom; font-family: serif; font-size: 8pt; color: #000000; font-weight: bold; font-style: italic;" width="100%">
        <tbody>
            <tr>
                <td width="33%"><span style="font-weight: bold; font-style: italic;">{DATE j-m-Y}</span></td>
                <td style="font-weight: bold; font-style: italic;" align="center" width="33%">{PAGENO}/{nbpg}</td>
                <td style="text-align: right;" width="33%">My document</td>
            </tr>
        </tbody>
    </table>
</htmlpagefooter>
```

### Displaying Headers/Footers [#displaying-headers-and-footers](#displaying-headers-and-footers){#displaying-headers-and-footers}

There are two different methods to assign headers and footers:

1. Using the special CSS selector `@page`
1. Using mPDF's custom HTML setter tags `<sethtmlpageheader>` and `<sethtmlpagefooter>`

#### @page [#at-page](#at-page){#at-page}

Using `@page` is the preferred way to set a header or footer in the PDF as it has less quirks and keeps your HTML mark-up cleaner.

```{.language-html}
<style>
    @page {
        header: html_MyCustomHeader; /* display <htmlpageheader name="MyCustomHeader"> on all pages */
        footer: html_MyCustomFooter; /* display <htmlpagefooter name="MyCustomFooter"> on all pages */
    }
</style>
```    

You can also apply headers and footers to the first page of your document using the pseudo selector `:first`.

```{.language-html}
<style>
    /* Displays on all pages of the PDF */
    @page {
        header: html_MyCustomHeader; 
    }

    /* Overrides the @page header and displays on the first page of the PDF */
    @page :first {
        header: html_MyCustomHeader; 
    }
</style>
```

You can also get more specific with named `@page` selectors but [we'll discuss those in the `<pagebreak>` section](#).

#### Inline HTML [#inline-html](#inline-html){#inline-html}

The use of the `<sethtmlpageheader />` or `<sethtmlpagefooter />` tag will set a header/footer on the current page in the document. While using [@page](#@page) is preferred, these tags do have their usefulness – because there's currently no `@page :last` pseudo selector we can use them before the closing `</body>` tag to display a header/footer on the very last page.

```{.language-html}
<sethtmlpageheader name="html_MyCustomHeader" show-this-page="1" value="on" />
<sethtmlpagefooter name="html_MyCustomFooter" value="on" />
</body>
```

The extra attribute `show-this-page` in the header tag is required because the PDF software has already finished writing the page header. This tells it to go back and set our new header, otherwise it will wait until the next page. You can also turn headers/footers off for specific pages:

```{.language-html}
<sethtmlpageheader value="off" />
<sethtmlpagefooter value="off" />
```

### Reserved Variables [#reserved-variables](#reserved-variables){#reserved-variables}

Header and Footers have access to the following reserved variables that can be used to display the current page number and the total page number:

* `{pageno}` – Will be replaced by the current page number.
* `{nb}` – Will return the total number of pages in the PDF document

### Samples and Further Reading [#samples-and-further-reading](#samples-and-further-reading){#samples-and-further-reading}

We've put together two sample PDF templates showing off the two header and footer methods we discussed above:

1. [Example 1 – @page](https://gist.github.com/blueliquiddesigns/7d62b713e51f8e956a91)
1. [Example 2 – Inline HTML](https://gist.github.com/blueliquiddesigns/af2f81d4c3e61bb2da01)

For more information about the methods discussed we recommend reviewing the mPDF documentation:

* [`@page`](http://mpdf1.com/manual/index.php?tid=307)
* [`<htmlpageheader>`](http://mpdf1.com/manual/index.php?tid=177)
* [`<htmlpagefooter>`](http://mpdf1.com/manual/index.php?tid=178)
* [`<sethtmlpageheader>`](http://mpdf1.com/manual/index.php?tid=179)
* [`<sethtmlpagefooter>`](http://mpdf1.com/manual/index.php?tid=180)

                    