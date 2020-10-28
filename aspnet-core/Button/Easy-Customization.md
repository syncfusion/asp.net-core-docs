---
layout: post
title: Easy Customization | Button | ASP.NET Core | Syncfusion
description: easy customization
platform: aspnet-core
control: Button
documentation: ug
---

# Easy Customization

Button is used in all applications. Button size, content and content location is varied according to each application. Here you can see some customizable option for button that can perform easily. 

## Button Size

You can render the button in different sizes. Here, you have some predefined size options for rendering a button with different sizes in easiest way. Each size option has different height and width. Mainly it avoids the complexity in rendering button with complex CSS class. 

_List of predefined button size_

<table>
<tr>
<td>
Normal</td><td>
Creates button with content size.</td></tr>
<tr>
<td>
Mini</td><td>
Creates button with Built-in mini size height, width specified.</td></tr>
<tr>
<td>
Small</td><td>
Creates button with Built-in small size height, width specified.</td></tr>
<tr>
<td>
Medium</td><td>
Creates button with Built-in medium size height, with specified.</td></tr>
<tr>
<td>
Large</td><td>
Creates button with Built-in large size height, width specified.</td></tr>
</table>
Apart from the above mentioned predefined size option, you can set your own width and height for button using Height and Width property.

The following steps explains you the details about rendering the button with different size options.

1. In the CSHTML page, configure the button widget as follows.

{% highlight CSHTML%}

/*ej-Tag Helper code to render Button*/

@*Add the code in CSHTML page to configure and initialize the control*@

@*Set the different size types for button control as follows.*@

<div class="control">        
	
	<ej-button id="button_normal" text="login" size="Normal" show-rounded-corner="true" content-type="ImageOnly" prefix-icon="e-icon e-handup" />
    <ej-button id="button_mini" text="login" size="Mini" show-rounded-corner="true"/>
    <ej-button id="button_small" text="login" size="Small" show-rounded-corner="true" />
    <ej-button id="button_medium" text="login" size="Medium" show-rounded-corner="true" />
    <ej-button id="button_large" text="login" size="Large" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" />
    <ej-button id="button_customSize" text="login" size="Normal" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" height="50" width="50"/>


</div>

{% endhighlight  %}


{% highlight html %}

/*Razor code to render Button*/

