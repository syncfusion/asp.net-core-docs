---
layout: post
title: Clipboard in ASP.NET Core Spreadsheet widget | Syncfusion 
description: You can learn here about clipboard support in Syncfusion ASP.NET Core Spreadsheet control and more details.
platform: aspnet-core
control: Spreadsheet
documentation: ug
---

# Clipboard in ASP.NET Core Spreadsheet

The Spreadsheet provides support for the clipboard operations (cut, copy, and paste). Clipboard operations can be enabled or disabled by setting `allow-clipboard` property in Spreadsheet.
By default `allow-clipboard` property is `true`.

## Cut

This function cuts the selected range values and make it available in clipboard.

You can do this by one of the following ways. 

* Using "Ctrl + X" key.
* Using Cut button of HOME tab in ribbon to perform cut operation.
* Using Cut option in Context Menu.
* Using [`cut`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlclipboard-cut "cut") method.

## Copy

This function copies the selected range values and make it available in clipboard.

You can do this by one of the following ways. 

* Using "Ctrl + C" key.
* Using Copy button of HOME tab in ribbon to perform copy operation.
* Using Copy option in Context Menu.
* Using [`copy`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlclipboard-copy "copy") method.

## Paste

This function pastes the clipboard content to newly selected range. If you perform cut paste, clipboard contents are cleared whereas in copy paste the clipboard contents are maintained. 

You have following options in Paste.

* Paste Special - You can paste the values with formatting.
* Paste - You can paste only the values.

N> The default paste option is Paste Special. This is working only within the current Spreadsheet. If you copy the content from other sources, it will paste only the values in the Spreadsheet.

You can do this by one of the following ways,

* Using "Ctrl + V" key.
* Using Paste button of HOME tab in ribbon to perform paste operation.
* Using Paste option in Context Menu.
* Using [`paste`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlclipboard-paste "paste") method.

The following code example describes the above behavior.

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" allow-clipboard="true" load-complete="loadComplete">
    <e-sheets>
        <e-sheet>
            <e-range-settings>
                <e-range-setting datasource="ViewBag.Datasource"></e-range-setting>
            </e-range-settings>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>

<script type="text/javascript">
    function loadComplete() {
        var xlClip = this.XLClipboard;
        this.performSelection("G1:H3");
        xlClip.cut(); // Cut the selected cells
        //xlClip.copy();//Copy the selected cells.
        this.performSelection("J4");
        xlClip.paste();
    }
</script>

{% endhighlight %}
{% highlight c# %}

namespace samplebrowser.Controllers.SpreadsheetASP
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            List<ItemDetail> lItems = new List<ItemDetail>();
            lItems.Add(new ItemDetail() { ItemName = "Casual Shoes", Date = new DateTime(2014, 02, 14), Time = new DateTime(2014, 02, 14, 11, 34, 32), Quantity = 10, Price = 20, Amount = 200, Discount = 1, Profit = 10 });
            lItems.Add(new ItemDetail() { ItemName = "Sports Shoes", Date = new DateTime(2014, 06, 11), Time = new DateTime(2014, 06, 11, 05, 56, 32), Quantity = 20, Price = 30, Amount = 600, Discount = 5, Profit = 50 });
            lItems.Add(new ItemDetail() { ItemName = "Formal Shoes", Date = new DateTime(2014, 07, 27), Time = new DateTime(2014, 07, 27, 03, 32, 44), Quantity = 20, Price = 15, Amount = 300, Discount = 7, Profit = 27 });
            lItems.Add(new ItemDetail() { ItemName = "Sandals & Floaters", Date = new DateTime(2014, 11, 21), Time = new DateTime(2014, 11, 21, 06, 23, 54), Quantity = 15, Price = 20, Amount = 300, Discount = 11, Profit = 67 });
            lItems.Add(new ItemDetail() { ItemName = "Flip- Flops & Slippers", Date = new DateTime(2014, 06, 23), Time = new DateTime(2014, 06, 23, 12, 43, 59), Quantity = 30, Price = 10, Amount = 300, Discount = 10, Profit = 70 });
            ViewBag.Datasource = lItems;
            return View();
        }
    }
}

{% endhighlight %}
{% endtabs %}

The following output is displayed as a result of the above code example.

![Using Spreadsheet Clipboard](Clipboard_images/Clipboard_img1.png)

N> Similarly you can perform clipboard operations for shapes (Chart).