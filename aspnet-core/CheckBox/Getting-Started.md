---
layout: post
title: Getting Started with ASP.NET Core CheckBox control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core CheckBox control, its elements, and more.
platform: aspnet-core
control: CheckBox
documentation: ug
---

# Getting Started with ASP.NET Core CheckBox

This section explains briefly about how to create a Checkbox in your application with ASP.NET Core.

## Create your first Checkbox in ASP.NET Core

Essential ASP.NET Core Checkbox provides support to multiple selections within your web page, and allows you to select options from the list. Refer the following guidelines to create multiple or single selection List Receiving App using Checkbox that helps you to get the value of checked Checkbox using the button. The following screenshot illustrates the functionality of Checkbox with button action.

![Getting-Started_images1](Getting-Started_images/Getting-Started_img1.png)

Checkboxes Control
{:.caption}

In the above screenshot, you can select hobbies, interest list and social networks receiving app using Checkbox. The Checkbox performs the action to render the checked values when button clicked.

### Create a Checkbox

ASP.NET Core Checkbox widget has built-in features like multiple selections. You can easily create the Checkbox widget using simple Tag helper `<ej-check-box />` as follows.

1. Create a .NetCore Project with the help of the given [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) documentation.
2. Add the following code to the corresponding view page to render Checkbox.



{% highlight html %}

/*ej-Tag Helper code to render CheckBox*/

<div class="frame">

	<div class="control">

		<div class="chkalign">

			<h4>Hobbies</h4>

			<table>

				<tr>

					<td class="chkrad">

						<ej-check-box id="check1" value="Music" />

						<label for="check1" class="clslab">

							Music

						</label>

					</td>

					<td class="chkrad">

						<ej-check-box id="Checkbox3" value="Sports" />

						<label for="Checkbox3" class="clslab">

							Sports

						</label>

					</td>

					<td class="chkrad">

						<ej-check-box id="Checkbox4" value="Bike Riding" />

						<label for="Checkbox4" class="clslab">

							Bike Riding

						</label>

					</td>

				</tr>

			</table>

			<h4>Interest List</h4>

			<table>

				<tr>

					<td class="chkrad">

						<ej-check-box id="Checkbox1" value="Playing Games" size="Medium" />

						<label for="Checkbox1" class="clslab">Playing Games</label>

					</td>

					<td class="chkrad">

						<ej-check-box id="Checkbox5" value="Hearing Songs" size="Medium" />
						
						<label for="Checkbox5" class="clslab">Hearing Songs</label>

					</td>

					<td class="chkrad">

						<ej-check-box id="Checkbox6" value="Reading Books" size="Medium" />

						<label for="Checkbox6" class="clslab">Reading Books</label>

					</td>

				</tr>

			</table>

		</div>

	</div>

</div>

{% endhighlight  %}


{% highlight html %}

/*Razor code to render CheckBox*/

<div class="frame">

    <div class="control">

        <div class="chkalign">

            <h4>Hobbies</h4>

            <table>

                <tr>
                    <td class="chkrad">

                        @{  Html.EJ().CheckBox("check1").Value("Music").Render(); }

                      <label for="check1" class="clslab">
                    
                            Music

                        </label>

                    </td>

                    <td class="chkrad">

                        @{ Html.EJ().CheckBox("Checkbox3").Value("Sports").Render(); }


                        <label for="Checkbox3" class="clslab">

                            Sports

                        </label>

                    </td>

                    <td class="chkrad">

                        @{ Html.EJ().CheckBox("Checkbox4").Value("Bike Riding").Render(); }

                        <label for="Checkbox4" class="clslab">

                            Bike Riding

                        </label>

                    </td>

                </tr>

            </table>

            <h4>Interest List</h4>

            <table>

                <tr>

                    <td class="chkrad">

                        @{ Html.EJ().CheckBox("Checkbox1").Value("Playing Games").Size(Size.Medium).Render(); }

                        <label for="Checkbox1" class="clslab">Playing Games</label>

                    </td>

                    <td class="chkrad">

                        @{ Html.EJ().CheckBox("Checkbox5").Value("Hearing Songs").Size(Size.Medium).Render(); }

                        <label for="Checkbox5" class="clslab">Hearing Songs</label>

                    </td>

                    <td class="chkrad">

                        @{ Html.EJ().CheckBox("Checkbox6").Value("Reading Books").Size(Size.Medium).Render(); }

                        <label for="Checkbox6" class="clslab">Reading Books</label>

                    </td>

                </tr>

            </table>

        </div>

    </div>

