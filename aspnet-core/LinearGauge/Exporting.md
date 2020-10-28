---
layout: post
title: Exporting | lineargauge |  Syncfusion
description: exporting
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Exporting

Linear Gauge has an exporting feature that converts Gauge control into image format and then export in client side. The method API exportImage is used to export the LinearGauge. It has two arguments such as file name and file format to specify the file name and file formats. For exporting refer the following code example.


{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" width="500" label-color="#8c8c8c" >
 <e-linear-scale-collections>
            <e-linear-scales width="4" background-color="transparent"  show-ranges="true" length="310">
                <e-border color="transparent"></e-border>
                <e-linear-position x="51" y="50"></e-linear-position>
                <e-marker-pointer-collections>
                    <e-marker-pointers value="50" length="10" markerdistance-from-scale="8" width="10" marker-background-color="#4D4D4D">
                        <e-border color="#4D4D4D"></e-border>
                    </e-marker-pointers>
                </e-marker-pointer-collections>
                <e-linear-label-collections>
                    <e-linear-labels>
                        <e-font size="11px" font-family="Segoe UI" font-style="bold"></e-font>
                        <e-distance-from-scale x="-13"></e-distance-from-scale>
                    </e-linear-labels>
                </e-linear-label-collections>
                <e-bar-pointer-collections>
                    <e-bar-pointers bar-pointer-value="50" width="4" bar-pointerdistance-from-scale="8" bar-pointer-background-color="#6FAAB0"></e-bar-pointers>
                </e-bar-pointer-collections>
                <e-linear-tick-collections>
                    <e-linear-ticks color="#8c8c8c"></e-linear-ticks>
                </e-linear-tick-collections>
                <e-linear-range-collections>
                    <e-linear-ranges end-value="60" start-value="0" range-background-color="#F6B53F" start-width="4" end-width="4">
                        <e-border color="#F6B53F"></e-border>
                    </e-linear-ranges>
                    <e-linear-ranges end-value="100" start-value="60" range-background-color="#E94649" start-width="4" end-width="4">
                        <e-border color="#E94649"></e-border>
                    </e-linear-ranges>
                </e-linear-range-collections>
            </e-linear-scales>
        </e-linear-scale-collections>
</ej-linear-gauge> 

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

        $("#LinearGauge").ejLinearGauge("exportImage", FileName, FileFormat);

    }



</script>

{% endhighlight %}

Execute the above code to render the following output.

![](Exporting_images/Exporting_img1.png)



