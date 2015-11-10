---
ID: 1459
post_title: Managing PDFs
author: GravityBot
post_date: 2015-10-19 02:27:51
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-managing-pdfs/
published: true
---
![A look at a form's PDF list](https://gpdfv4.pv/app/uploads/2015/10/pdf-list.png) 

When you begin taking advantage of [conditional logic](https://gpdfv4.pv/v4-docs/setup-pdf/#conditional-logic), or install a [premium](#) or [custom](#) template, one PDF per form just isn't enough. That's why we've built an AJAXified PDF list to help you activate / deactivate, duplicate and delete your PDFs – all without a page reload. You can also add new PDFs or edit existing ones (it's not AJAX-powered though). The user interface is similar to the confirmation and notification lists so you should feel right at home. 

To access the *Managing PDFs* page see [Locating Your PDF Settings](https://gpdfv4.pv/v4-docs/setup-pdf/#locating).

---

### List Columns [#columns](#columns){#columns}

![The list column names](https://gpdfv4.pv/app/uploads/2015/10/column-list.png) 

The PDF list contains four columns which provide an overview of the PDFs currently configured for your Gravity Form.

Name [#name](#name){#name}
:    This column displays the internal PDF [name](https://gpdfv4.pv/v4-docs/setup-pdf/#name). It also functions as the "actions" column. By hovering over the row the `Edit`, `Duplicate` and `Delete` actions will appear in this column.

Download Shortcode [#download-shortcode](#download-shortcode)
:    This column displays a sample shortcode that generates a download link for the PDF. Use it in the Gravity Form confirmations or notifications. [See our shortcode documentation](https://gpdfv4.pv/v4-docs/shortcodes/) for more details about the `[gravitypdf]` shortcode.

Template [#template](#template){#template}
:    The selected PDF template will be displayed in this column. Along with the name, the template's group will also be displayed. For instance, any template that ships with the software is apart of the `Core` group. This is useful when you start creating [custom PDF templates](https://gpdfv4.pv/v4-docs/developer-start-customising/).
:    If you've run the [Setup Custom Templates](https://gpdfv4.pv/v4-docs/global-settings/#custom-templates) tool the text "User Templates" may appear. This means the template is being loaded from the user templates location instead of the core plugin files. See the [Custom Templates documentation](#) for more details.
:    PDF templates may also require a specific version of Gravity PDF. If the version requirements aren't met a notice will be displayed in this column.
Notifications [#notifications](#notifications)
:    If you've configured the PDF to attach to any of the form's notifications a list of those notifications will show in this column.

---

### Actions [#actions](#actions){#actions}

There a five main actions available to you when managing your PDFs. They are:

1. [Add](#add)
1. [Edit](#edit)
1. [Activate / Deactivate](#active-toggle)
1. [Duplicate](#duplicate)
1. [Delete](#delete)

The Edit, Duplicate and Delete actions will appear in the [#name](#name) column while hovering over the row.

#### Add [#add](#add){#add}

New PDFs can be added by clicking the `Add New` button, which is located to the right of the *Gravity PDF* page heading. [See our Setup PDF documentation](https://gpdfv4.pv/v4-docs/setup-pdf/) for more details on adding new PDFs.

#### Edit [#edit](#edit){#edit}

Click a PDFs *Edit* action to modify an existing PDF configuration. [See our Setup PDF documentation](https://gpdfv4.pv/v4-docs/setup-pdf/) for more in-depth details on what each PDF setting does.

#### Activate / Deactivate PDFs [#active-toggle](#active-toggle){#active-toggle}

![Active and deactivated toggles](https://gpdfv4.pv/app/uploads/2015/10/toggles.png) 

PDFs can be **completely disabled** by using the activate/deactivate toggle – located to the left of the `Name` column. Once a PDF has been deactivated users and administrators will no longer be able to access the document. The PDF will not be attached to email notifications, and its shortcode won't generate a link.

#### Duplicate [#duplicate](#duplicate){#duplicate}

![The UI shown when duplicating PDFs](https://gpdfv4.pv/app/uploads/2015/10/duplcate.png) 

You can duplicate an existing PDF configuration by clicking the *Duplicate* action. This action will happen in the background without the page reloading and once done you'll see a copy of the PDF added to the list.

#### Delete [#delete](#delete){#delete}

![The warning shown when deleting PDFs](https://gpdfv4.pv/app/uploads/2015/10/delete.png) 

You can delete an existing PDF configuration by clicking the *Delete* action. A warning box will pop up asking you to confirm before a PDF is deleted. This action will happen in the background without the page reloading.