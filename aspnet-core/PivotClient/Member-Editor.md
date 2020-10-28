---
layout: post
title: Member Editor | PivotClient | ASP.NET Core | Syncfusion
description:  Member editor in pivot client control
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Member Editor

The member editor dialog displays the members of current field in a tree view structure, which is opened by clicking the pivot button available in axis elements. It helps to search, filter, and sort the field members available in the pivot client control.

![Member editor in ASP NET Core pivot client control](Member_Editor_images/member_editor.png)

## Member editor - Paging

The member editor paging helps you to improve the rendering performance of the dialog by dividing the large amounts of data into sections and displaying them.

You can enable the member editor paging and set the member editor page size in the pivot client control by setting the [`enable-member-editor-paging`] and [`member-editor-page-size`] properties.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" enable-member-editor-paging="true" member-editor-page-size="100">
   //..
</ej-pivot-client>

{% endhighlight %}

The following are the navigation options available in the member editor pager:

* Move first: Navigates to the first page.
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Move last: Navigates to the last page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in a numeric value.


![Member editor paging in ASP NET Core pivot client control](Member_Editor_images/member_editor_paging.png)

## Member editor - Sorting

The sorting support in the member editor helps you to sort the field members in ascending or descending order.

You can enable the member editor sorting in the pivot grid control by setting the [`enable-member-editor-sorting`] property.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" enable-member-editor-sorting="true">
   //..
</ej-pivot-client>

{% endhighlight %}

![Member editor sorting with ascending order in ASP NET Core pivot client control](Member_Editor_images/member_editor_sorting_ascending.png)

![Member editor sorting with descending order in ASP NET Core pivot client control](Member_Editor_images/member_editor_sorting_descending.png)