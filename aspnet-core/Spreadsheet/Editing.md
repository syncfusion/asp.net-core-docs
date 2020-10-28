---
layout: post
title: Editing in ASP.NET Core Spreadsheet widget | Syncfusion
description: You can learn about editing support in Syncfusion ASP.NET Core Spreadsheet control and more details. 
platform: aspnet-core
control: Spreadsheet
documentation: ug
---

# Editing in ASP.NET Core Spreadsheet 

You can edit the contents of a cell directly in the cell. You can also do this by typing in the formula bar. When you edit the cell, Spreadsheet is operating in edit mode. In this mode some of the options are unavailable. You can use `allow-editing` property to enable/disable editing feature.

N> By default `allow-editing` property is set to true.

## Edit cell content

You can perform this by one of the following ways,

* Double click on the cell to perform editing. This starts the edit mode and positions the cursor at the end of the cell.
* Press F2 Key to edit the active cell.
* Use Formula bar to perform editing.
* Use Backspace and Delete Key to delete the contents of a cell.
* Use "Alt + Enter" keys to perform multi line editing.
* Using [`editCell`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xledit-editcell "editCell") method.

## Save cell content

You can do this by one of the following ways,

* Perform mouse click on any other cell other than the current editing cell.
* Perform Enter/Tab key press on the cell.
* Using [`saveCell`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xledit-savecell "saveCell") method.

N> Edited cells are automatically formatted (right/left/center/Number Formatting) based on cell values.

The following code example describes the above behavior.

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" load-complete="loadComplete">
    <e-sheets>
        <e-sheet datasource="ViewBag.Datasource"></e-sheet>
    </e-sheets>
</ej-spread-sheet>

<script type="text/javascript">
    function loadComplete(args) {
        if(!this.isImport) {
            this.XLEdit.editCell(3, 0, true); //if true, it maintains the existing data otherwise it clears the data.
            //this.XLEdit.saveCell(); 
        }
    }
</script>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
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

![Save cell content using Spreadsheet in ASP.NET Core](Editing_images/Editing_img1.png)

## Read-Only Cells

You can restrict/prevent the editing in the specified range. You can use `allow-lock-cell` property to enable/disable the lock cells. You can do this by one of the following ways,

* Using [`lockCells`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:lockcells "lockCells") method to lock the selected cells. Then you need to protect the sheet using [`protectSheet`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:protectsheet "protectSheet") method to restrict the editing.
* Using "Lock Cells” option under Changes group of REVIEW tab in ribbon. Then Using "Protect Sheet” option under Changes group of REVIEW tab in ribbon to restrict editing.

The following code example describes the above behavior.

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" load-complete="loadComplete">
    <e-sheets>
        <e-sheet datasource="ViewBag.Datasource"></e-sheet>
    </e-sheets>
</ej-spread-sheet>

<script type="text/javascript">
    function loadComplete(args) {
        if(!this.isImport) {
            this.protectSheet(false);
            this.lockCells("A1:A5”, true);
            this.protectSheet(true);
        }
    }
</script>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
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

![Read-Only Cells using Spreadsheet in ASP.NET Core](Editing_images/Editing_img2.png)

## Events

The following events will trigger when editing and saving the cell. 

* `cellEdit` - Triggered when the cell is edited.
* `cellSave` - Triggered when save the edited cell.

## Data binding

You can bind the data to Spreadsheet using data manager. You can use [`saveBatchChanges`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:savebatchchanges "saveBatchChanges") method to update the changes in server.  

The following code example describes the above behavior.

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" load-complete="loadComplete">
    <e-sheets>
        <e-sheet>
            <e-datamanager url="Default" batch-url="BatchUpdate" adaptor="UrlAdaptor"></e-datamanager>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>

<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) {
            this.XLEdit.updateValue("I2", "amazon");
            this.XLEdit.updateValue("J2", "flipkart");
            this.saveBatchChanges(this.getActiveSheetIndex());
        }
    }
    </script>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {

        public ActionResult Editing()
        {          
            return View();
        }      

        public ActionResult Default()
        {
            List<ItemDetail> lItems = new List<ItemDetail>();
            lItems.Add(new ItemDetail() { ItemName = "Casual Shoes", Date = new DateTime(2014, 02, 14), Time = new DateTime(2014, 02, 14, 11, 34, 32), Quantity = 10, Price = 20, Amount = 200, Discount = 1, Profit = 10 });
            lItems.Add(new ItemDetail() { ItemName = "Sports Shoes", Date = new DateTime(2014, 06, 11), Time = new DateTime(2014, 06, 11, 05, 56, 32), Quantity = 20, Price = 30, Amount = 600, Discount = 5, Profit = 50 });
            lItems.Add(new ItemDetail() { ItemName = "Formal Shoes", Date = new DateTime(2014, 07, 27), Time = new DateTime(2014, 07, 27, 03, 32, 44), Quantity = 20, Price = 15, Amount = 300, Discount = 7, Profit = 27 });
            lItems.Add(new ItemDetail() { ItemName = "Sandals & Floaters", Date = new DateTime(2014, 11, 21), Time = new DateTime(2014, 11, 21, 06, 23, 54), Quantity = 15, Price = 20, Amount = 300, Discount = 11, Profit = 67 });
            lItems.Add(new ItemDetail() { ItemName = "Flip- Flops & Slippers", Date = new DateTime(2014, 06, 23), Time = new DateTime(2014, 06, 23, 12, 43, 59), Quantity = 30, Price = 10, Amount = 300, Discount = 10, Profit = 70 });
            return Json(new { result = lItems, count = lItems.Count });
        }

        public ActionResult BatchUpdate(List<ItemDetail> changed, List<ItemDetail> added, List<ItemDetail> deleted, string action, string key)
        {
            //Save the batch changes
        }
    }
}

{% endhighlight %}
{% endtabs %}

To save and retrieve the Spreadsheet data in the database, you can refer this [`Knowledge Base`](https://www.syncfusion.com/kb/7567/how-to-save-and-retrieve-the-spreadsheet-data-in-database "Knowledge Base") link.

You can update data dynamically in the Spreadsheet by using [`updateRange`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:updaterange "updateRange") method.