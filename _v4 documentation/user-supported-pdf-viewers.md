---
ID: 1720
post_title: Supported PDF Viewers
author: GravityBot
post_date: 2015-10-22 03:25:45
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-supported-pdf-viewers/
published: true
---
Gravity PDF officially supports the [free Adobe Reader software](https://get.adobe.com/reader/) as Adobe is the company who developed the [PDF specification](http://www.adobe.com/devnet/pdf/pdf_reference.html). This means if a PDF generated with Gravity PDF has display issues in your PDF reader but shows correctly in Adobe Reader we won't consider it a bug. 

![FireFox PDF Rendering Issues](https://gpdfv4.pv/app/uploads/2015/10/Firefox-PDF-viewer-warning.png) 

These days browsers are shipping with a their own PDF viewing software so you don't have to install a third-party plugin. Firefox uses PDF.js, Chrome and Opera includes their own PDF plugin, Safari uses Preview and Microsoft's new browser, Edge, even ships with a document reader. This is great in theory, but in practice it causes problems. Why? Because building software that correctly renders PDFs is hard (just take a look at the [latest PDF specification](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/pdf/pdfs/adobe_supplement_iso32000.pdf) and tell us it doesn't give you a headache). And if that's not a compelling enough reason check [Firefox's PDF.js current open issues](https://github.com/mozilla/pdf.js/issues)... 

Adobe has third party plugins for most modern browsers which allow you to view PDF documents using Adobe Reader right in your favourite browser. The exception to this is version 42+ of Google Chrome which recently [stopped supporting NPAPI plugins like Adobe Reader, Silverlight and Java](https://support.google.com/chrome/answer/6213033?hl=en). Right now Adobe is yet to work around this issue. 

To ensure a consistent viewing experience if there isn't an Adobe Reader extension for your browser, your best option is to save the PDFs to your computer and open them with Adobe Reader.