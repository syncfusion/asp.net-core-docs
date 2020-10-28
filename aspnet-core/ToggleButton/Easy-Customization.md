---
layout: post
title: Easy Customization | ToggleButton | ASP.NET Core | Syncfusion
description: easy customization
platform: aspnet-core
control: ToggleButton
documentation: ug
---

# Easy Customization

Toggle Button is used in all applications. ToggleButton size, content and content location is varied according to each application. The following section contains some customizable option for Toggle Button that can perform easily. 

## Toggle State

Toggle button has two states like off / on state in a switch. By default you can set any state at initial and then you can move from one state to another state by clicking on the Toggle Button. These two states are Default and Active.toggle-state property is used to set the state of Toggle Button as default state or active state. Default value of ToggleState is false.

The following steps explains you the details about rendering the Toggle Button with different ToggleState.


{% highlight CSHTML %}

/*ej-Tag Helper code to render ToggleButton*/

//Add the code in CSHTML page to configure the widget and initialize the control

@*set the state for toggle button*@

    <div class="control">
        <table>
            <tr>
                <td> <ej-toggle-button id="toggleButton_default" size="@ButtonSize.Small" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Pause" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediapause" toggle-state="false" /></td>

                <td> <ej-toggle-button id="toggleButton_active" size="@ButtonSize.Small" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Pause" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediapause" toggle-state="true" /></td>
            </tr>
        </table>
    </div>
		
{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render ToggleButton*/

<div class="control">
    <table>
        <tr>
            <td>
                @{Html.EJ().ToggleButton("toggleButton_default").Size(ButtonSize.Small).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Pause").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediapause").ToggleState(false).Render(); }</td>
            <td>
                @{Html.EJ().ToggleButton("toggleButton_active").Size(ButtonSize.Small).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Pause").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediapause").ToggleState(true).Render();}
            </td>
            </tr>
    </table>
</div>


{% endhighlight %}

N> To render the ToggleButton Control you can use either Razor or Tag helper code as given in the above code snippet.

{% highlight CSS %}

    td, th {
    padding: 5px;
}

{% endhighlight %}

Execute the above code to render the following output.

![Toggle State](Easy-Customization_images/Easy-Customization_img1.png)

Toggle button with two different toggle states
{:.caption}

## ToggleState with icons

### Prefix and Suffix Icons

You can add icons in prefix and suffix position of Toggle Button. Location of Icon is customized easily using the following mentioned option. This is applicable for the content type’s ImageOnly, TextAndImage, ImageTextImage and ImageBoth.

Toggle Button control also supports the Built-in icon libraries. The ej.widgets.core.min.css contains the definition for important icons that are used in toggle buttons. You can use these Built-in icons by mentioning the icon class name as value in default-prefix-icon, default-suffix-icon, active-prefix-icon,and active-suffix-icon property. You can use any font icons that is defined in ej.widgets.core.min.css it avoids the complexity in specifying icon using sprite image and CSS.

For example the following mentioned Built-in CSS class are used to show the font icons that are used by media player.

* e-mediaback
* e-mediaforward
* e-medianext
* e-mediaprev
* e-mediaeject
* e-mediaclose
* e-mediapause
* e-mediaplay

#### Prefix Icon

It inserts the icon at the starting position of Toggle Button. After this prefix icon, you can use text or suffix icon.

#### Suffix Icon

It inserts the icon at the ending position of Toggle Button. Before this suffix icon, you can use text or prefix icon.

You can also set icon in different location (prefix, suffix) and in different state (default, active) by using the option provided. The following properties are defined for merging the option to add text, icon with different position and in toggle states.

_Property Table_

<table>
<tr>
<th>
active-text</th><th>
Specifies the text of toggle button in active state</th></tr>
<tr>
<td>
active-prefix-icon</td><td>
Specifies the prefix icon of toggle button in active state</td></tr>
<tr>
<td>
 active-suffix-icon</td><td>
