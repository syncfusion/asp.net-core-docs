---
layout: post
title: Getting Started | NumericTextBox | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: NumericTextBox
documentation: ug
---

# Getting Started

This section explains briefly about how to create a NumericTextBox in ASP.NET Core application.

## Create your first NumericTextBox in ASP.NET Core

From the following steps you can learn how to create and use NumericTextBox in your application. Here we have showcased, a small Electric bill calculator application using ASP.NET Core Editors widgets.The Essential ASP.NET Core Editors control includes Numeric, Percentage, Currency and MaskEdit textbox controls. This will guide you to use the wide range of Editors functionalities to complete this application. 

![](Getting-Started_images/Getting-Started_img1.png)



## Create Editors 

ASP.NET Core Editors renders built-in features like keyboard navigation, min and max range and flexible API’s. 

1. Create an ASP.NET Core Project and add Syncfusion assembly packages and Scripts. Refer [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/getting-started).
2. Add necessary Tag helper elements to render the Editor components.

   ~~~ cshtml

    <div class="editors">

        <div class="element-icon"></div>

        <div class="element-text" style="">Electricity Bill Calculator</div>

        <br />

        <table class="editors">

            <tbody>

                <tr>

                    <td>

                        <label>Unit meters</label>

                    </td>

                    <td>
                        @* NumericTextBox creation with watermark text *@

                        <ej-numeric-text-box id="numeric" watermark-text="Units" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Service Tax</label>

                    </td>

                    <td>
                        @* PercentageTextBox creation with watermark text *@

                        <ej-percentage-text-box id="percent" watermark-text="Tax" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Fare</label>

                    </td>

                    <td>
                        @* CurrencyTextBox creation with watermark text *@

                        <ej-currency-text-box id="currency" watermark-text="Amount per unit" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Mobile No</label>

                    </td>

                    <td>
                        @* MaskEditTextBox creation with watermark text *@

                        <ej-mask-edit id="maskedit" watermark-text="Phone number" />

                    </td>

                </tr>

            </tbody>
        </table>

        <div class="pay-bill">

            <ej-button id="btn" size="@ButtonSize.Small" text="Calculate" content-type="@ContentType.TextAndImage" prefix-icon="e-calender" />

        </div>

    </div>
	
   ~~~
Razor code to render NumericTextBox

 ~~~ cshtml

@{Html.EJ().NumericTextBox("numeric").Render();}

~~~

