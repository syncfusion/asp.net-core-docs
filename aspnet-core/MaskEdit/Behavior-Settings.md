---
layout: post
title: Behavior Settings | MaskEdit | ASP.NET Core | Syncfusion
description: behavior settings
platform: aspnet-core
control: MaskEdit
documentation: ug
---

# Behavior Settings

## Persistence Support

MaskEditTextBox provides state maintenance support. You can maintain the previous changes made in the control after a page loads.

### Configure Persistence Support 

In the View page add MaskEditTextBox helper, and configure the EnablePersistence property as follows.


{% highlight CSHTML %}

	<ej-mask-edit id="mask" mask-format="99-999-99999" enable-persistence="true" />

{% endhighlight %}

Output of MaskEditTextBox with EnablePersistence is as follows. 



![](Behavior-Settings_images/Behavior-Settings_img1.png)

MaskEditTextBox at initial load
{:.caption}

![](Behavior-Settings_images/Behavior-Settings_img2.png)

MaskEditTextBox after changing the value and after page refresh
{:.caption}

## Enabled or Disabled

MaskEditTextBox has an option to enable or disable its element. You can set the Enabled property as “false” to enable the Textbox controls.

### Configure Enabled or Disabled 

In the View page add MaskEditTextBox helper, and configure the Enabled property.



{% highlight CSHTML %}

	<ej-mask-edit id="mask" mask-format="99-999-99999" enabled="false" />

{% endhighlight %}

Output when Enabled is “true” and when Enabled is “false”.

![](Behavior-Settings_images/Behavior-Settings_img3.png)

Textboxes with enabled as true
{:.caption}

![](Behavior-Settings_images/Behavior-Settings_img4.png)

Textboxes with enabled as false
{:.caption}

## Adjusting Textbox Size

MaskEditTextBox size can be modified by using the Height and Width properties. You can customize the size of Textbox by using these properties.

### Configure Height and Width 

MaskEditTextBox size can be modified by using the Height and Width properties. 

{% highlight CSHTML %}

	<ej-mask-edit id="mask" mask-format="99-999-99999" width="100px" height="50px" />

{% endhighlight %}

Output of MaskEditTextBox after setting “Height” and “Width” is as follows.

![](Behavior-Settings_images/Behavior-Settings_img5.png)

MaskEditTextBox with height and width
{:.caption}

## Define Value