Specifies the suffix icon of toggle button in active state</td></tr>
<tr>
<td>
DefaultText</td><td>
Specifies the text of toggle button in default state.</td></tr>
<tr>
<td>
default-prefix-icon</td><td>
Specifies the prefix icon of toggle button in default state</td></tr>
<tr>
<td>
default-suffix-icon</td><td>
Specifies the suffix icon of toggle button in default state</td></tr>
</table>


The following script explains you the details about rendering the Toggle Button with above mentioned customization properties.



{% highlight CSHTML %}

/*ej-Tag Helper code to render ToggleButton*/

//Add the code in CSHTML page to configure the widget and initialize the control

    @*set the prefix, suffix built-in icons in default and active state*@
    <div class="control">
        <ej-toggle-button id="toggleButton_iconsAndStates" content-type="@ContentType.ImageTextImage" show-rounded-corner="true" default-text="forward" active-text="backward" default-prefix-icon="e-icon e-mediaforward" active-prefix-icon="e-icon e-mediaback" default-suffix-icon="e-icon e-redo" />

    </div>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render ToggleButton*/

<div class="control">

    @{Html.EJ().ToggleButton("toggleButton_iconsAndStates").ContentType(ContentType.ImageTextImage).ShowRoundedCorner(true).DefaultText("forward").ActiveText("backward").DefaultPrefixIcon("e-icon e-mediaforward").ActivePrefixIcon("e-icon e-mediaback").DefaultSuffixIcon("e-icon e-redo").Render();}

</div>


{% endhighlight %}

Execute the above code to render the following output.

![Prefix and Suffix Icons](Easy-Customization_images/Easy-Customization_img2.png)



Before clicking the toggle button
{:.caption}

![Prefix and Suffix Icons](Easy-Customization_images/Easy-Customization_img3.png)



After clicking the toggle button
{:.caption}


## Toggle button size

You can render the Toggle Button in different sizes by using size property. You can use some predefined size option for rendering a Toggle Button in easiest way. Each size option has different height and width. It mainly avoids the complexity in rendering Toggle Button with complex CSS class. You can mention the size of the Toggle Button using the following five predefined size options. 

_Predefined Toggle Button size_

<table>
<tr>
<th>
Normal</th><th>
Creates toggle button with content size.</th></tr>
<tr>
<td>
Mini</td><td>
Creates toggle button with Built-in mini size height, width specified.</td></tr>
<tr>
<td>
Small</td><td>
Creates toggle button with Built-in small size height, width specified.</td></tr>
<tr>
<td>
Medium</td><td>
Creates toggle button with Built-in medium size height, width specified.</td></tr>
<tr>
<td>
Large</td><td>
Creates toggle button with Built-in large size height, width specified.</td></tr>
</table>


You can also set your own width and height for toggle button using height and width property.

The following steps explains you the details about rendering the Toggle Button with above mentioned size options.

1. In the View page, add the following button elements to configure Toggle Button widget.

{% highlight CSHTML %}

/*ej-Tag Helper code to render ToggleButton*/

//Add the code in CSHTML page to configure the widget and initialize the control

<div class="control">

        @*Set the different size types for toggle button control as follows. *@

        <table>

            <tr>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_normal" size="@ButtonSize.Normal" show-rounded-corner="true" content-type="@ContentType.ImageOnly" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" />
                </td>
            </tr>
            <tr>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_mini" size="@ButtonSize.Mini" show-rounded-corner="true" default-text="Play" active-text="Next" />
                </td>
            </tr>
            <tr>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_small" size="@ButtonSize.Small" show-rounded-corner="true" default-text="Play" active-text="Next" />
                </td>
            </tr>
            <tr>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_medium" size="@ButtonSize.Medium" show-rounded-corner="true" default-text="Play" active-text="Next" />
                </td>
            </tr>
            <tr>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_large" size="@ButtonSize.Large" show-rounded-corner="true" default-text="Play" active-text="Next" content-type="@ContentType.TextAndImage" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" />
                </td>
            </tr>
            <tr>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_customSize" show-rounded-corner="true" default-text="Play" active-text="Next" content-type="@ContentType.TextAndImage" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" height="50" width="150" />
                </td>

            </tr>

        </table>

    </div>


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render ToggleButton*/

