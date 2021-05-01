---
layout: post
title: Getting Started with ASP.NET Core Toolbar control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core Toolbar control, its elements, and more.
platform: aspnet-core
control: Toolbar
documentation: ug
---

# Getting Started with ASP.NET Core Toolbar

This section explains how to create a Toolbar in your ASP.NET Core application. 

## Create your first Toolbar in ASP.NET Core

### Create Toolbar for PDF Reader

Toolbar control displays a list of tools in a web page. It is used to customize Toolbar items of any functionality by using enriched client-side methods. This control consists of a collection of unordered lists, containing text and images in <div>.This section explains how to customize Toolbar control for a PDF Reader scenario.Here, the Toolbar consists of a title and text area like PDF Reader.


![Getting-Started_images0](Getting-Started-images/Getting-Started0.JPG)

### Create a Toolbar

The basic rendering of ASP.NET Core Toolbar is achieved with default functionality.

1.Create an ASP.NET Core Project as given in [`ASP.NET Core`](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) documentation

2.Then, add the mentioned code to the corresponding view page for Toolbar rendering.

{% highlight CSHTML %}

   	 <!--ej-Tag Helper code to render Toolbar-->

        <ej-toolbar id="Toolbar1" >
            
        </ej-toolbar>


{% endhighlight  %}
 
{% highlight Razor %}

     <!--Razor code to render Toolbar-->
   
       @{Html.EJ().Toolbar("ToolbarItem").Render(); }


{% endhighlight  %}

The following output is displayed.

![Getting-Started_images1](Getting-Started-images/Getting-Started1.png)

Toolbar without Toolbar items
{:.caption}

N> To render the Toolbar Control, use either Razor or Tag helper code as given in the above code snippet.

### Initialize Toolbar Items

The toolbar consists of a list of items. To initialize the Toolbar items, use the following code: 

{% highlight CSHTML %}

	/*ej-Tag Helper code to render Toolbar*/
	
	<ej-toolbar id="Toolbar2" width="250px">
        
         <e-toolbar-items>
            <e-toolbar-item sprite-css-class="PdfDocument e-icon convertToOthers" tooltip-text="Convert to others" />
            <e-toolbar-item sprite-css-class="PdfDocument e-icon convertToPdf" tooltip-text="convertToPdf" />
            <e-toolbar-item sprite-css-class="PdfDocument e-icon signature" tooltip-text="signature" />
            <e-toolbar-item sprite-css-class="PdfDocument e-icon print" tooltip-text="print" />
            <e-toolbar-item sprite-css-class="PdfDocument e-icon msg" tooltip-text="message" />
        </e-toolbar-items>
        
    </ej-toolbar> 

{% endhighlight  %}

{% highlight Razor %}

     <!--Razor code to render Toolbar-->
   
    @{Html.EJ().Toolbar("Toolbar1").Items(s =>
        {
            s.Add().SpriteCssClass("PdfDocument e-icon convertToOthers").TooltipText("Convert to others");
            s.Add().SpriteCssClass("PdfDocument e-icon convertToPdf ").TooltipText("convertToPdf");
            s.Add().SpriteCssClass("PdfDocument e-icon signature ").TooltipText("signature");
            s.Add().SpriteCssClass("PdfDocument e-icon print").TooltipText("print");
            s.Add().SpriteCssClass("PdfDocument e-icon msg").TooltipText("message");
        }).Width("250px").Render();
    }


{% endhighlight  %}

 Apply the given styles in the code table to show the Toolbar items. You can refer images from any location.The images in the following code example were referred from:

