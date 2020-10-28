---
layout: post
title: Getting-Started | TimePicker | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: TimePicker
documentation: ug
---

# Getting Started

This section explains briefly about how to create  and customize a TimePicker in an ASP.net Core application.

## Create your first TimePicker

Essential TimePicker provides support to display the time in your web page and allows you to pick a time from the dropdownlist. In this section you can learn how to customize TimePickers in a real-time application. The following example shows you how to use the TimePicker control to book a hotel dining table booking application, within a limited time, in any day.

![Create your first TimePicker](Getting-Started_images/Getting-Started_img1.png)

The above screenshot illustrates the functionality of a TimePicker, with a time range from morning to evening. You can select the time to book a table ranging from 9.00 AM to 10.00 PM in the current day. This avoids selecting a time prior to that day.


### Create a TimePicker

Essential TimePicker widget has built-in features such as keyboard navigation, other time navigation with animations, and flexible APIs. You can easily create the TimePicker widget using simple TimePicker element as follows.

1. [Getting Started](/aspnet-core/getting-started) section explains about basic system requirements and the steps to configure the Syncfusion Components in an ASP.net core application.

    After successfully adding the necessary dependencies in your solution, make sure to build the solution, so that the necessary assembly files are compiled properly before using it in your project.

2. Add the following code to the corresponding view page to render the TimePicker.

   {% highlight CSHTML %}

/*ej-Tag Helper code to render TimePicker*/

	@*Add the following code example to the corresponding CSHTML page to render TimePicker widget*@

	<table>

            <tr>

                <td class="control">Date</td>

                <td class="control">Time</td>

                <td class="control">Person</td>

            </tr>

            <tr>

                <td class="control">

                    <span class="inner-display">

                        <ej-date-picker id="startDate"></ej-date-picker>

                    </span>

                </td>

                <td class="control">

                    <span class="inner-display">

                        <ej-time-picker id="timeStart"></ej-time-picker>

                    </span>

                </td>

                <td class="control">

                    <span class="inner-display">

                        <ej-numeric-text-box id="NumericTextbox" value="0" />

                    </span>

                </td>

            </tr>

            <tr>

                <td></td>

                <td></td>

                <td class="control">

                    <span class="inner-display">

                        <ej-button id="Submit" width="100px" size="Small" text="Submit" click="Confirm" />

                    </span>

                </td>

            </tr>

        </table>

   {% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render TimePicker*/

<table>

    <tr>

        <td class="table-cell">Date</td>

        <td class="table-cell">Time</td>

        <td class="table-cell">Person</td>

    </tr>

    <tr>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().DatePicker("startDate").Render(); }

            </span>

        </td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().TimePicker("timeStart").Render(); }

            </span>

        </td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().NumericTextbox("NumericTextbox").Value("0").Render(); }

            </span>

        </td>

    </tr>

    <tr>

        <td></td>

        <td></td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().Button("Submit").Width("100px").Size(ButtonSize.Small).Text("Submit").ClientSideEvents(s => s.Click("button")).Render(); }

            </span>

        </td>

    </tr>

</table>


{% endhighlight %}

N> To render the TimePicker Control you can use either Razor or Tag helper code as given in the above code snippet.

   
3. Add the following styles to show the TimePicker control in horizontal order in the Content folder.

   ~~~ css


	<style type="text/css" class="cssStyles">

		.control 
		{

		width: 70px;

		height: 10px;

		font-weight: bold;

		padding: 10px;

		}

		.inner-display 
		{

		display: inline-block;

		}

	</style>

   ~~~
   
4. Add the following code to the Layout page for DatePicker and TimePicker initialization.

   ~~~ js


	<script type="text/javascript">

		function Confirm()

		{

		alert("You have Successfully booked");

		}

	</script>

   ~~~
   



5. The following screenshot displays the output for the above code.

   ![Create a TimePicker](Getting-Started_images/Getting-Started_img2.png)





6. Click the submit button in the application to get the following output.

   ![Create a TimePicker](Getting-Started_images/Getting-Started_img3.png)


### Set Min and Max Date

In a real-time scenario, the booking is open only for a limited time. You can select a date and time from the given range using the properties MinDate, MinTime and MaxDate, MaxTime that enables only the dates and times ranging between the MinDate, MinTime and MaxDate, MaxTime in the DatePicker and TimePicker.

1. Add the following code to the corresponding view page to render the TimePicker.

   {% highlight CSHTML %}