<div class="control">

     @{ Html.EJ().Button("button_normal").Text("login").Size(ButtonSize.Normal).ShowRoundedCorner(true).ContentType(ContentType.ImageBoth).PrefixIcon("e-icon e-handup").Render();  }
     @{ Html.EJ().Button("button_mini").Text("login").Size(ButtonSize.Mini).ShowRoundedCorner(true).Render();  }
     @{ Html.EJ().Button("button_small").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).Render(); }
     @{ Html.EJ().Button("button_medium").Text("login").Size(ButtonSize.Medium).ShowRoundedCorner(true).Render(); }
     @{ Html.EJ().Button("button_large").Text("login").Size(ButtonSize.Large).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").Render(); }
     @{ Html.EJ().Button("button_customSize").Text("login").Size(ButtonSize.Normal).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").Height("50").Width("50").Render(); }

</div>

{% endhighlight %}

N> To render the Button Control you can use either Razor or Tag helper code as given in the above code snippet.

Execute the above code to render the following output.

![](Easy-Customization_images/Easy-Customization_img1.png)

Button with different sizes
{:.caption}

## Content Type

The content of the Button is mainly text and images. Instead of using complex CSS classes to render Button with different content types, you can use some predefined content type options provided for button control. Using this content types you can easily add different types of content for button. Button supports the following content types.

_List of content types for button_

<table>
<tr>
<td>
TextOnly</td><td>
Supports only for text content only.</td></tr>
<tr>
<td>
ImageOnly</td><td>
Supports only for image content only</td></tr>
<tr>
<td>
ImageBoth</td><td>
Supports image for both ends of the button.</td></tr>
<tr>
<td>
TextAndImage</td><td>
Supports image with the text content.</td></tr>
<tr>
<td>
ImageTextImage</td><td>
Supports image with both ends and middle in text.</td></tr>
</table>

## Prefix and Suffix icons

Icons inside the Button is added easily using PrefixIcon and SuffixIcon property. Location of the icon in button is a necessary thing and you can easily customize it using the following mentioned options.

Button control also supports the Built-in icon libraries. The ej.widgets.core.min CSS contains definitions for important icons that can be used in buttons. Simply you can use these Built-in icons by mentioning the icon class name as value in PrefixIcon and SuffixIcon property. You can use any font icons that are defined in ej.widgets.core.minCSS. It avoids the complexity in specifying icon using sprite image and CSS.

For example the following mentioned Built-in CSS class are used to show the font icons that is used by media player.

e-mediaback

e-mediaforward

e-medianext

e-mediaprev

e-mediaeject

e-mediaclose

e-mediapause

e-mediaplay

### Prefix Icon

It inserts the icon at the starting position of button. After this prefix icon, you can use text or suffix icon.

### Suffix Icon

It inserts the icon at the ending position of button. Before this suffix icon, you can use text or prefix icon.

The following steps explains you the details about rendering the Button with above mentioned content type, prefix and suffix icon options

1. In the View page, configure the Button widget as follows.

   ~~~ cshtml

    /*ej-Tag Helper code to render Button*/

	@*Add the code in CSHTML page to configure and initialize the control*@

	@* Set the different content types and use the necessary build-in icons for button control as follows.*@

	<div class="control">           

	<ej-button id="button_imageOnly" text="login" show-rounded-corner="true" content-type="ImageOnly" prefix-icon="e-icon e-handup" />
    <ej-button id="button_textOnly" text="login" content-type="TextOnly" show-rounded-corner="true"/>
    <ej-button id="button_imageBoth" text="login" content-type="ImageBoth" show-rounded-corner="true" prefix-icon="e-icon e-handup" suffix-icon="e-icon e-palette" />
    <ej-button id="button_textAndImage" text="login" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" />
    <ej-button id="button_imageTextImage" text="login" show-rounded-corner="true" content-type="ImageTextImage" prefix-icon="e-icon e-handup" suffix-icon="e-icon e-palette" />

		<br />

		<br />

    <ej-button id="button_small_imageOnly" text="login" size="Small" show-rounded-corner="true" content-type="ImageOnly" prefix-icon="e-icon e-handup" />
    <ej-button id="button_small_textOnly" text="login" size="Small" content-type="TextOnly" show-rounded-corner="true"/>
    <ej-button id="button_small_imageBoth" text="login" size="Small" content-type="ImageBoth" show-rounded-corner="true" prefix-icon="e-icon e-handup" suffix-icon="e-icon e-palette" />
    <ej-button id="button_small_textAndImage" text="login" size="Small" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" />
    <ej-button id="button_small_imageTextImage" text="login" size="Small" show-rounded-corner="true" content-type="ImageTextImage" prefix-icon="e-icon e-handup" suffix-icon="e-icon e-palette" />


   


	</div>

   ~~~
{% highlight html %}

/*Razor code to render Button*/

<div class="control">

     @{ Html.EJ().Button("button_imageOnly").Text("login").ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).PrefixIcon("e-icon e-handup").Render(); }
	 @{ Html.EJ().Button("button_textOnly").Text("login").ContentType(ContentType.TextOnly).ShowRoundedCorner(true).Render(); }
	 @{ Html.EJ().Button("button_imageBoth").Text("login").ContentType(ContentType.ImageBoth).ShowRoundedCorner(true).PrefixIcon("e-icon e-handup").SuffixIcon("e-icon e-palette").Render(); }
	 @{ Html.EJ().Button("button_textAndImage").Text("login").ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").Render(); }
	 @{ Html.EJ().Button("button_imageTextImage").Text("login").ShowRoundedCorner(true).ContentType(ContentType.ImageTextImage).PrefixIcon("e-icon e-handup").SuffixIcon("e-icon e-palette").Render(); }
<br />
<br />
	 @{ Html.EJ().Button("button_small_imageOnly").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).PrefixIcon("e-icon e-handup").Render(); }
	 @{ Html.EJ().Button("button_small_textOnly").Text("login").Size(ButtonSize.Small).ContentType(ContentType.TextOnly).ShowRoundedCorner(true).Render(); }
	 @{ Html.EJ().Button("button_small_imageBoth").Text("login").Size(ButtonSize.Small).ContentType(ContentType.ImageBoth).ShowRoundedCorner(true).PrefixIcon("e-icon e-handup").SuffixIcon("e-icon e-palette").Render(); }
	 @{ Html.EJ().Button("button_small_textAndImage").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").Render(); }
   	 @{ Html.EJ().Button("button_small_imageTextImage").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageTextImage).PrefixIcon("e-icon e-handup").SuffixIcon("e-icon e-palette").Render(); }
		
</div>

{% endhighlight %}

N> To render the Button Control you can use either Razor or Tag helper code as given in the above code snippet.


	 Execute the above code to render the following output.

	 ![](Easy-Customization_images/Easy-Customization_img2.png)
     
	 Button with different content types
	 {:.caption}

   ## Image Position

	To provide the best look and feel for Button, position of button images is an important customizable option. With ImagePosition property you can easily customize the position of images inside button without using any complex CSS. ImagePosition property is applicable only with the TextAndImageContentType property. This property supports the following values.

	_List of values supported by ContentType property_

	<table>
	<tr>
	<td>
	ImageLeft</td><td>
	Support for aligning text in right and image in left.</td></tr>
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


	The following steps explains you the details about rendering the Button with the above mentioned image Position options.

2. In the CSHTML page, configure the Button widget as follows.


   ~~~ cshtml
    
	/*ej-Tag Helper code to render Button*/

	@*Add the code in CSHTML page to configure and initialize the control*@



	@* Set the different image position for button control as follows.*@

	<div class="control">

    <ej-button id="button_normal_left" text="login" size="Normal" show-rounded-corner="true" content-type="ImageOnly" prefix-icon="e-icon e-handup" image-position="ImageLeft" />
    <ej-button id="button_mini_left" text="login" size="Mini" show-rounded-corner="true" image-position="ImageLeft"  />
    <ej-button id="button_small_left" text="login" size="Small" show-rounded-corner="true" image-position="ImageLeft" />
    <ej-button id="button_medium_left" text="login" size="Medium" show-rounded-corner="true" image-position="ImageLeft" />
    <ej-button id="button_large_left" text="login" size="Large" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageLeft" />

		<br />

		<br />

    <ej-button id="button_normal_right" text="login" size="Normal" show-rounded-corner="true" content-type="ImageOnly" prefix-icon="e-icon e-handup" image-position="ImageRight" />
    <ej-button id="button_mini_right" text="login" size="Mini" show-rounded-corner="true" image-position="ImageRight"  />
    <ej-button id="button_small_right" text="login" size="Small" show-rounded-corner="true" image-position="ImageRight" />
    <ej-button id="button_medium_right" text="login" size="Medium" show-rounded-corner="true" image-position="ImageRight" />
    <ej-button id="button_large_right" text="login" size="Large" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageRight" />

		<br />

		<br />

    <ej-button id="button_imageTop" text="login" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageTop"/>
    <ej-button id="button_imageBottom" text="login" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageBottom" />


	</div>

   ~~~
  
{% highlight html %}

/*Razor code to render Button*/

<div class="control">

	 @{ Html.EJ().Button("button_normal_left").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).Render(); }
	 @{ Html.EJ().Button("button_mini_left").Text("login").Size(ButtonSize.Mini).ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageLeft).Render(); }
	 @{ Html.EJ().Button("button_small_left").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageLeft).Render(); }
	 @{ Html.EJ().Button("button_medium_left").Text("login").Size(ButtonSize.Medium).ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageLeft).Render(); }
	 @{ Html.EJ().Button("button_large_left").Text("login").Size(ButtonSize.Large).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).Render(); }