</div>


{% endhighlight %}

N> To render the CheckBox Control you can use either Razor or Tag helper code as given in the above code snippet.


3. Add the following styles to the corresponding view page to show the Checkbox in horizontal order.

{% highlight css %}

	<style>

		td {

			float: left;

		}

		label

		{

			float: right; margin:5px 10px;

		}

	</style>
	
{% endhighlight  %}




4. Run the above code to render the following output.



![Getting-Started_images2](Getting-Started_images/Getting-Started_img2.png)

Checkbox Creation
{:.caption}

### Create a Tri-State Checkbox

ASP.NET Core Tri-State Checkbox widget renders by setting EnableTriState property to true. You can add the following code to create Tri-state Checkbox in the <div> element of the corresponding view page.



{% highlight js %}

/*ej-Tag Helper code to render CheckBox*/


<h4>Social networks</h4>

<table>

	<tr>

		<td class="chkrad">

			<ej-check-box id="Checkbox2" value="Checkbox2" size="Medium" enable-tri-state="true" check-state="Indeterminate" /> <label for="Checkbox2" class="clslab">Facebook</label>

		</td>

		<td class="chkrad">

			<ej-check-box id="Checkbox7" value="GPlus" size="Medium" enable-tri-state="true" check-state="Uncheck" /> <label for="Checkbox7" class="clslab">GPlus</label>

		</td>

		<td class="chkrad">

			<ej-check-box id="Checkbox8" value="Twitter" size="Medium" enable-tri-state="true" check-state="Check" /> <label for="Checkbox8" class="clslab">Twitter</label>

		</td>

	</tr>

</table>



{% endhighlight %}

{% highlight html %}

/*Razor code to render CheckBox*/

<table>
    <tr>
        <td class="chkrad">

	 @{ Html.EJ().CheckBox("Checkbox2").Value("Facebook").Size(Size.Medium).EnableTriState(true).CheckState(CheckState.Indeterminate).Render(); }
            <label for="Checkbox2" class="clslab">Facebook</label>

        </td>

        <td class="chkrad">

	 @{ Html.EJ().CheckBox("Checkbox7").Value("GPlus").Size(Size.Medium).EnableTriState(true).CheckState(CheckState.Uncheck).Render(); }
            <label for="Checkbox7" class="clslab">GPlus</label>

        </td>

        <td class="chkrad">

	 @{ Html.EJ().CheckBox("Checkbox8").Value("Twitter").Size(Size.Medium).EnableTriState(true).CheckState(CheckState.Check).Render();}
            <label for="Checkbox8" class="clslab">Twitter</label>

        </td>
    </tr>
</table>


{% endhighlight %}

Run the above code to render the following output.



![Getting-Started_images3](Getting-Started_images/Getting-Started_img3.png)

Tri-state Checkbox Creation
{:.caption}

### Receive Hobbies and Interest

You can receive the Hobbies and Interest values using Checkbox. You can create a button in your corresponding view page <div> element using <ej-button /> and add the script section to the view page. The following steps illustrate how to create and set action to the button.

 Add the following code for Button creation.


{% tabs %}

{% highlight CSHTML %}

/*ej-Tag Helper code to render CheckBox*/

<ej-button id="buttonnormal" text="Submit" size="Normal">

{% endhighlight %}



 Add the script into your view page.	



{% highlight js %}