/*ej-Tag Helper code to render TimePicker*/

	@*Add the following code example to the corresponding CSHTML page to render TimePicker widget*@

	<table>

            <tr>

                <td class="control">Date</td>

                <td class="control">StartTime</td>

                <td class="control">EndTime</td>

                <td class="control">Person</td>

            </tr>

            <tr>

                <td class="control">

                    <span class="inner-display">

                        <ej-date-picker id="startDate" value="DateTime.Now" min-date="DateTime.Now" max-date="DateTime.Now.AddDays(1)"></ej-date-picker>

                    </span>

                </td>

                <td class="control">

                    <span class="inner-display">

                        <ej-time-picker id="timeStart" min-time="9:00 AM" max-time="10:00 PM" interval="60" select="selectedStartTime"></ej-time-picker>
                    </span>

                </td>

                <td class="control">

                    <span class="inner-display">

                        <ej-time-picker id="timeEnd" min-time="9:00 AM" max-time="10:00 PM" interval="60"></ej-time-picker>

                    </span>

                </td>

                <td class="control">

                    <span class="inner-display">

                        <ej-numeric-text-box id="NumericTextbox" value="0" />

                    </span>

                </td>

            </tr>

            <tr>

                <td></td>

                <td></td>

                <td></td>

                <td class="control">

                    <span class="inner-display">

                        <ej-button id="Submit" width="100px" size="Small" text="Submit" click="Confirm" />

                    </span>

                </td>

            </tr>

        </table>

   {% endhighlight %}
   
{% highlight CSHTML%}

/*Razor code to render TimePicker*/

<table>

    <tr>

        <td class="table-cell">Date</td>

        <td class="table-cell">StartTime</td>

        <td class="table-cell">EndTime</td>

        <td class="table-cell">Person</td>

    </tr>

    <tr>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().DatePicker("startDate").Value(DateTime.Now).MinDate(DateTime.Now).MaxDate(DateTime.Now.AddDays(1)).Render(); }

            </span>

        </td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().TimePicker("timeStart").MinTime("9:00 AM").MaxTime("10:00 PM").Interval(60).ClientSideEvents(e => e.Select("selectedStartTime")).Render(); }

            </span>

        </td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().TimePicker("timeEnd").MinTime("9:00 AM").MaxTime("10:00 PM").Interval(60).Render(); }

            </span>

        </td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().NumericTextbox("NumericTextbox").Value("0").Render(); }

            </span>

        </td>

    </tr>

    <tr>

        <td></td>

        <td></td>

        <td></td>

        <td class="table-cell">

            <span class="inner-display">

                @{Html.EJ().Button("Submit").Width("100px").Size(ButtonSize.Small).Text("Submit").ClientSideEvents(s => s.Click("button")).Render(); }

            </span>

        </td>

    </tr>

</table>


{% endhighlight %}

2. Add the following styles to show the TimePicker control in horizontal order in the Content folder.

   {% highlight css %}

	<style type="text/css" class="cssStyles">

		.control {

        width: 70px;

        height: 10px;

        padding: 10px;
        
        color: #333;

        font-family: Segoe UI;
        
        font-weight: 500;

        font-size: 14px;

        }

		.inner-display 
		{

		display: inline-block;

		}


	</style>

   {% endhighlight %}
   




3. Add the following code to the Layout page for DatePicker and TimePicker initialization.

   ~~~ js


		<script type="text/javascript">

		    function selectedStartTime(sender) {

			var selDate = sender.value; // mentions the selected time.

			minTimepicker = $("#timeEnd").data("ejTimePicker");// creating TimePicker object

			minTimepicker.setModel({ "minTime": selDate });// setting minTime property through setModel of TimePicker object.

		    }

		    function Confirm()

		    {

			alert("You have Successfully booked");

		    }

		</script>

   ~~~
   





4. The following screenshot displays the output for the above code. 

![Set Min and Max Date](Getting-Started_images/Getting-Started_img4.png)





You can select the Start time in the first TimePicker and select the End time within the given range. The second TimePicker start value is based on the first TimePicker’s selected value. This is illustrated in the following screenshots.



![Set Min and Max Date](Getting-Started_images/Getting-Started_img5.png)


![Set Min and Max Date](Getting-Started_images/Getting-Started_img6.png)



### Display Reserved Time 

An acknowledgment message appears when you click the Submit button. 

You can specify the alert message in the script as follows.

{% highlight js %}

<script type="text/javascript">

        function button()

            {



                    var a = $('#startDate').val();



                    var b = $('#timeStart').val();



                    var d = $('#timeEnd').val();



                    var c = $('#NumericTextbox').val();



                    alert("You have successfully booked\nDate    : " + a + "\nStartTime: " + b + "\nEndTime: " + d + " \nPerson   :  " + c);



            }

</script>

{% endhighlight %}


![Display Reserved Time](Getting-Started_images/Getting-Started_img7.png)