<div class="control">

    @*Set the different size types for toggle button control as follows. *@

    <table>

        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_normal").Size(ButtonSize.Normal).ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Render(); }

            </td>
        </tr>
        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_mini").Size(ButtonSize.Mini).ShowRoundedCorner(true).DefaultText("Play").ActiveText("Next").Render(); }

            </td>
        </tr>
        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_small").Size(ButtonSize.Small).ShowRoundedCorner(true).DefaultText("Play").ActiveText("Next").Render(); }

            </td>
        </tr>
        <tr>

            <td class="btnsht">

                @{ Html.EJ().ToggleButton("toggleButton_medium").Size(ButtonSize.Medium).ShowRoundedCorner(true).DefaultText("Play").ActiveText("Next").Render();}

            </td>
        </tr>
        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_large").Size(ButtonSize.Large).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Render(); }

            </td>
        </tr>
        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_customSize").ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Height("50").Width("150").Render();  }

            </td>

        </tr>

    </table>

</div>


{% endhighlight %}

Execute the above code to render the following output.



![Toggle button size](Easy-Customization_images/Easy-Customization_img4.png)

Toggle button in different sizes
{:.caption}

## Content type

The content of the Toggle Button is mainly text and images. Instead of using complex CSS classes to render Toggle Button with different content types, you can use some predefined content type options as listed in the following table. Using this content-type property you can easily add different types of content for Toggle Button. The Toggle Button supports the following content types.

_List of Content types_

<table>
<tr>
<th>
TextOnly</th><th>
Supports only for text content only.</th></tr>
<tr>
<td>
ImageOnly</td><td>
Supports only for image content only</td></tr>
<tr>
<td>
ImageBoth</td><td>
Supports image for both ends of the toggle button.</td></tr>
<tr>
<td>
TextAndImage</td><td>
Supports image with the text content.</td></tr>
<tr>
<td>
ImageTextImage</td><td>
Supports image with both ends and middle in text.</td></tr>
</table>


The following steps explains you the details about rendering the Toggle Button with above mentioned content type options.

1. In the View page, add the following button elements to configure Toggle Button widget.



{% highlight CSHTML %}

/*ej-Tag Helper code to render ToggleButton*/

//Add the code in CSHTML page to configure the widget and initialize the control

<div class="control">
        <table>

            <tr>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_imageOnly" show-rounded-corner="true" content-type="@ContentType.ImageOnly" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" />

                </td>
                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_textOnly" show-rounded-corner="true" default-text="Play" active-text="Next" />
                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_imageBoth" show-rounded-corner="true" content-type="@ContentType.ImageBoth" default-prefix-icon="e-icon e-mediaforward" active-prefix-icon="e-icon e-mediaback" default-suffix-icon="e-icon e-undo" active-suffix-icon="e-icon e-redo" />
                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_textAndImage" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" />
                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_imageTextImage" show-rounded-corner="true" content-type="@ContentType.ImageTextImage" default-text="forward" active-text="backward" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" default-suffix-icon="e-icon e-undo" active-suffix-icon="e-icon e-redo" />

                </td>

            </tr>

        </table>

    </div>

    <div class="small">

        <table>

            <tr>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_small_imageonly" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.ImageOnly" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" />

                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_small_textOnly" size="@ButtonSize.Small" show-rounded-corner="true" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" />
                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_small_imageBoth" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.ImageBoth" default-prefix-icon="e-icon e-mediaforward" active-prefix-icon="e-icon e-mediaback" default-suffix-icon="e-icon e-undo" active-suffix-icon="e-icon e-redo" />

                </td>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_small_textAndImage" show-rounded-corner="true" size="@ButtonSize.Small" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" />

                </td>

                <td class="btnsht">
                    <ej-toggle-button id="toggleButton_small_imageTextImage" show-rounded-corner="true" content-type="@ContentType.ImageTextImage" default-text="forward" active-text="backward" default-prefix-icon="e-icon e-mediaforward" active-prefix-icon="e-icon e-mediaback" default-suffix-icon="e-icon e-undo" active-suffix-icon="e-icon e-redo" />

                </td>

            </tr>

        </table>

    </div>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render ToggleButton*/

