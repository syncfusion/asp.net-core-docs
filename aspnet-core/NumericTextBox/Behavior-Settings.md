---
layout: post
title: Behavior Settings | NumericTextBox | ASP.NET Core | Syncfusion
description: behavior settings
platform: aspnet-core
control: NumericTextBox
documentation: ug
---

# Behavior Settings

## Decimal Places

DecimalPlaces property specifies number of values allowed after the decimal point.The default value of DecimalPlaces property is 0 i.e., by default you cannot specify decimal value in NumericTextBox. We need to add this property to allow decimal values. To set the DecimalPlaces to “-1”, that allows the decimals without any limit in NumericTextBox control.

### Configure Decimal Places

In the View page add the below code and configure the DecimalPlaces property as shown below.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" decimal-places="3" value="333"/>

{% endhighlight %}

The output is as follows.

![](Behavior-Settings_images/Behavior-Settings_img1.png)

## Persistence Support

NumericTextBox provides state maintenance support. You can maintain the previous changes made in the control after a page loads.

### Configure Persistence Support 

In the View page add the below code and configure the EnablePersistence property as shown below.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="11" enable-persistence="true"/>

{% endhighlight %}

Output of NumericTextBox with EnablePersistence is as follows. 

![](Behavior-Settings_images/Behavior-Settings_img2.png)

![](Behavior-Settings_images/Behavior-Settings_img3.png)

## Strict Mode Support

NumericTextBox allows you to use the strict mode option by setting the EnableStrictMode property. You can set the MinValue and MaxValue to the controls to enable strict mode functionality. Default value of this property is false. When the textbox value exceeds the MaxValue, it restricts the exceeded value and returns the MaxValue. Likewise when the textbox value goes below MinValue, it restricts the new value and returns the MinValue. When this property is enabled, it will not restrict the specified value and an error class is added to indicate wrong value is provided to the textbox.

### Configure Strict Mode Support 

In the View page add the below code and configure the EnableStrictMode property.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="10" min-value="-3" max-value="5" enable-strict-mode="true"/>

{% endhighlight %}

Output when EnableStrictMode is “true” is as follows.

![](Behavior-Settings_images/Behavior-Settings_img4.png)


## Enabled or Disabled

