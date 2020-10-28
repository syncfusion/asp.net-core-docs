---
layout: post
title: Getting Started | Slider | ASP.NET Core | Syncfusion
description: getting started 
platform: aspnet-core
control: Slider
documentation: ug
---

# Getting Started 

This section explains briefly about how to create a Slider in your ASP.NET Core application.

## Create your first Slider in ASP.NET Core

ASP.NET Core Slider provides support to display a Slider within the web page. The following section explains you on how to use Sliders in a real-time application to select a mobile model within specified range in Mobile Purchase.

The following screenshot illustrates the functionality of Slider control. You can select a mobile model in the dropdown to purchase it at any rate specified in the Mobile RateSlider and you can also specify the number of mobiles you need by selecting the Mobile CountSlider. Simultaneously, you can observe the change in mobile rate and count using Sliders.

![](Getting-Started_images/Getting-Started_img1.png)



### Create a Slider

ASP.NET Core Slider control allows you to switch between different ranges of input. The basic Slider is horizontal and has a single handle that can be moved with the mouse or by using the arrow keys. You can easily create the Slider control using Tag helper as follows.

1. Create an ASP.NET Core Project and add Syncfusion assembly packages, scripts, and styles to it.

   Refer [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/getting-started)

2. Add the following code example for Slider to the corresponding view page.

   ~~~ cshtml

	    <div class="frame">

        <div class="inner">

            <div class="control-label">

                Select a Mobile

            </div>  

            <ej-drop-down-list id="selectMobile" target-id="mobileList" width="150px" ></ej-drop-down-list>
              
            <div id="mobileList">

                <ul>

                    <li>Moto X</li>

                     <li>Moto g</li>

                     <li>Nexus</li>

                     <li>Lenovo</li>

                     <li>Samsung</li>

                </ul>

            </div>

            <span class="column-left">

                <span>Mobile Rate</span>

            </span>

            <span class="column-right">

                <span>Rs </span><span class="value"></span>

            </span>

            <ej-slider id="rateSlider" height="20px" value="100" min-value="5000" max-value="30000" increment-step="20" change="onChange" slide="onChange" />       

            <span class="column-left">

                <span>Mobile Count</span>

            </span> 

            <ej-slider id="countSlider" height="20px" value="1" min-value="1" max-value="10" increment-step="1" change="onChange" slide="onChange" />              

            You are choosing:

            <span id="EventLog"></span>

        </div>

    </div>

   ~~~
   

3. Add the following styles for Sliders.


   ~~~ css
   
	<style>

		.frame

		{

			width:400px;

			height:200px;

			border:1px solid black;

			margin-right:100px;

		}

		.control-label, .loan

		{

			font-weight:bold;

		}

		.column-right

		{

			font-weight:bold;

			float:right;

		}

		.inner

		{

			width:300px;

			height:150px;

			padding:20px 40px 20px 30px;

		 } 

		.mobileList

		{

			display:block;

		}

	</style>

   ~~~
   

4. Add the following script to the Slider.

   ~~~ js

	<script>

			var mobileObj, rateObj, countObj;

			function onChange(args) {

				$('#' + args.id).parent().prev().find('.value').html(args.value)

				show();

			}

			function show() {

				selectObj = $('#selectMobile').data('ejDropDownList');

				rateObj = $('#rateSlider').data('ejSlider');

				countObj = $('#countSlider').data('ejSlider');

				var x = selectObj.getValue();

				var y = rateObj.getValue();

				var z = countObj.getValue();

				$('#EventLog').html("\n" + x + "\n" + "at Rs: " + y + "\n" + "and count is " + z);

				}

	</script>

   ~~~
   

5. The following screenshot displays the final output in Slider creation.

![](Getting-Started_images/Getting-Started_img2.png)



### EMI Calculator

This section explains how to use the Slider control for EMI Calculation. The final result of EMI amount is calculated automatically based on the loan amount, interest rate and tenure amount based on the amount you choose using Slider.

1. You can create an ASP.NET Core Project and add necessary Syncfusion assembly packages and script to it.
2. Add the following code for Slider to the corresponding view page.



   ~~~ cshtml

    <div class="frame">

        <div class="inner">

            <div id="loan-heading">

                Details of Loan

            </div>

            <span class="column-left">

                <span>Loan Amount</span>

            </span>

            <span class="column-right">

                <span>Rs </span><span class="value">25000</span>

            </span>    
        
            <ej-slider id="loanSlider" height="16px" value="25000" min-value="10000" max-value="1000000" increment-step="10" change="onChange" slide="onChange" />

            <span class="column-left">

                <span>Interest Rate</span>

            </span>

            <span class="column-right">

                <span class="value"></span><span>% pa</span>

            </span>        
        
            <ej-slider id="interestSlider" height="16px" value="4" min-value="1" max-value="20" increment-step="1" change="onChange" slide="onChange" />

            <span class="column-left">

                <span>Tenure</span>

            </span>

            <span class="column-right">

                <span class="value"></span><span>Years</span>

            </span>        
        
            <ej-slider id="tenureSlider" height="16px" value="3" min-value="1" max-value="20" increment-step="1" change="onChange" slide="onChange" />

            Your Monthly EMI Amount is

            <span id="EventLog"></span>

        </div>

    </div>

   ~~~
   

3. Include the following styles for Slider.


   ~~~ css
   
	<style>

		.frame

		{

			width:350px;

			height:200px;

			border:1px solid black;

		}

		.inner

		{

			 width:250px;

			height:150px;

			padding:20px 30px;

		}

		#loan-heading

		{

		font-weight:bold;

		}

		.column-left

		{

			font-weight:bold;

		}

		.column-right

		{

			float:right;

			font-weight:normal;

		}

	</style>


   ~~~
   


4. Include the following script to calculate the EMI amount.



   ~~~ cshtml

	<script type="text/javascript">

		var loanObj, interestObj, tenureObj;

		function onChange(args) 
		{

			$('#' + args.id).parent().prev().find('.value').html(args.value)

			calculate();

		}

		function calculate() 
		{

			loanObj = $('#loanSlider').data('ejSlider');

			interestObj = $('#interestSlider').data('ejSlider');

			tenureObj = $('#tenureSlider').data('ejSlider');

			var loan = loanObj.getValue(), interest = interestObj.getValue(), tenure = tenureObj.getValue();

			var P = loan;

			var y = interest / 1200;

			var tenureAmount = tenure * 12;

			//actual processing

			var top = y * (Math.pow((1 + y), tenureAmount));

			var bottom = (Math.pow((1 + y), tenureAmount)) - 1;

			var ans = top / bottom;

			var final = P * ans;

			var z = Math.round(final);

			$('#EventLog').html("Rs: " + z);

		}

	</script>
		
   ~~~
   

The following screenshot displays the calculated EMI amount using Slider.



![](Getting-Started_images/Getting-Started_img3.png)



The Slider component lets you to select a value such as number, percentage by moving the slider handle. It also allows you to specify a range of values between its minimum and maximum values. You can use Slider to influence other object. For example, Slider can be associated with a picture so that the picture enlarges or shrinks based upon the value in the slider.

The Slider has horizontal orientation by default. You can also change the orientation as vertical. Also, the Slider contains features like enabling slider of different types, enabling scale in the slider etc.