<div class="normal">

    @*set different content types for toggle button*@

    <table>

        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_imageOnly").ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_textOnly").ShowRoundedCorner(true).DefaultText("Play").ActiveText("Next").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_imageBoth").ShowRoundedCorner(true).ContentType(ContentType.ImageBoth).DefaultPrefixIcon("e-icon e-mediaforward").ActivePrefixIcon("e-icon e-mediaback").DefaultSuffixIcon("e-icon e-undo").ActiveSuffixIcon("e-icon e-redo").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_textAndImage").ShowRoundedCorner(true).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_imageTextImage").ShowRoundedCorner(true).ContentType(ContentType.ImageTextImage).DefaultText("forward").ActiveText("backward").DefaultPrefixIcon("e-icon e-mediaforward").ActivePrefixIcon("e-icon e-mediaback").DefaultSuffixIcon("e-icon e-undo").ActiveSuffixIcon("e-icon e-redo").Render(); }

            </td>

        </tr>

    </table>

</div>

<div class="small">

    <table>

        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_small_imageOnly").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_small_textOnly").Size(ButtonSize.Small).ShowRoundedCorner(true).DefaultText("Play").ActiveText("Next").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_small_imageBoth").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageBoth).DefaultPrefixIcon("e-icon e-mediaforward").ActivePrefixIcon("e-icon e-mediaback").DefaultSuffixIcon("e-icon e-undo").ActiveSuffixIcon("e-icon e-redo").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_small_textAndImage").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_small_imageTextImage").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageTextImage).DefaultText("forward").ActiveText("backward").DefaultPrefixIcon("e-icon e-mediaforward").ActivePrefixIcon("e-icon e-mediaback").DefaultSuffixIcon("e-icon e-undo").ActiveSuffixIcon("e-icon e-redo").Render(); }

            </td>

        </tr>

    </table>

</div>


{% endhighlight %}

Execute the above code to render the following output.

![Content type](Easy-Customization_images/Easy-Customization_img5.png)

Toggle button with different content type
{:.caption}

### ImagePosition

To provide the best look and feel for Toggle Button, position of images in toggle button is important. You can easily customize the position of images inside toggle button using image-position property without using any complex CSS. ImagePosition property is applicable only with the TextAndImage content type property. This property represent the position of images with respect to text.

_Property Table_

<table>
<tr>
<th>
ImageLeft</th><th>
Support for aligning text in right and image in left.</th></tr>
<tr>
<td>
ImageRight</td><td>
Support for aligning text in left and image in right.</td></tr>
<tr>
<td>
ImageTop</td><td>
Support for aligning text in bottom and image in top.</td></tr>
<tr>
<td>
ImageBottom</td><td>
Support for aligning text in top and image in bottom.</td></tr>
</table>


The following steps explains you the details about rendering the Toggle Button with above mentioned image Position options.

1. In the View page, add the following button elements to configure Toggle Button widget.


{% highlight CSHTML %}

/*ej-Tag Helper code to render ToggleButton*/

@*Add the code in CSHTML page to configure the widget and initialize the control*@
    <div class="one">
            <table>

            <tr>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_normal_imageLeft" size="@ButtonSize.Normal" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" image-position="@ImagePosition.ImageLeft" />
                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_normal_imageRight" size="@ButtonSize.Normal" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" image-position="@ImagePosition.ImageRight" />

                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_imageTop" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" image-position="@ImagePosition.ImageTop" height="60" width="50" />

                </td>

              

            </tr>

        </table>

    </div>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render ToggleButton*/

<div class="one">

       <table>

        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_normal_imageLeft").Size(ButtonSize.Normal).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").ImagePosition(ImagePosition.ImageLeft).Render();}

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_normal_imageRight").Size(ButtonSize.Mini).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").ImagePosition(ImagePosition.ImageRight).Render();}

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_imageTop").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").ImagePosition(ImagePosition.ImageTop).Height("60").Width("50").Render();}

            </td>
</tr>
</table>
</div>


{% endhighlight %}


