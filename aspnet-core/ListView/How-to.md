---
title: How To | ListView | ASP.NET CORE | Syncfusion
description: “How to do” section for ListView
platform: aspnet-core
control: ListView
documentation: UG
keywords: ListView,  Syncfusion, UG document, How To
---
# How To

## Get the selected values on post back

**Single selection**

Enable the property [PersistSelection](https://help.syncfusion.com/api/js/ejlistview#members:persistselection) in order to use selection in ListView. Then use the [getActiveItemText](https://help.syncfusion.com/api/js/ejlistview#methods:getactiveitemtext) method take the selected active text through javascript and then pass it to the controller via AJAX. 

 
{% highlight html %}

<ej-list-view id="listview" persist-selection="true" width="400">
    <e-list-view-items>
        <e-list-view-item text="Artwork"></e-list-view-item>
        <e-list-view-item text="Abstract"></e-list-view-item>
        <e-list-view-item text="2 Acrylic Mediums"></e-list-view-item>
        <e-list-view-item text="Creative Acrylic"></e-list-view-item>
        <e-list-view-item text="Modern Painting"></e-list-view-item>
        <e-list-view-item text="Canvas Art"></e-list-view-item>
        <e-list-view-item text="Black white"></e-list-view-item>
        <e-list-view-item text="Children"></e-list-view-item>
        <e-list-view-item text="Preschool Crafts"></e-list-view-item>
        <e-list-view-item text="School-age Crafts"></e-list-view-item>
    </e-list-view-items>
</ej-list-view>

<ej-button id="btn" text="Post" click="onclick" />


<script>
    function onclick() {       
        var text = $("#listview").ejListView("getActiveItemText");      
        $.ajax({ 
            type: "POST", 
            data: { value: text },
            url: "/Home/Features", 
            success: function (result) {  
                alert(result); 
            } 
        }); 
 
    }    
    
</script>

    
{% endhighlight %}

    
    {% highlight c# %}
    
     [HttpPost]
        public ActionResult Features(string value)
        {
            var val = value;
            return Json(val);
        }


    
    {% endhighlight %}



**Multiple selection**

{% highlight html %}

<ej-list-view id="listview" enable-check-mark="true" width="400">
    <e-list-view-items>
        <e-list-view-item text="Artwork"></e-list-view-item>
        <e-list-view-item text="Abstract"></e-list-view-item>
        <e-list-view-item text="2 Acrylic Mediums"></e-list-view-item>
        <e-list-view-item text="Creative Acrylic"></e-list-view-item>
        <e-list-view-item text="Modern Painting"></e-list-view-item>
        <e-list-view-item text="Canvas Art"></e-list-view-item>
        <e-list-view-item text="Black white"></e-list-view-item>
        <e-list-view-item text="Children"></e-list-view-item>
        <e-list-view-item text="Preschool Crafts"></e-list-view-item>
        <e-list-view-item text="School-age Crafts"></e-list-view-item>
    </e-list-view-items>
</ej-list-view>

<ej-button id="btn" text="Post" click="onclick" />


<script>
    
    function onclick() {
       
        var text = $("#listview").ejListView("getCheckedItemsText");
        $.ajax({ 
            type: "POST", 
            data: { value: text },
            url: "/Home/Features", 
            success: function (result) {  
                alert(result); 
            } 
        }); 
 
    }    
    

</script>

    
{% endhighlight %}


    
    {% highlight c# %}
    
      [HttpPost]
         public ActionResult Features(object value)  
         {
             object val = value;
             return Json(val);
         }

    
    {% endhighlight %}
    