<script>

    $(document).ready(function () {

        $("button").click(function () {

            var checked = [];                                               

            $(".e-checkbox").each(function () {

             if ($("#" + $(this)[0].id).ejCheckBox("option", "checked"))

                 checked.push($("#" + $(this)[0].id).ejCheckBox("option","value"));

             });

            alert(checked);        
		});
    });

</script>


{% endhighlight %}

{% endtabs %}  


{% tabs %}

{% highlight CSHTML %}

/*Razor code to render CheckBox*/

	 @{ Html.EJ().Button("button").Text("Submit").Size(ButtonSize.Normal).Render(); }

{% endhighlight %}



 Add the script into your view page.	



{% highlight js %}



<script>

    $(document).ready(function () {

        $("button").click(function () {

            var checked = [];                                               

            $(".e-checkbox").each(function () {

             if ($("#" + $(this)[0].id).ejCheckBox("option", "checked"))

                 checked.push($("#" + $(this)[0].id).ejCheckBox("option","value"));

             });

            alert(checked);        
		});
    });

</script>


{% endhighlight %}

{% endtabs %}  


Execute the above code example to render the following output.



![Getting-Started_images4](Getting-Started_images/Getting-Started_img4.png)

Receive hobbies and interest
{:.caption}

### Receive Media Player

You can get the Media Player file type application like video, audio and picture using Checkbox. You can refer the following steps to render Media Player file types.

1. Add the following code in <div> element of the corresponding view page.



{% highlight html %}

/*ej-Tag Helper code to render CheckBox*/

			<table>

				<label for="check2" class="clslab">

					Audio

				</label>

				<tr>

					<td class="chkrad">

						<ej-check-box id="Checkboxs3" value=".mp3" size="Medium" />

						<label for="Checkboxs3" class="clslab">

							.mp3

						</label>

					</td>

				</tr>

				<tr>

					<td class="chkrad">

						<ej-check-box id="Checkboxs4" value=".avi" size="Medium" />

						<label for="Checkboxs4" class="clslab">

							.avi

						</label>

					</td>

				</tr>

			</table>

			<table>

				<label for="Checkboxs1" class="clslab">Video</label>

				<tr>

					<td class="chkrad">

						<ej-check-box id="Checkboxs5" value=".mp4" size="Medium" />

						<label for="Checkboxs5" class="clslab">.mp4</label>

					</td>

				</tr>

				<tr>

					<td class="chkrad">

						<ej-check-box id="Checkboxs6" value=".wave" size="Medium" />

						<label for="Checkboxs6" class="clslab">.wave</label>

					</td>

				</tr>

			</table>

{% endhighlight  %}


{% highlight html %}

/*Razor code to render CheckBox*/

<table>

    <label for="check2" class="clslab">

        Audio

    </label>

    <tr>

        <td class="chkrad">

            @{Html.EJ().CheckBox("Checkboxs3").Value(".mp3").Size(Size.Medium).Render(); }

            <label for="Checkboxs3" class="clslab">

                .mp3

            </label>

        </td>

    </tr>

    <tr>

        <td class="chkrad">

            @{Html.EJ().CheckBox("Checkboxs4").Value(".AVI").Size(Size.Medium).Render(); }

            <label for="Checkboxs4" class="clslab">

                .AVI

            </label>

        </td>

    </tr>

</table>

<table>

    <label for="Checkboxs1" class="clslab">Video</label>

    <tr>

        <td class="chkrad">

            @{Html.EJ().CheckBox("Checkboxs5").Value(".mp4").Size(Size.Medium).Render(); }

            <label for="Checkboxs5" class="clslab">.mp4</label>

        </td>

    </tr>

    <tr>

        <td class="chkrad">

     @{Html.EJ().CheckBox("Checkboxs6").Value(".wave").Size(Size.Medium).Render(); }

            <label for="Checkboxs6" class="clslab">.wave</label>

        </td>

    </tr>

</table>

{% endhighlight %}

Execute the above code to render the following output.	



![Getting-Started_images5](Getting-Started_images/Getting-Started_img5.png)

Receive Media player
{:.caption}
