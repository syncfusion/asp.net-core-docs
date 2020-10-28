---
layout: post
title: Exporting | CircularGauge |  Syncfusion
description: exporting
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Exporting

* Circular Gauge has an exporting feature that converts Gauge control into image format and then export in client side. The method API exportImage is used to export the Circular Gauge. 
* It has two arguments such as file name and file format to specify the file name and file formats. For exporting refer the following code example.

{% highlight cshtml %}


<ej-circular-gauge id="circularGauge">
</ej-circular-gauge>

<input type="submit" value="Export Image" id="ExportImage" />
<div>FileName </div>
<input type="text" id="txtFileName">
<div >FileFormat </div>
<select id="FileType">
<option value="JPEG">JPEG</option>
<option value="PNG">PNG</option>
</select>


<script type="text/javascript">

        $(function () {

            $("#ExportImage").ejButton({ width: "100px", click: "buttonClickEvent", });

        });

        function buttonClickEvent() {

            var FileName = $("#txtFileName").val();

            var FileFormat = $("#FileType").val();

            $("#circularGauge").ejCircularGauge("exportImage", FileName, FileFormat);

        }

    </script>
    
{% endhighlight %}

Execute the above code to render the following output.

![](Exporting_images/Exporting_img1.png)

Circular Gauge control Export Functionality
{:.caption}