NumericTextBox has an option to enable or disable its element. You can set the Enabled property as “false” to enable the Textbox controls.
Also you can enable/disable the **NumericTextBox** by using [enable](https://help.syncfusion.com/api/js/ejtextboxes#methods:enable) and [disable](https://help.syncfusion.com/api/js/ejtextboxes#methods:disable) methods.

### Configure Enabled or Disabled 

In the View page add the below code and configure the Enabled property.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" enabled="false"/>

{% endhighlight %}

Output when Enabled is “true” and when Enabled is “false”.

![](Behavior-Settings_images/Behavior-Settings_img5.png)

![](Behavior-Settings_images/Behavior-Settings_img6.png)

## Adjusting Textbox Size

NumericTextBox size can be modified by using the Height and Width properties. 

Configure Height and Width 

In the View page add the below code and configure the Height and Width property.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" width="100px" height="50px"/>

{% endhighlight %}

 Output of NumericTextBox after setting “Height” and “Width” is as follows.

![](Behavior-Settings_images/Behavior-Settings_img7.png)

## Increment Step

The IncrementStep property is used to increase or decrease the amount of value in the Numeric textbox. 

### Configure Increment Step

In the View page add the below code and configure the IncrementStep property.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" increment-step="2"/>

{% endhighlight %}

Output of Numeric textbox with IncrementStep is as follows.

![](Behavior-Settings_images/Behavior-Settings_img8.png)

![](Behavior-Settings_images/Behavior-Settings_img9.png)

## Define Name

When you have placed the NumericTextBox in a form, the Name property is used to send the field value at form submission. The default value of the Name property is null.

### Configure Name

In the View page add the below code and configure the Name property.  

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" name="Numeric"/>

{% endhighlight %}

## Define Value

The value of NumericTextBox can be assigned by using the Value property. The default value for Value property is null.
You can get the value of **NumericTextBox** by using [getValue](https://help.syncfusion.com/api/js/ejtextboxes#methods:getvalue) method.

### Configure Value

In the View page add the below code and configure the Value property.  

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="12"/>

{% endhighlight %}

Output of NumericTextBox with the value property is as follows.

![](Behavior-Settings_images/Behavior-Settings_img10.png)

## Define MaxValue and MinValue

### MaxValue

The maximum limit value can be assigned to the NumericTextBox by using the MaxValue property. The default value of MaxValue property is 1.7976931348623157e+308. 

### MinValue

The minimum limit value can be assigned to the NumericTextBox by using the MinValue property. The default value of MinValue property is -1.7976931348623157e+308.

### Configure MaxValue and MinValue

In the View page add the below code and configure the MinValue and MaxValue property.  .  

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="2" min-value="-1" max-value="2"/>

{% endhighlight %}

Output of NumericTextBox with MaxValue and MinValue is as follows.

![](Behavior-Settings_images/Behavior-Settings_img11.png)

![](Behavior-Settings_images/Behavior-Settings_img12.png)

## Read Only Support

NumericTextBox supports read only option. When you enable the ReadOnly property to the control, the value cannot be changed in the NumericTextBox. You can set the ReadOnly property as “true” to enable this option.

### Configure Read Only

In the View page add the below code and configure the ReadOnly property.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" read-only="true"/>

{% endhighlight %}

Output of NumericTextBox when ReadOnly is “true” is as follows. NumericTextBox values cannot be edited or changed.

![](Behavior-Settings_images/Behavior-Settings_img13.png)

## Appearance

### Theme

NumericTextBox control’s style and appearance can be controlled based on CSS classes. In order to apply styles you need to refer 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. If the file ej.web.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.web.all.min.css is the combination of these two. 

By default, there are 17 themes support available namely:

* bootstrap
* flat-azure
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
* high-contrast-01
* high-contrast-02
* material
* office-365

### CSS Class

The CSS can be customized by using the CssClass in the NumericTextBox. You can customize the NumericTextBox with CssClass property to appear like your desired control.

#### Configure CSS Class

In the View page add the below code and configure the CssClass property. 

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" css-class="customCss"/>

{% endhighlight %}

1. Customize the CSS properties in custom CSS class.

{% highlight css %}

<style>

	.customCss .e-box {

		border-color: #9d241b;

	}

	.customCss .e-input {

		background-color: #f6db8d;            

	}

	.customCss .e-select {

		background-color: #ecf6ac;

		border-color: #3c36e7;

	}

</style>

{% endhighlight %}

Output of NumericTextBox after applying CssClass is as follows.

![](Behavior-Settings_images/Behavior-Settings_img14.png)

### Rounded Corner Support

NumericTextBox provides you with rounded corner support whose appearance is different from normal textbox controls.

#### Configure Rounded Corner Support

In the View page add the below code and configure the ShowRoundedCorner property. 

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" show-rounded-corner="true"/>

{% endhighlight %}

Output of NumericTextBox when ShowRoundedCorner is “true”.

![](Behavior-Settings_images/Behavior-Settings_img15.png)

### Spin Button Support

NumericTextBox provides you the option as to whether to display the spin button in the widget or remove it from the control by using showSpinButton property.

### Configure Spin Button

In the View page add the below code and configure the ShowSpinButton property. 

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" value="1" show-spin-button="false"/>

{% endhighlight %}

Output of NumericTextBox when ShowSpinButton is “false”.

![](Behavior-Settings_images/Behavior-Settings_img16.png)

## Water Mark Text Support

The NumericTextBox provide water mark text support. You can display the initial value in the control by water mark.

### Configure Water Mark Text

In the View page add the below code and configure the ShowSpinButton property.

{% highlight CSHTML %}

    <ej-numeric-text-box id="numeric" watermark-text="Numeric"/>

{% endhighlight %}

Output of NumericTextBox after applying WaterMarkText is as follows.

![](Behavior-Settings_images/Behavior-Settings_img17.png)