<br />
<br />
	 @{ Html.EJ().Button("button_normal_right").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.ImageOnly).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageRight).Render(); }
	 @{ Html.EJ().Button("button_mini_right").Text("login").Size(ButtonSize.Mini).ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageRight).Render(); }
	 @{ Html.EJ().Button("button_small_right").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageRight).Render(); }
	 @{ Html.EJ().Button("button_medium_right").Text("login").Size(ButtonSize.Medium).ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageRight).Render(); }
	 @{ Html.EJ().Button("button_large_right").Text("login").Size(ButtonSize.Large).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageRight).Render(); }
<br />
<br />
	 @{ Html.EJ().Button("button_imageTop").Text("login").ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageTop).Render(); }
	 @{ Html.EJ().Button("button_imageBottom").Text("login").ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageBottom).Render();}

</div>


{% endhighlight %}


	Execute the above code to render the following output.

	![](Easy-Customization_images/Easy-Customization_img3.png)

    Button with different image positions
	{:.caption}

   ### Theme support

	You can control the style and appearance of Button control based on CSS classes. In order to apply styles to the Button control, you can refer two files namely, ej.widgets.core.min.css and ej.theme.min.css. When you refer the ej.widgets.all.min.css file, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two. 

	By default, there are 12 themes support available for Button control.

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

   ### Custom CSS

	You can customize the appearance of Button control using CSS class. Define a CSS class as per requirement and assign the class name to CssClass property.

	The following steps explains you the details about rendering the Button with custom CSS.

