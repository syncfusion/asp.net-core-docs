---
layout: post
title: Exporting the Digital Gauge | DigitalGauge | Syncfusion
description: exporting the digital gauge
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

# Exporting the Digital Gauge

Digital Gauge has an exporting feature where Gauge control is converted into image format and then exported to client-side. The method API exportImage exports the Digital Gauge. It has two arguments such as filename and file format. For exporting, you can refer the following code example.


{% highlight CSHTML %}



<ej-digital-gauge id="DigitalGauge"  value="syncfusion">
</ej-digital-gauge>

<input type="submit" value="Export Image" id="ExportImage" />
<div>FileName </div>
<input type="text" id="txtFileName">
<div >FileFormat </div>
<select id="FileType">
<option value="JPEG">JPEG</option>
<option value="PNG">PNG</option>
</select>

<script>
 $(function () {

            $("#ExportImage").ejButton({ width: "100px", click: "buttonClickEvent", });

        });

        function buttonClickEvent() {

            var FileName = $("#txtFileName").val();

            var FileFormat = $("#FileType").val();

            $("#DigitalGauge").ejDigitalGauge("exportImage", FileName, FileFormat);

        }
	

</script>

{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.

![](Exporting-the-Digital-Gauge_images/Exporting-the-Digital-Gauge_img1.png)

Digital Gauge control with Export functionality
{:.caption}