The value of MaskEditTextBox can be assigned by using the Value property. The default value for Value property is null. Specify the [name](https://help.syncfusion.com/api/js/ejmaskedit#members:name) attribute value for the mask edit textbox.
You can get the raw value of **MaskEdit** without literals and prompt characters by using the [get_StrippedValue](https://help.syncfusion.com/api/js/ejmaskedit#methods:get_strippedvalue) method.
Also you get the value of **MaskEdit** with the masked format by using the [get_UnstrippedValue](https://help.syncfusion.com/api/js/ejmaskedit#methods:get_unstrippedvalue) method.

### Configure Value

In the View page add MaskEditTextBox helper, and configure the Value property 

{% highlight CSHTML %}

	<ej-mask-edit id="mask" mask-format="99-999-99999" value="1234567890" />

{% endhighlight %}



Output of MaskEditTextBox with the value property is as follows.


![](Behavior-Settings_images/Behavior-Settings_img6.png)

MaskEditTextBox with value
{:.caption}

## Read Only Support

MaskEditTextBox supports read only option. When you enable the ReadOnly property to the control, the value cannot be changed in the MaskEditTextBox. You can set the ReadOnly property as “true” to enable this option.

### Configure Read Only

In the View page add MaskEditTextBox helper, and configure the ReadOnly property.

{% highlight CSHTML %}

	<ej-mask-edit id="mask" mask-format="99-999-99999" value="123456" read-only="true" />

{% endhighlight %}

Output of MaskEditTextBox when ReadOnly is “true” is as follows. MaskEditTextBox values cannot be edited or changed.



![](Behavior-Settings_images/Behavior-Settings_img7.png)

MaskEditTextBox with readOnly 
{:.caption}

## Error Visibility

The MaskEditTextBox has an option that shows the error value with red colored text. It is used to validate the Mask Edit value. You can set the ShowError property as “true” to enable this option.

### Configure Error Visibility

In the View page use the corresponding Textbox helper for rendering Textbox controls. 



{% highlight CSHTML %}

	@* Add the following code in your view page to render Textbox controls.*@

	<ej-mask-edit id="mask" mask-format="99-999-99999" value="123456" show-error="true" />

{% endhighlight %}

Output for MaskEditTextBox when ShowError is “true” is as follows. 



![](Behavior-Settings_images/Behavior-Settings_img8.png)

Textbox with showError
{:.caption}


![](Behavior-Settings_images/Behavior-Settings_img9.png)

Textbox without error
{:.caption}

## Mask Edit Properties

### Custom Character

The MaskEdit allows you to use the custom character option. You can define any of the non-mask element as the mask element  through the customCharacters property.The specified character is allowed to enter in the Mask Edit Textbox by using the CustomCharacter property.Non-mask element  accepts the values as mentioned in the custom characters collection.

### Hide Prompt On Leave

The MaskEditTextBox provides the option to hide the prompt when you focus out from the control. The mask prompt is visible when you focus again to the control. The default value of HidePromptOnLeave is false.

### Input Mode

The MaskEdit supports two type of inputs such as text and password that have been assigned by using the enum values ej.InputMode.Text and ej.InputMode.Password. The default value for InputMode is text in MaskEdit.

### Mask Format

The MaskEdit provides the option to define the MaskFormat to the value. The default value for MaskFormat property is empty string.

The following steps explain the implementation of MaskEdit Properties.

In the View page use the corresponding Textbox helper for rendering MaskEdit control. 



{% highlight CSHTML %}

	@* Add the following code in your view page to render Textbox controls.*@

	<ej-mask-edit id="mask" mask-format="99-999-CCCC" custom-character="r" hide-prompt-on-leave="true" input-mode="Text" />

{% endhighlight %}



The output for MaskEditTextBox with its properties is as follows.

![](Behavior-Settings_images/Behavior-Settings_img10.png)

MaskEdit with MaskFormat
{:.caption}


![](Behavior-Settings_images/Behavior-Settings_img11.png)

MaskEdit with HidePromptOnLeave
{:.caption}



![](Behavior-Settings_images/Behavior-Settings_img12.png)

MaskEdit with prompt focus
{:.caption}



![](Behavior-Settings_images/Behavior-Settings_img13.png)

MaskEdit with InputMode text
{:.caption}



![](Behavior-Settings_images/Behavior-Settings_img14.png)

MaskEdit with CustomCharacter
{:.caption}

## Appearance

### Theme

The MaskEditTextBox control’s style and appearance can be controlled based on CSS classes. In order to apply styles to the Textbox control, you need to refer 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. If the file ej.web.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.web.all.min.css is the combination of these two. 

By default, there are 17 themes support available for Textbox control namely:

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
* bootstrap
* high-contrast-01
* high-contrast-02
* office-365
* material


### CSS Class

The CSS can be customized by using the CssClass in the MaskEditTextBox. You can customize the MaskEditTextBox with CssClass property to appear like your desired control.

#### Configure CSS Class

1. In the View page add MaskEditTextBox helper, and configure the CssClass property. 


   ~~~ cshtml

	<ej-mask-edit id="mask" mask-format="99-999-99999" value="123456" css-class="customCss" />

   ~~~
   

2. Customize the CSS properties in custom CSS class.

   ~~~ css
   
	<style>

		.customCss .e-box 
		{

			border-color: #9d241b;

		}

		.customCss .e-input 
		{

			background-color: #f6db8d;            

		}

		.customCss .e-select 
		{

			background-color: #ecf6ac;

			border-color: #3c36e7;

		}

	</style>

   ~~~
   

The output for MaskEditTextBox after applying CssClass is as follows.



![](Behavior-Settings_images/Behavior-Settings_img15.png)

Textboxes with cssClass
{:.caption}

### Rounded Corner Support

MaskEditTextBox provides you with rounded corner support whose appearance is different from normal textbox controls.

#### Configure Rounded Corner Support

In the View page add MaskEditTextBox helper, and configure the ShowRoundedCorner property. 



{% highlight CSHTML %} 

	<ej-mask-edit id="mask" value="123456" show-rounded-corner="true" />

{% endhighlight %}

Output of MaskEditTextBox when ShowRoundedCorner is “true”.

![](Behavior-Settings_images/Behavior-Settings_img16.png)

Textboxes with showRoundedCorner
{:.caption}

### Water Mark Text Support

The Textboxes provide water mark text support. You can display the initial value in the control by water mark.

#### Configure Water Mark Text

In the View page use the corresponding Textbox helper for rendering Textbox controls. 

{% highlight CSHTML %} 

	<ej-mask-edit id="mask" mask-format="99-999-99999" watermark-text="MaskEdit" />

{% endhighlight %}

Output of MaskEditTextBox with watermark text.

![](Behavior-Settings_images/Behavior-Settings_img17.png)

MaskEditTextBox with watermark text
{:.caption}

### Text Alignment Support

The MaskEditTextBox provides text alignment support that allows you to set the alignment of text in the control by using the TextAlign property.

#### Configure Text Alignment

In the View page use the corresponding MaskEdit helper for rendering MaskEdit control. 



{% highlight CSHTML %}

	<ej-mask-edit id="mask" mask-format="99-999-99999" value="12345677"text-align="Right" />

{% endhighlight %}

The output for Textboxes when TextAlign is set to “right”.

![](Behavior-Settings_images/Behavior-Settings_img18.png)

MaskEditTextBox with textAlign
{:.caption}

### HTML Attributes Support

The MaskEditTextBox provides support for adding HTML attributes to the component. ‘HtmlAttributes’ property is used to add HTML attributes like, id, class etc.. to the components. We need to use IDictionary<string,object> to specify the HTML attributes. 

#### Configure HTMLAttributes property

1. In the View page add MaskEditTextBox helper, and configure the HtmlAttributes property. Here we have added the [Access key](http://en.wikipedia.org/wiki/Access_key) attribute. While pressing the “AccessKey” and “J” keys, MaskEditTextBox will gain focus.



   ~~~ cshtml

	@{IDictionary<string, object> maskAttribute = new Dictionary<string, object>();

	maskAttribute.Add("accesskey", "j");

	}
	
	<ej-mask-edit id="mask" mask-format="99-999-99999" html-attributes="maskAttribute" />

   ~~~
   


2. Add the following JavaScript code to focus the MaskEditTextBox

   ~~~ js

	<script type="text/javascript">

	$(function () 
	{

		$(document).on("keydown", function (e) 
		{

			if (e.altKey && e.keyCode === 74) 
			
			{ // j- key code.

				$("#mask").focus();

			}

		});

	});

	</script>

   ~~~
   

The output for MaskEditTextBox after configuring the HtmlAttributes property

![](Behavior-Settings_images/Behavior-Settings_img19.png)

MaskEditTextBox with focus
{:.caption}