3. In the CSHTML page, configure the Button widget as follows.

   ~~~ cshtml
 
 
    /*ej-Tag Helper code to render Button*/

	@*Add the code in CSHTML page to configure and initialize the control*@



	@* Set Custom CSS class for button control as follows.*@

	<div class="control">



	<ej-button id="customCss1" text="login" size="Small" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageLeft" css-class="customCss1"/>
    <ej-button id="customCss2" text="login" size="Small" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageLeft" css-class="customCss2" />
    <ej-button id="customCss3" text="login" size="Small" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageLeft" css-class="customCss3" />
    <ej-button id="customCss4" text="login" size="Small" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageLeft" css-class="customCss4" />
    <ej-button id="customCss5" text="login" size="Small" show-rounded-corner="true" content-type="TextAndImage" prefix-icon="e-icon e-handup" image-position="ImageLeft" css-class="customCss5" />




	</div>

   ~~~
  
{% highlight html %}

/*Razor code to render Button*/

<div class="control">

	 @{ Html.EJ().Button("customCss1").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).CssClass("customCss1").Render(); }
	 @{ Html.EJ().Button("customCss2").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).CssClass("customCss2").Render(); }
	 @{ Html.EJ().Button("customCss3").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).CssClass("customCss3").Render(); }
	 @{ Html.EJ().Button("customCss4").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).CssClass("customCss4").Render(); }
	 @{ Html.EJ().Button("customCss5").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").ImagePosition(ImagePosition.ImageLeft).CssClass("customCss5").Render(); }
	 
</div>


{% endhighlight %}

4. Configure the CSS styles to apply on buttons.

   ~~~ css 

	<style type="text/css" class="cssStyles">

		/* Customize the button background */

		.e-button.customCss1 {

			background-color: #121111;

		}

		.e-button.customCss2 {

			background-color: #94bbd5;

		}

		.e-button.customCss3 {

			background-color: #f3533c;

		}

		.e-button.customCss4 {

			background-color: #d1eeed;

		}

		.e-button.customCss5 {

			background-color: #deb66e;

		}

		 /* Customize the button image & text color */

		.e-button.customCss1.e-btn.e-select .e-icon, .e-button.customCss1.e-btn.e-select .e-btntxt {

			color: #94bbd5;

		}

		.e-button.customCss2.e-btn.e-select .e-icon, .e-button.customCss2.e-btn.e-select .e-btntxt {

			color: #121111;

		}

		.e-button.customCss3.e-btn.e-select .e-icon, .e-button.customCss3.e-btn.e-select .e-btntxt {

			color: #cef6f7;

		}

		.e-button.customCss5.e-btn.e-select .e-icon, .e-button.customCss5.e-btn.e-select .e-btntxt {

			color: #534f4f;

		}

	</style>

   ~~~
  

Execute the above code to render the following output.

![](Easy-Customization_images/Easy-Customization_img4.png)

Button with Custom CSS
{:.caption}