[http://js.syncfusion.com/UG/Web/Content/](http://js.syncfusion.com/UG/Web/Content/)pdf-icon.png

{% highlight css %}

    <style type="text/css" class="cssStyles">
       
      .e-tooltxt .e-icon {
        background-image: url('http://js.syncfusion.com/UG/Web/Content/pdf-icon.png');
        background-repeat: no-repeat;
        display: block;
        height: 30px;

        width: 30px;
     }

     .convertToOthers {
        background-position: -349px 0px;
     }

     .convertToPdf {
        background-position: -527px 0px;
     }

     .signature {
        background-position: 2px 0px;
     }

     .save {
        background-position: -87px 0px;
      }

      .print {
        background-position: -43px 0px;
      }

      .msg {
        background-position: -483px 0px;
      }

   </style>

{% endhighlight  %}

Execute the code to render a Toolbar with a list of Toolbar items.

![Getting-Started_images2](Getting-Started-images/Getting-Started2.png)

Toolbar with list of toolbar items
{:.caption}

### Render Toolbar Items with separator 

You can separate or group Toolbar items. The separation or grouping can be achieved by using the <b>enableSeparator</b> property.

Initialize the Toolbar items using the following code to group Toolbar items.

{% highlight CSHTML %}

 	 <!--ej-Tag Helper code to render Toolbar-->

	  <div class="cols-sample-area">
          
       <ej-toolbar id="toolbarJson" enable-separator="true" orientation="@Orientation.Horizontal" width="250px" dataSource="ViewBag.datasource">
        <e-toolbar-fields id="id" sprite-css-class="spriteCss" group="group" />
       </ej-toolbar>
      
      </div>

{% endhighlight  %}

{% highlight Razor %}

     <!--Razor code to render Toolbar-->
	 
       <div class="cols-sample-area">
	   
        @{Html.EJ().Toolbar("toolbarJson").EnableSeparator(true).Datasource((IEnumerable<Toolbar>)ViewBag.datasource1).ToolbarFields(f => f.ID("id").SpriteCssClass("spriteCss").Group("group")).Orientation(Orientation.Horizontal).Width("250px").Render(); }
      
	  </div>
{% endhighlight  %}

{% highlight c# %}

    public IActionResult Index()
        {
            List<ToolbarLocalBinding> t = new List<ToolbarLocalBinding>();

            t.Add(new ToolbarLocalBinding { id = "1", spriteCss = "IE", group = "g1" });
            t.Add(new ToolbarLocalBinding { id = "2", spriteCss = "chrome", group = "g2" });
            t.Add(new ToolbarLocalBinding { id = "3", spriteCss = "firefox", group = "g2" });
            t.Add(new ToolbarLocalBinding { id = "4", spriteCss = "bitty", group = "g2" });
            t.Add(new ToolbarLocalBinding { id = "5", spriteCss = "opera", group = "g1" });
            ViewBag.datasource = t;

            return View();
        }
		
		
		public class ToolbarLocalBinding
    {
        public string id { get; set; }
        public string spriteCss { get; set; }
        public string text { get; set; }
        public string group { get; set; }

    }
{% endhighlight  %}


Add the following styles in the code table to display the Toolbar items as follows. 

{% highlight css %}

 /*Additional style for Remaining toolbar items*/
 
       <style type="text/css" class="cssStyles">

      .cols-sample-area .e-tooltxt .e-spriteimg {
        display: block;
        background-image: url('../../images/browser.png');
        height: 32px;
        width: 32px;
        background-repeat: no-repeat;
       }



      .IE
      {
        background-position: -84px 0px;
      }

      .chrome 
	  {
         background-position: -42px 0px;
      }

      .firefox
	  {
         background-position: 0px 0px;
      }

       .bitty
	   {
       background-position: -126px 0px;
        }

       .opera 
	   {
       background-position: -168px 0px;

	   }



</style>

{% endhighlight  %}

Execute the code to render Toolbar items with a separator.

![Getting-Started_images3](Getting-Started-images/Getting-Started3.png)

### Add Actions to Toolbar Items

After the Toolbar is rendered, you need to render the header and content area to create a PDF Reader.The below code sample shows how to render the header (toolbar), content section (PDF viewer area), and set the action to toolbar items.

N> PDF reading or rendering is not shown here. Simulation of the PDF Reader app to demonstrate the usage of Toolbar control is provided. PDF rendering area is ignored._



Initialize the content area and header as specified in the code table.

{% highlight CSHTML %}

	 <!--ej-Tag Helper code to render Toolbar-->
    
	     <div id="ctrllabel">PDF Reader</div>
       
            <ej-toolbar id="Toolbar4" width="450px">
                
                <e-toolbar-items>
				
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon convertToOthers" tooltip-text="Convert to others"  />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon convertToPdf" tooltip-text="convertToPdf"/>
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon signature" tooltip-text="signature"  />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon print" tooltip-text="print"/>
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon msg" tooltip-text="message" />

                </e-toolbar-items>
                <e-toolbar-items>
				
				     <e-toolbar-item sprite-css-class="PdfDocument e-icon previous" tooltip-text="Previous" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon next" tooltip-text="Next"  />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon zoomIn" tooltip-text="ZoomIn" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon zoomOut" tooltip-text="ZoomOut" />

                </e-toolbar-items>
                <e-toolbar-items>

                     <e-toolbar-item sprite-css-class="PdfDocument e-icon fitOne" tooltip-text="Fit one" group="g3" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon sticky" tooltip-text="Sticky" group="g3" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon readMode" tooltip-text="Read Mode" group="g3" />


              </e-toolbar-items>


        </ej-toolbar>
        <br />
        <div id="contentSection">

            <textarea id="content" rows="16" cols="100" style="max-width:450px">

                Description:

                Toolbar control supports displaying a list of tools within a Web page. This control is capable of

                customizing toolbar items with any functionality by using enriched client-side methods.This control

                Is composed of collection of unordered lists containing text and images contained into a div.

            </textarea>

        </div>
{% endhighlight  %}

{% highlight Razor %}

   <!--Razor code to render Toolbar-->
   
    <div id="ctrllabel">PDF Reader</div>
   
      @{Html.EJ().Toolbar("Toolbar3").Items(s =>
        {
            s.Add().SpriteCssClass("PdfDocument e-icon convertToOthers").TooltipText("Convert to others");
            s.Add().SpriteCssClass("PdfDocument e-icon convertToPdf ").TooltipText("convertToPdf");
            s.Add().SpriteCssClass("PdfDocument e-icon signature ").TooltipText("signature");
            s.Add().SpriteCssClass("PdfDocument e-icon print").TooltipText("print");
            s.Add().SpriteCssClass("PdfDocument e-icon msg").TooltipText("message");
        }).Items(s1 =>
        {
            s1.Add().SpriteCssClass("PdfDocument e-icon previous").TooltipText("Previous");
            s1.Add().SpriteCssClass("PdfDocument e-icon next").TooltipText("Next");
            s1.Add().SpriteCssClass("PdfDocument e-icon zoomIn ").TooltipText("zoom In ");
            s1.Add().SpriteCssClass("PdfDocument e-icon zoomOut ").TooltipText("zoom Out ");


        }).Items(s2 =>
        {
            s2.Add().SpriteCssClass("PdfDocument e-icon fitOne").TooltipText("Fit one");
            s2.Add().SpriteCssClass("PdfDocument e-icon sticky").TooltipText("Sticky");
            s2.Add().SpriteCssClass("PdfDocument e-icon readMode").TooltipText("Read Mode");

        }).Width("450px").EnableSeparator(true).ClientSideEvents(e => e.Click("click")).Render();
    }

    <br />
    <div id="contentSection">

        <textarea id="content" rows="17" cols="100" style="max-width:450px">

            Description:

            Toolbar control supports displaying a list of tools within a Web page. This control is capable of

            customizing toolbar items with any functionality by using enriched client-side methods.This control

            Is composed of collection of unordered lists containing text and images contained into a div.

        </textarea>

    </div>


{% endhighlight  %}

You can apply the following styles with the previous styles to design the PDF header and content area. 

{% highlight css %}

      <style type="text/css" class="cssStyles">

       #ctrllabel {
        height: 28px;
        width: 450px;
        color: #FFFFFF;
        box-sizing: border-box;
        padding-left: 10px;
        padding-top: 5px;
        font-weight: normal;
        background: #ff9933; /* Old browsers */
      
      }
	
</style>

{% endhighlight  %}

![Getting-Started_images0](Getting-Started-images/Getting-Started0.JPG)

PDF Reader Appearance
{:.caption}

So far, you have added the required toolbar items and configured its appearance. When you click Toolbar items, the operation is performed through client-slide click event. 

The following code example explains how to perform operations when you click the Toolbar items.

{% highlight CSHTML %}

		 <!--ej-Tag Helper code to render Toolbar-->

        <div id="ctrllabel">PDF Reader</div>
		
            <ej-toolbar id="Toolbar4" width="450px"  click="click">
                
                <e-toolbar-items>
				
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon convertToOthers" tooltip-text="Convert to others"  />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon convertToPdf" tooltip-text="convertToPdf"/>
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon signature" tooltip-text="signature"  />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon print" tooltip-text="print"/>
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon msg" tooltip-text="message" />

                </e-toolbar-items>
                <e-toolbar-items>
				
				     <e-toolbar-item sprite-css-class="PdfDocument e-icon previous" tooltip-text="Previous" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon next" tooltip-text="Next"  />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon zoomIn" tooltip-text="ZoomIn" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon zoomOut" tooltip-text="ZoomOut" />

                </e-toolbar-items>
                <e-toolbar-items>

                     <e-toolbar-item sprite-css-class="PdfDocument e-icon fitOne" tooltip-text="Fit one" group="g3" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon sticky" tooltip-text="Sticky" group="g3" />
                     <e-toolbar-item sprite-css-class="PdfDocument e-icon readMode" tooltip-text="Read Mode" group="g3" />


              </e-toolbar-items>


        </ej-toolbar>
            

{% endhighlight  %}

{% highlight Razor %}

      <!--Razor code to render Toolbar-->
   
    @{Html.EJ().Toolbar("Toolbar3").Items(s =>
        {
            s.Add().SpriteCssClass("PdfDocument e-icon convertToOthers").TooltipText("Convert to others");
            s.Add().SpriteCssClass("PdfDocument e-icon convertToPdf ").TooltipText("convertToPdf");
            s.Add().SpriteCssClass("PdfDocument e-icon signature ").TooltipText("signature");
            s.Add().SpriteCssClass("PdfDocument e-icon print").TooltipText("print");
            s.Add().SpriteCssClass("PdfDocument e-icon msg").TooltipText("message");
        }).Items(s1 =>
        {
            s1.Add().SpriteCssClass("PdfDocument e-icon previous").TooltipText("Previous");
            s1.Add().SpriteCssClass("PdfDocument e-icon next").TooltipText("Next");
            s1.Add().SpriteCssClass("PdfDocument e-icon zoomIn ").TooltipText("zoom In ");
            s1.Add().SpriteCssClass("PdfDocument e-icon zoomOut ").TooltipText("zoom Out ");


        }).Items(s2 =>
        {
            s2.Add().SpriteCssClass("PdfDocument e-icon fitOne").TooltipText("Fit one");
            s2.Add().SpriteCssClass("PdfDocument e-icon sticky").TooltipText("Sticky");
            s2.Add().SpriteCssClass("PdfDocument e-icon readMode").TooltipText("Read Mode");

        }).Width("450px").EnableSeparator(true).ClientSideEvents(e => e.Click("click")).Render();
    }

    <script>
	
    function click(args) {
	
        var option = args.currentTarget.title;
        switch (option) {

            case "Convert to others":

               
                //writes a code for Convert pdf files to Other format.

            case "convertToPdf":

                
                //writes a code for Convert files to Pdf online.

            case "signature":
                


                //writes a code for Send a document for signature.

            case "print":
               

                //writes a code for Save content.

            case "message":
              

                //writes a code for Print content.

            case "Previous":
               

                //writes a code for Send a Message.



            case "Next":
             


                //writes a code for Show Next page.

            case "ZoomOut":
               


                //writes a code for Zoom out the page.

            case "ZoomIn":
               


                //writes a code for Zoom In the page.

            case "Fit one":
                

                //writes a code for Fit one full page to window.

            case "Sticky":
               


                //writes a code for Add Sticky Note.

            case "Read Mode":
                

                //writes a code for view file in read mode.

        }

    }

    </script>
   
{% endhighlight  %}