Execute the above code to render the following output.


![ImagePosition](Easy-Customization_images/Easy-Customization_img6.png)

Toggle button with different type of image position
{:.caption}

## Theme support

You can control the style and appearance of Toggle Button based on CSS classes. To apply styles to the Toggle Button control, you can refer two files, ej.widgets.core.min.css and ej.theme.min.css. When you refer ej.widgets.all.min.css file, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two. 

By default, there are 12 themes support available for Toggle Button control namely,

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark

## Custom CSS

You can use the CSS to customize the Toggle Button control appearance. Define a CSS class as per requirement and assign the class name to css-class property.

The following steps explains you the details about rendering the Toggle Button with custom CSS.

1. In the View page, add the following button elements to configure Toggle Button widget.



{% highlight CSHTML %}

/*ej-Tag Helper code to render ToggleButton*/

	@*Add the code in CSHTML page to configure the widget and initialize the control*@



		@*set different custom CSS class for toggle button*@

<div class="one">


        <table>

            <tr>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_customCSS1" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" css-class="customCss1" />
                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_customCSS2" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" css-class="customCss2" />

                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_customCSS3" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" css-class="customCss3" />

                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_customCSS4" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" css-class="customCss4" />

                </td>

                <td class="btnsht">

                    <ej-toggle-button id="toggleButton_customCSS5" size="@ButtonSize.Small" show-rounded-corner="true" content-type="@ContentType.TextAndImage" default-text="Play" active-text="Next" default-prefix-icon="e-icon e-mediaplay" active-prefix-icon="e-icon e-mediaforward" css-class="customCss5" />

                </td>

            </tr>

        </table>


    </div>

{% endhighlight %}
   
{% highlight CSHTML%}

/*Razor code to render ToggleButton*/

<div class="one">

    @*apply custom CSS class for toggle buttons*@

    <table>

        <tr>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_customCSS1").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").CssClass("customCss1").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_customCSS2").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").CssClass("customCss2").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_customCSS3").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").CssClass("customCss3").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_customCSS4").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").CssClass("customCss4").Render(); }

            </td>

            <td class="btnsht">

                @{Html.EJ().ToggleButton("toggleButton_customCSS5").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).DefaultText("Play").ActiveText("Next").DefaultPrefixIcon("e-icon e-mediaplay").ActivePrefixIcon("e-icon e-mediaforward").CssClass("customCss5").Render();}

            </td>

        </tr>

    </table>

</div>


{% endhighlight %}

2. Configure the CSS styles to apply on buttons.

{% highlight CSS %}

	<style type="text/css" class="cssStyles">

			/* Customize the button background */

			.e-togglebutton.customCss1 
			{

				background-color: #121111;

			}

			.e-togglebutton.customCss2 
			{

				background-color: #94bbd5;

			}

			.e-togglebutton.customCss3 
			{

				background-color: #f3533c;

			}

			.e-togglebutton.customCss4
			{

				background-color: #d1eeed;

			}

			.e-togglebutton.customCss5 
			{

				background-color: #deb66e;

			}

			 /* Customize the button image & text color */

			.e-togglebutton.customCss1.e-btn.e-select .e-icon, .e-togglebutton.customCss1.e-btn.e-select .e-btntxt 
			{

				color: #94bbd5;

			}

			.e-togglebutton.customCss2.e-btn.e-select .e-icon, .e-togglebutton.customCss2.e-btn.e-select .e-btntxt 
			{

				color: #121111;

			}

			.e-togglebutton.customCss3.e-btn.e-select .e-icon, .e-togglebutton.customCss3.e-btn.e-select .e-btntxt 
			{

				color: #cef6f7;

			}

			.e-togglebutton.customCss5.e-btn.e-select .e-icon, .e-togglebutton.customCss5.e-btn.e-select .e-btntxt 
			{

				color: #534f4f;

			}
	    	td, th {
                padding: 5px;
         }

		</style>

{% endhighlight %}
   

Execute the above code to render the following output.



![Custom CSS](Easy-Customization_images/Easy-Customization_img7.png)

Toggle button with Custom CSS
{:.caption}



