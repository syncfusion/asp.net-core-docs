---
layout: post
title: Getting Started with ASP.NET Core MaskEdit control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core MaskEdit control, its elements, and more.
platform: aspnet-core
control: MaskEdit
documentation: ug
---

# Getting Started with ASP.NET Core MaskEdit

This section explains you briefly on how to create a MaskEdit control in your ASP.NET Core application.



## Create your first MaskEdit Widget in ASP.NET Core

ASP.NET Core MaskEdit control allows you to set the type and format of the input mask that is used in the textbox and also the number of place holders. Using the following guidelines, you can create MaskEdit control for a real-time payment application.

The following screenshot illustrates the functionality of a MaskEdit. Using MaskEdit control textbox, you can enter only the assigned text format and no other formats. The input mask prevents you from entering invalid characters into the control. In this application, MobileNumber textbox has a mask value.

![Getting-Started_images1](Getting-Started_images/Getting-Started_img1.png)

MaskEdit
{:.caption}

In the above screenshot, you can type only numbers and it does not allow text format.

### Create a MaskEdit control

ASP.NET Core MaskEdit control renders built-in features like text masking, number masking and flexible APIs. You can easily create the MaskEdit control using simple HTML helper class as follows:

1. Create an ASP.NET Core Project and add Syncfusion assembly packages, styles and scripts to it. Refer [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0)
2. Add the following code to the corresponding view page to render MaskEdit.



   ~~~ cshtml

   /*ej-Tag Helper code to render MaskEdit*/

    <div class="frame">

        <div class="control">

            <table class="editors">

                <tbody>

                    <tr>

                        <td>

                            <label>

                                Mobile No

                            </label>

                        </td>

                        <td>

                            @*creating MaskEdit control*@
                       
                            <ej-mask-edit id="maskedit" mask-format="99-999-99999" input-mode="@InputMode.Text" />

                        </td>

                    </tr>

                </tbody>

            </table>

            <div class="payBill">

                <ej-button id="btn" size="@ButtonSize.Small" text="PayBill" />            

            </div>

        </div>

    </div>
	
   ~~~

## Razor code to render MaskEdit

~~~ cshtml

@{Html.EJ().MaskEdit("mask").MaskFormat("99-999-99999").Render();}

~~~

N>To render the MaskEdit Control you can use either Razor or Tag helper code as given in the above code snippet. For more information about ej-tag helper you can refer [ASP.NET Core-ejTagHelpers](https://help.syncfusion.com/aspnet-core/ejtaghelpers)



3. Add the following styles to show MaskEdit and place it in a particular position.

   ~~~ css

	<style>

		.frame 
		{

			width: 300px;

		}



		.editors 
		{

			max-width: 400px;

		}



		.control .payBill 
		{

			margin-left: 208px;

			margin-top: 15px;

		}



		.editors label 
		{

			display: block;

			width: 130px;

		}



		.control 
		{

			margin-top: 10px;

		}



		.ctrlLabel 
		{

			padding-bottom: 3px;

		}

	</style>

   ~~~
   			

Execute the above code example to render the following output.

![Getting-Started_images1](Getting-Started_images/Getting-Started_img1.png)

MaskEdit
{:.caption}

## Set Mask value for MobileNumber textbox

In this section, you can learn how to set mask value for MobileNumber textbox. To achieve this, set the mask value in the MaskEdit control to the desired values.

  	{% highlight html %}

  
		<ej-mask-edit id="maskedit" mask-format="99-999-99999" input-mode="@InputMode.Text" />
	
	{% endhighlight  %}


## Mask Configuration

The mask is a combination of standard and custom mask elements that validates the user input based on its behavior.

### Standard Mask Elements

The following table shows the list of mask elements and its behavior based on MSDN standard.

The mask can be formed by combining any one or more of these mask elements.

<table>
<tr>
<th>
Mask Element</th><th>
Description</th></tr>
<tr>
<td>
0</td><td>
Digit required. This element will accept any single digit from <b>0</b> to <b>9</b>.</td></tr>
<tr>
<td>
9</td><td>
Digit or space, optional.</td></tr>
<tr>
<td>
#</td><td>
Digit or space, optional, Plus(+) and minus(-) signs are allowed.</td></tr>
<tr>
<td>
L</td><td>
Letter required. It will accept letters <b>a-z</b> and <b>A-Z</b>.</td></tr>
<tr>
<td>
?</td><td>
Letter or space, optional.</td></tr>
<tr>
<td>
&</td><td>
Requires a character.</td></tr>
<tr>
<td>
C</td><td>
Character or space, optional.</td></tr>
<tr>
<td>
A</td><td>
Alphanumeric <b>(A-Z a-z 0-9)</b> required.</td></tr>
<tr>
<td>
a</td><td>
Alphanumeric <b>(A-Z a-z 0-9)</b> or space, optional.</td></tr>
<tr>
<td>
<</td><td>
Shift down. Converts all characters to lower case.</td></tr>
<tr>
<td>
></td><td>
Shift up. Converts all characters to upper case.</td></tr>
<tr>
<td>
|</td><td>
Disable a previous shift up or shift down.</td></tr>
<tr>
<td>
\\</td><td>
Escapes a mask character, turning it into a literal.</td></tr>
<tr>
<td>
All other characters</td><td>
Literals. All non-mask elements (literals) will appear as themselves within MaskedTextBox.</td></tr>
</table>

## Create a MaskEdit control for Product Key Validation

### Create a MaskEdit

You can easily create the MaskEdit control using simple HTML helper class as follows.

1. Create a ASP.NET Core Project and add Syncfusion assembly packages and scripts to it. 

   Refer [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0).

2. Add the following code to the corresponding view page to render MaskEdit.


   ~~~ cshtml
   
	<div class="frame">

		<div class="control">

			<table class="editors">

				<tbody>

					<tr>

						<td>

							<label>

								Product Key</label>

						</td>

						<td>

						  @*creating MaskEdit control for product key validation*@   
						  
						  <ej-mask-edit id="maskedit" mask-format="aaaa-aaaa-aaaa-aaaa" input-mode="@InputMode.Text" />                     
						  
						</td>

					</tr>

				</tbody>

			</table>

			<div class="productKey">

				<ej-button id="btn" size="@ButtonSize.Small" text="Submit" />

			</div>

		</div>

	</div>

   ~~~
   

3. Add the following styles to show the MaskEdit, and place it in a particular position.

   ~~~ css

	<style>

		.frame 
		{

			width: 300px;

		}



		.editors 
		{

			max-width: 400px;

		}



		.control .productKey 
		{

			margin-left: 208px;

			margin-top: 15px;

		}



		.editors label 
		{

			display: block;

			width: 130px;

		}



		.control 
		{

			margin-top: 10px;

		}



		.ctrlLabel 
		{

			padding-bottom: 3px;

		}

	</style>

   ~~~
   

4. Run the above code example to render the following output. 

![Getting-Started_images3](Getting-Started_images/Getting-Started_img3.png)

Product Key
{:.caption}

## Set Mask value to Product key textbox

You can set mask value for Product key textbox by setting the desired values to the MaskEdit control.

{% highlight CSHTML %}

	<ej-mask-edit id="maskedit" mask-format="aaaa-aaaa-aaaa-aaaa" input-mode="@InputMode.Text" />

{% endhighlight %}

