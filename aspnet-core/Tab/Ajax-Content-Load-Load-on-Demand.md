---
layout: post
title: Ajax Content Load Load on Demand | Tab  | ASP.NET Core | Syncfusion
description: ajax content load (load on demand)
platform: aspnet-core
control: Tab 
documentation: ug
---

# AJAX Content Load (Load on Demand)

You can change the contents in a sub tab element periodically and you are provided with a support to change the contents without any problems. To achieve the content load, use the Load on Demand concept.

In Load on Demand, the external HTML file with the necessary details are referred in URL section during the tab header declaration. It also includes DataType, ContentType, and Async in the script like the following example on rendering the control. When you click the tab header, the AJAX automatically calls the content from the external files and display it in a tab content section.

## Sub tab with AJAX content

Each item has a variety of options and these options are also specified in the limited space. So you can choose the tab control that is used within the root tab to specify more details.

1. Add the following code in your view page to render the sub tab with AJAX content.


{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

	<ej-tab id="DishType" width="600px">
	    <e-tab-items>
	        <e-tab-item id="Pizza" text="Pizza Menu">
	            <e-content-template>
	                <div>
	                     <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
	                    </div>
	               
	                <ej-tab id="PizzaMenu">
	                    <e-tab-items>
	                        <e-tab-item id="Corn-Spinach" text="Corn Spinach" url="../css/cornspinach.html">
	                          
	                        </e-tab-item>
	                        <e-tab-item id="ChickenDelite" text="Chicken-Delite" url="../css/chickenDelite.html">
	                         
	                        </e-tab-item>
	                    </e-tab-items>
	                </ej-tab>
	            </e-content-template>
	        </e-tab-item>
	        <e-tab-item id="sandwitchtype" text="Sandwizza Menu">
	            <e-content-template>
	                <div>
	                    <p> Sandwizza cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
	                </div>
	
	                <ej-tab id="sandwitchMenu">
	                    <e-tab-items>
	                        <e-tab-item id="gardenveggie" text="Garden-Veggie" url="../css/gardenVeggie.html">
	
	                        </e-tab-item>
	                        <e-tab-item id="chickentikka" text="Chicken-Tikka" url="../css/chickenTikka.html">
	
	                        </e-tab-item>
	                    </e-tab-items>
	                </ej-tab>
	            </e-content-template>
	        </e-tab-item>
	    </e-tab-items>
	    </ej-tab>
{% endhighlight %}

{% highlight Razor %}

/*Razor code to render Tab*/

	@{Html.EJ().Tab("DishType").Items(data =>

    {

    data.Add().ID("Pizzatype").Text("Pizza Menu").ContentTemplate(@<div>

        Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.

        @firstTab()

    </div>);

    data.Add().ID("sandwitchtype").Text("Sandwizza Menu").ContentTemplate(@<div>

        Sandwizza cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.

        @secondTab()

    </div>);


    }).Render()};




    @helperfirstTab()


            {

    @{Html.EJ().Tab("PizzaType").Items(data =>

        {

            data.Add().ID("Corn-Spinach").Text("Corn Spinach").Url("../css/cornspinach.html");

            data.Add().ID("ChickenDelite").Text("Chicken-Delite").Url("../css/chickenDelite.html");

        }).Render(); }


            }

    @helper secondTab()


        {

    @{Html.EJ().Tab("sandwichtype").Items(data =>

        {

            data.Add().ID("gardenveggie").Text("Corn Spinach").Url("../css/gardenVeggie.html");

            data.Add().ID("chickentikka").Text("Chicken-Delite").Url("../css/chickenTikka.html");
        }).Render(); }

       }

  {% endhighlight %}

   

2. The file **cornSpinach.html** content is as follows:
   
 
{% highlight CSHTML %}
        

	<!DOCTYPE html>

	<html xmlns="http://www.w3.org/1999/xhtml">

	<body>

		<div class="e-content">

		<img src="http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach">

		<div class="ingredients">

			Rate    : $70<br/> Ingredients : cheese, sweet corn &amp; green capsicums.

			<br />

			Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.                    </div>

		</div>   

	</body>

	</html>

  {% endhighlight %}

   



3. The file **chickenDelite.html** content is as follows.

 {% highlight CSHTML %}

	<!DOCTYPE html>

	<html xmlns="http://www.w3.org/1999/xhtml">

	<body>

		<div class="e-content">

		<img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="chicken-delite">

		<div class="ingredients">

			Rate    : $100<br /> Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.   <br /> 

			 Description: This is a tasty, elegant chicken dish that is easy to prepare.

		</div>

		</div>

	</body>

	</html>

{% endhighlight %}

   
N> To render the tab Control, you can use either Razor or Tag helper code as given in the previous code snippet.



The following screenshot illustrates the first Tab with the sub tab control using Load on Demand.

![](Ajax-Content-Load-Load-on-Demand_images/Ajax on load.JPG)

Tab section with sub Tab control using Load on Demand.
{:.caption}



N> You can also load content from another view page by providing the Url as the name of required view page. For example: url="../Home/Index".