---
layout: post
title: Ribbon Dependencies | Ribbons | ASP.NET Core | Syncfusion
description: ribbon dependencies
platform: aspnet-core
control: Ribbon
documentation: ug
---

# Ribbon Dependencies

_ej.web.all.js_ is a bundle of all _ASP.NET Core_ controls. When you use _ej.web.all.js_ in your application, you can leave this section or else you can try to render _Ribbon_ in your application by using _ej.ribbon_ file. You can refer to the following frameworks and controls in your project.

_Ribbon Dependency_

<table>
<tr>
<th>
Files             </th><th>
Description/Usage </th></tr>
<tr>
<td>
ej.core.min.js</td><td>
Must always be referred to before using all the {{ '_ASP.NET Core_'  | markdownify }}controls.</td></tr>
<tr>
<td>
ej.data.min.js</td><td>
Used to handle data manger operation and should be used while binding data to {{ '_ASP.NET Core_' | markdownify }} controls.</td></tr>
<tr>
<td>
ej.globalize.min.js</td><td>
Must be referred to localize any of the JS control's text and content.</td></tr>
<tr>
<td>
ej.ribbon.min.js</td><td>
Should be referred when using {{ '_Ribbon_' | markdownify }}control.</td></tr>
<tr>
<td>
ej.waitingpopup.min.js</td><td>
This file is used to render waiting popup when on-demand functionality is enabled in {{ '_Ribbon_' | markdownify }}control.</td></tr>
<tr>
<td>
ej.menu.min.js</td><td>
This file is used to render menu in the application tab.</td></tr>
<tr>
<td>
ej.scroller.min.js</td><td>
This file is used to render scroller in the {{ '_Ribbon_' | markdownify }} control.</td></tr>
<tr>
<td>
ej.checkbox.min.js</td><td>
This file is used to render checkboxes in the {{ '_Ribbon_' | markdownify }} control.</td></tr>
<tr>
<td>
ej.tab.min.js</td><td>
This file is used to render tabs into the {{ '_Ribbon_' | markdownify }} control.</td></tr>
<tr>
<td>
ej.dropdownlist.min.js</td><td rowspan = "4">
  These files are used to render button,split button,toggle button, and dropdown list controls in the ribbon groups.</td></tr>
<tr>
<td>
ej.splitbutton.min.js</td></tr>
<tr>
<td>
ej.button.min.js</td></tr>
<tr>
<td>
ej.togglebutton.min.js</td></tr>
</table>