3. The following styles are added to arrange the Editors.  You can add the following location in the URL path for the background image and to apply styling [http://js.syncfusion.com/UG/Web/Content/electricity.png](http://js.syncfusion.com/UG/Web/Content/electricity.png)

   ~~~ css

	<style type="text/css" class="cssStyles">

		.element-icon

		{

			display: inline-block;

			background-image: url(http://js.syncfusion.com/UG/Web/Content/electricity.png);

			background-repeat: no-repeat;

			background-size: contain;

			height: 50px;

			width: 50px;

			margin-left:50px;

			margin-top:15px;

		}

		.element-text

		{

			display: inline-block;

			font-size: 20px;

			font-weight: bolder;

			height: 50px;

			position: relative;

			text-align: center;

			top: -20px;

		}

		.editors

		{

			max-width: 400px;

			border: 2px solid #DDDDDD;

		}

			.editors table

			{

				border:0px;

				padding-left:50px;

			}

		.pay-bill

		{

			margin:15px 0px 10px 208px;

		}

		.editors label

		{

			display: block;

			width: 130px;

		}

	</style>

   ~~~
   

4. Execute the code to render Editors as follows



![](Getting-Started_images/Getting-Started_img2.png)

NumericTextBox with watermark text
{:.caption}

## Set MinValue, MaxValue and value in NumericTextBox

You can set the “MinValue”,“MaxValue” and “Value” in Numeric, Percentage and Currency text boxes for maintaining the range in Editors widgets. In this scenario, you have to enter the values between the default ranges and enter the phone number in the MaskEdit widget by using the ”MaskFormat” property. By using DecimalPlaces property for CurrencyTextBox you can get decimal values. The following code example illustrates how to achieve this.

{% highlight CSHTML %}

    <div class="editors">

        <div class="element-icon"></div>

        <div class="element-text" style="">Electricity Bill Calculator</div>

        <br />

        <table class="editors">

            <tbody>

                <tr>

                    <td>

                        <label>Unit meters</label>

                    </td>

                    <td>                        

                        <ej-numeric-text-box id="numeric" watermark-text="Units" min-value="1" max-value="10000" value="70" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Service Tax</label>

                    </td>

                    <td>                        

                        <ej-percentage-text-box id="percent" watermark-text="Tax" min-value="5" max-value="100" value="15" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Fare</label>

                    </td>

                    <td>                       

                        <ej-currency-text-box id="currency" watermark-text="Amount per unit" min-value="0.00" max-value="100000.00" value="350.00" decimal-places="2" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Mobile No</label>

                    </td>

                    <td>                        

                        <ej-mask-edit id="maskedit" watermark-text="Phone number" mask-format="99-999-99999" value="9090909090"/>

                    </td>

                </tr>

            </tbody>
        </table>

        <div class="pay-bill">

            <ej-button id="btn" size="@ButtonSize.Small" text="Calculate" content-type="@ContentType.TextAndImage" prefix-icon="e-calender" />

        </div>

    </div>

{% endhighlight %}

The following screenshot illustrates the output of the above code examples. 

![](Getting-Started_images/Getting-Started_img3.png)



## Setting the Strict Mode Option

You can set the “StrictMode” option to restrict entering values defined outside the range. The following code example illustrates how to set strict mode option. 

{% highlight CSHTML %}

    <div class="editors">

        <div class="element-icon"></div>

        <div class="element-text" style="">Electricity Bill Calculator</div>

        <br />

        <table class="editors">

            <tbody>

                <tr>

                    <td>

                        <label>Unit meters</label>

                    </td>

                    <td>                       

                        <ej-numeric-text-box id="numeric" watermark-text="Units" min-value="1" max-value="10000" value="70" enable-strict-mode="true" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Service Tax</label>

                    </td>

                    <td>                        

                        <ej-percentage-text-box id="percent" watermark-text="Tax" min-value="5" max-value="100" value="15" />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Fare</label>

                    </td>

                    <td>                        

                        <ej-currency-text-box id="currency" watermark-text="Amount per unit" min-value="0.00" max-value="100000.00" value="350.00" decimal-places="2"  />

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Mobile No</label>

                    </td>

                    <td>                        

                        <ej-mask-edit id="maskedit" watermark-text="Phone number" mask-format="99-999-99999" value="9090909090"/>

                    </td>

                </tr>

            </tbody>
        </table>

        <div class="pay-bill">

            <ej-button id="btn" size="@ButtonSize.Small" text="Calculate" content-type="@ContentType.TextAndImage" prefix-icon="e-calender" />

        </div>

    </div>

{% endhighlight %}

Run the above code example and you can see that it restricts entering a value exceeding the MinValue and MaxValue range mentioned in the Numeric textbox.

## Set Calculation process with NumericTextBox Widgets

You can use events to calculate the total and displays the value. You can achieve this with the help of Click event in the button widget. The calculation steps are written in the call back function of Click event button.

To customize the button, set the ContentType as TextAndImage to include the icon before the text. Add the PrefixIcon value as “e-calender” and add the ClientSideEvents for click event.

{% highlight CSHTML %}

   <div class="editors">

    @* Please refer the table format for textboxes customization *@

    <div class="pay-bill">

        <ej-button id="btn" size="@ButtonSize.Small" text="Calculate" content-type="@ContentType.TextAndImage" prefix-icon="e-calender"  click="calculateBill"/>
      
    </div>

</div>


<script type="text/javascript">   

function calculateBill() {

        // Declares Necessary variable creation 

        var unitMeter, serviceTax, amountPerKm;

        unitMeter = $("#numeric").data("ejNumericTextbox");// Object of Numeric 

        serviceTax = $("#percent").data("ejPercentageTextbox");// Object of Percentage

        amountPerKm = $("#currency").data("ejCurrencyTextbox"); // Object of Currency

        mobileNumber = $("#maskedit").data("ejMaskEdit"); // Object of MaskEdit        

        // This is used to calculate the Net amount

        var netAmount = unitMeter.model.value * amountPerKm.model.value;

        // This is used to calculate the service tax amount

        var sTax = (netAmount * serviceTax.model.value) / 100;

        // This shows the calculated amount for the units

        alert("The amount $" + (netAmount + sTax) + " has been sent as message to " + mobileNumber.model.value + ".");

    }

</script>

{% endhighlight %}

Run the above code sample, fill the required Textbox fields and click the Calculate button. The values are displayed and an alert message is shown. The following screen shot illustrates the final output of the Electricity bill calculator. 

![](Getting-Started_images/Getting-Started_img4.png)



