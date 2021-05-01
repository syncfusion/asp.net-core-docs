---
layout: post
title: Getting Started with ASP.NET Core Tab control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core Tab control, its elements, and more.
platform: aspnet-core
control: Tab
documentation: ug
---

# Getting Started with ASP.NET Core Tab

This section explains how to create a tab control in your application with ASP.NET Core.

## Create your first tab control in ASP.NET Core

The ASP.NET Core tab control is an interface that displays the content in multiple sections. A tab panel consists of HeaderText as well as a ContentTemplate. This is very useful when dashboards have limited space. The following screenshot shows how to customize the tab to display Hotel menu items,  rate details, and the ingredients on demand.

![Getting-Started_images1](Getting-Started_images/Getting-Started_img1.png)

Tab control with Hotel Menu items
{:.caption}

### Create tab control

The ASP.NET Core tab widget basically builds a dynamic, interactive, and menu-driven interface from your content. The content can be a text, graphics, or HTML. You can create the tab headers using the Text and Content template properties.

To create a tab control:

1. Create a core project, and add the required assemblies and script with the help of [Dotnet Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) documentation.
2.Then, add the following code sample to the corresponding view page for tab rendering..
  
{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

<div style="width: 500px">

    <ej-tab id="tabSample">
        <e-tab-items>
            <e-tab-item id="Pizza" text="Pizza Menu">
                <e-content-template></e-content-template>
            </e-tab-item>
            <e-tab-item id="Pasta" text="Pasta Menu">
                <e-content-template></e-content-template>
            </e-tab-item>
            <e-tab-item id="Sandwich" text="Sandwich Menu">
                <e-content-template></e-content-template>
            </e-tab-item>
        </e-tab-items>
    </ej-tab>

</div>

{% endhighlight %}

{% highlight Razor %}

 /*Razor code to render Tab*/

@{ Html.EJ().Tab("DishType").Items(data =>
	{
		data.Add().ID("pizza").Text("Pizza Menu").ContentTemplate(@<div></div>);
		data.Add().ID("type").Text("Pizza Type").ContentTemplate(@<div></div>);
		data.Add().ID("sandwich").Text("Sandwich Type").ContentTemplate(@<div></div>);
	}).Render();
    }

{% endhighlight %}

N> To render the tab control, use either Razor or Tag helper code as given in the code sample.
 
The following output will be displayed.

![Getting-Started_images2](Getting-Started_images/Getting-Started_img2.png)' 

Tab control with Header

{:.caption}


### Configure content

In this application, a detailed description of each item is provided . You can specify the contents in the tab section within the content template.
 
{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

<ej-tab id="DishType">
    <e-tab-items>
        <e-tab-item id="pizza" text="Pizza Menu">
            <e-content-template>
                <div>
                    <ej-rating id="RatingPizza" value="4" precision="@Precision.Exact" />
                    <!--Food item description-->

                    <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

                </div>
            </e-content-template>
        </e-tab-item>
        <e-tab-item id="type" text="Pizza Type">
            <e-content-template></e-content-template>
        </e-tab-item>
        <e-tab-item id="sandwich" text="Sandwich Type">
            <e-content-template></e-content-template>
        </e-tab-item>
    </e-tab-items>
</ej-tab>

{% endhighlight %}

{% highlight Razor %}

/*Razor code to render Tab*/

@Html.EJ().Tab("DishType").Items(data =>

{

data.Add().ID("pizza").Text("Pizza Menu").ContentTemplate(@<div>
    Rating:

    @Html.EJ().Rating("RatingPizza").Value(4).Precision(Precision.Exact)


    <!--Food item description-->

    <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

</div>);

})

{% endhighlight %}

You can also customize the tab by using rating control to describe the item’s price.

### Create the rating

The ASP.NET Core rating control provides an intuitive rating experience. This allows you to select the number of stars that represents rating.Create the rating control using HTML helper, and render the rating control and its description inside the content template in first tab control. 

For more information about rating, refer to the following link:

<https://help.syncfusion.com/aspnet-core>

The following code example explains the creation of rating control:

{% highlight CSHTML %}

 /*ej-Tag Helper code to render Tab*/

<div style="width: 500px">

        <ej-tab id="tabSample">
            <e-tab-items>
                <e-tab-item id="Pizza" text="Pizza Menu">
                    <e-content-template>
                        <div>
                            Rating :
                        </div>
                        <div>
                            <ej-rating id="gradenPizza" allow-reset="false" read-only="true" value="4" />
                        </div>
                        <div>
                            Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                        </div>
                    </e-content-template>
                </e-tab-item>
                <e-tab-item id="Sandwich" text="Sandwich Menu ">
                    <e-content-template>
                    </e-content-template>
                </e-tab-item>
                <e-tab-item id="Pasta" text="Pasta Menu">
                    <e-content-template>
                    </e-content-template>
                </e-tab-item>
            </e-tab-items>
        </ej-tab>

    </div>

 {% endhighlight %}

 {% highlight Razor %}

 /*Razor code to render Tab*/
  
@Html.EJ().Tab("DishType").Items(data =>
{
data.Add().ID("pizza").Text("Pizza Menu").ContentTemplate(@<div> Rating:
@Html.EJ().Rating("RatingPizza").Value(4).Precision(Precision.Exact)

<!--Food item description-->

<p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
</div>);
data.Add().ID("type").Text("Pizza Type").ContentTemplate(@<div></div>);
data.Add().ID("sandwich").Text("Sandwich Type").ContentTemplate(@<div></div>);
}) 

{% endhighlight %}

The following screenshot is the output for the given code example.

![Getting-Started_images3](Getting-Started_images/Getting-Started_img3.png)

### Sub tab with content

Each item has a variety of options and those options have to be specified in the limited space. So you can choose the tab control that is used within the root tab to specify more details.

The following code sample represents the rendering of sub tab control using the helper function:

{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

 <div style="width: 500px">
    <ej-tab id="DishType">
        <e-tab-items>
            <e-tab-item id="Pizza" text="Pizza Menu">
                <e-content-template>
                    <div>
                        <div>
                            Rating :
                            <div>
                                <ej-rating id="gradenPizza" allow-reset="false" read-only="true" value="4" />
                            </div>
                            <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
                        </div>
                    </div>
                    <ej-tab id="pizza">
                        <e-tab-items>
                            <e-tab-item id="Corn-Spinach" text="Corn Spinach">
                                <e-content-template>
                                    <div>
                                        <img src=" http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach">
                                        <div class="ingredients">
                                            Rate    : $70<br />
                                            Ingredients : cheese, sweet corn &amp; green capsicums.
                                            <br />
                                            Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.
                                        </div>
                                    </div>
                                </e-content-template>
                            </e-tab-item>
                            <e-tab-item id="ChickenDelite" text="Chicken-Delite">
                                <e-content-template>
                                    <div>
                                        <img src=" http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="corn-spinach">
                                        <div class="ingredients">
                                            Rate    : $100<br />
                                            Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.
                                            <br />
                                            Description: This is a tasty, elegant chicken dish that is easy to prepare.
                                        </div>
                                    </div>
                                </e-content-template>
                            </e-tab-item>
                        </e-tab-items>
                    </ej-tab>
                </e-content-template>
            </e-tab-item>
        </e-tab-items>
        </ej-tab>
</div>

{% endhighlight %}

{% highlight Razor %}

/*Razor code to render Tab*/

@Html.EJ().Tab("DishType").Items(data =>
{
    data.Add().ID("pizza").Text("Pizza Menu").ContentTemplate(@<div> Rating:
    @Html.EJ().Rating("RatingPizza").Value(4).Precision(Precision.Exact)

<!--Food item description-->

    <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
       @firstTab()
</div>);
    data.Add().ID("type").Text("Pizza Type").ContentTemplate(@<div></div>);
    data.Add().ID("sandwich").Text("Sandwich Type").ContentTemplate(@<div></div>);
})
@helper firstTab()
{
    @Html.EJ().Tab("pizza").Items(data =>
    {
        data.Add().ID("Corn-Spinach").Text("Corn Spinach").ContentTemplate(@<div class="e-content">
            <img src=" http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach">
            <div class="ingredients">
                Rate    : $70<br />
                Ingredients : cheese, sweet corn &amp; green capsicums.
                <br />
                Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.
            </div>
        </div>
    );
        data.Add().ID("ChickenDelite").Text("Chicken-Delite").ContentTemplate(@<div class="e-content">
    <img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="chicken-delite">
    <div class="ingredients">
        Rate    : $100<br />
        Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.
        <br />
        Description: This is a tasty, elegant chicken dish that is easy to prepare.
    </div> 
        ); 
    }) 
}); 
}

{% endhighlight %}

The following code example is used to position images and content.

{% highlight css %}

<style type="text/css" class="cssStyles">
   .ingredients 
   {
		height: 180px;
		margin-top: 8px;
	}
	img 
	{           
		float: left;        
		margin: 10px 26px 5px 1px;
	}
</style>

{% endhighlight %}

The following screenshot shows the first tab of the sub tab control.

![Getting-Started_images4](Getting-Started_images/Getting-Started_img4.png)

### Orientation change

To set the sub tab orientation to vertical use the **HeaderPosition** property. By default, the tab control is rendered in horizontal orientation.In the following code section,the tab header orientation is set to Left.

The following code section renders the sub tab element in the vertical orientation.

{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

 <div style="width: 500px">
    <ej-tab id="DishType">
        <e-tab-items>
            <e-tab-item id="Pizza" text="Pizza Menu">
                <e-content-template>
                    <div>
                        <div>
                            Rating :
                            <div>
                                <ej-rating id="gradenPizza" allow-reset="false" read-only="true" value="4" />
                            </div>
                            <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
                        </div>
                    </div>
                    <ej-tab id="pizza" header-position="@HeaderPosition.Left">
                        <e-tab-items>
                            <e-tab-item id="Corn-Spinach" text="Corn Spinach">
                                <e-content-template>
                                    <div>
                                        <img src=" http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach">
                                        <div class="ingredients">
                                            Rate    : $70<br />
                                            Ingredients : cheese, sweet corn &amp; green capsicums.
                                            <br />
                                            Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.
                                        </div>
                                    </div>
                                </e-content-template>
                            </e-tab-item>
                            <e-tab-item id="ChickenDelite" text="Chicken-Delite">
                                <e-content-template>
                                    <div>
                                        <img src=" http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="corn-spinach">
                                        <div class="ingredients">
                                            Rate    : $100<br />
                                            Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.
                                            <br />
                                            Description: This is a tasty, elegant chicken dish that is easy to prepare.
                                        </div>
                                    </div>
                                </e-content-template>
                            </e-tab-item>
                        </e-tab-items>
                    </ej-tab>
                </e-content-template>
            </e-tab-item>
        </e-tab-items>
        </ej-tab>
</div>

{% endhighlight %}

{% highlight Razor %}

/*Razor code to render Tab*/

    @Html.EJ().Tab("DishType").Items(data =>
{
    data.Add().ID("pizza").Text("Pizza Menu").ContentTemplate(@<div>
        Rating:
        @Html.EJ().Rating("RatingPizza").Value(4).Precision(Precision.Exact)
        <!--Food item description-->
        <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
        @firstTab()
    </div>);
    data.Add().ID("type").Text("Pizza Type").ContentTemplate(@<div></div>);
    data.Add().ID("sandwich").Text("Sandwich Type").ContentTemplate(@<div></div>);
})
    @helper firstTab(
{
    @Html.EJ().Tab("pizza").HeaderPosition(HeaderPosition.Left).Height("221").Items(data =>
    {
        data.Add().ID("Corn-Spinach").Text("Corn Spinach").ContentTemplate(@<div class="e-content">
            <img src=" http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach">
            <div class="ingredients">
                Rate    : $70<br />
                Ingredients : cheese, sweet corn &amp; green capsicums.
                <br />
                Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.
            </div>
        </div>
);
        data.Add().ID("ChickenDelite").Text("Chicken-Delite").ContentTemplate(@<div class="e-content">
            <img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="chicken-delite">
            <div class="ingredients">
                Rate    : $100<br />
                Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.
                <br />
                Description: This is a tasty, elegant chicken dish that is easy to prepare.
            </div>
        </div>
        );
    })
});

{% endhighlight %}

The following screenshot is the output of previous steps.

![Getting-Started_images5](Getting-Started_images/Getting-Started_img5.png)

### Configure contents to remaining tab items

The second and third tab contents are declared in the same method as the first tab content. These tabs also consist of rating and sub tab controls.

{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

<div style="width: 500px">

        <ej-tab id="tabSample">
            <e-tab-items>
                <e-tab-item id="Pizza" text="Pizza Menu">
                    <e-content-template>
                        <div>
                            Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                        </div>
                    </e-content-template>
                </e-tab-item>
                <e-tab-item id="Sandwich" text="Sandwich Menu ">
                    <e-content-template>
                        <div>
                            <div>
                                Rating :
                                <div>
                                    <ej-rating id="gradenPizza" allow-reset="false" read-only="true" value="4" />
                                </div>
                                <p>Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
                            </div>
                        </div>
                        <ej-tab id="SandwichMenu" header-position="@HeaderPosition.Left" height="221">
                            <e-tab-items>
                                <e-tab-item id="GardenVeggie" text="Garden Veggie">
                                    <e-content-template>
                                        <div class="e-content">
                                            <img src="http://js.syncfusion.com/demos/web/images/accordion/garden-veggie.png" alt="garden-veggie ">
                                            <div class="ingredients">
                                                Rate    : $55<br />
                                                Ingredients : grilled chicken, corn &amp;olives.
                                                <br />
                                                Description: To make an appetizer pizza made with crescent roll dough, baked and topped with flavored cream cheese and crispy fresh vegetables.
                                                Broccoli, carrots, and bell peppers make this a wonderfully delicious vegetarian treat
                                            </div>
                                        </div>
                                    </e-content-template>
                                </e-tab-item>
                                <e-tab-item id="ChickenTikka" text="Chicken Tikka ">
                                    <e-content-template>
                                        <div class="e-content">
                                            <img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-tikka.png" alt="chicken-tikka">
                                            <div class="ingredients">
                                                Rate    : $100<br />
                                                Ingredients : onions, grilled chicken, chicken salami &amp; tomatoes.
                                                <br />
                                                Description: Juicy chunks of boneless chicken roasted on open fire.This takeaway favorite is freezer-friendly and quick to reheat, giving you the chance to get ahead.
                                            </div>
                                        </div>
                                    </e-content-template>
                                </e-tab-item>
                                <e-tab-item id="PaneerTikka" text="Paneer Tikka ">
                                    <e-content-template>
                                        <div class="e-content">
                                            <img src="http://js.syncfusion.com/demos/web/images/accordion/paneer-tikka.png" alt="chicken-tikka">
                                            <div class="ingredients">
                                                Rate    : $150
                                                <br />
                                                Ingredients : onions, paneer & tomatoes.
                                                <br />
                                                Description: Delve into the tasty Paneer Tikka Kebabs made from marinated paneer or cottage cubes.
                                                Relish these grilled delicacies with green mint chutney and onion rings.
                                            </div>
                                        </div>
                                    </e-content-template>
                                </e-tab-item>
                            </e-tab-items>
                        </ej-tab>
                    </e-content-template>
                </e-tab-item>
                <e-tab-item id="Pasta" text="Pasta Menu">
                    <e-content-template>

                    </e-content-template>
                </e-tab-item>
            </e-tab-items>
        </ej-tab>

    </div>

{% endhighlight  %}

{% highlight Razor %}

/*Razor code to render Tab*/

@{Html.EJ().Tab("DishType").Items(data => 
        {
			data.Add().ID("type").Text("Pizza Menu").ContentTemplate(@<div> 
			Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
			@firstTab()
            </div>);
			data.Add().ID("sandwich").Text("Sandwich Menu").ContentTemplate(@<div>
			Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health. 
			@secondTab() 
			</div>);  
			data.Add().ID("Pasta").Text("Pasta Menu").ContentTemplate(@<div>
			</div>);  
		}).Render();

		@helper secondTab(){ 
		   @Html.EJ().Tab("Menu").HeaderPosition(HeaderPosition.Left).Height("221").Items(data =>
		   {       
				data.Add().ID("GardenVeggie").Text("Garden Veggie").ContentTemplate(@<div class="e-content">
				<img src="http://js.syncfusion.com/demos/web/images/accordion/garden-veggie.png" alt="garden-veggie "> 
				<div class="ingredients"> 
				Rate    : $55<br />  
				Ingredients : grilled chicken, corn &amp;olives.
				<br />    
				Description: To make an appetizer pizza made with crescent roll dough, baked and topped with flavored cream cheese and crispy fresh vegetables.
				Broccoli, carrots, and bell peppers make this a wonderfully delicious vegetarian treat
				</div> 
				</div>);
				data.Add().ID("ChickenTikka").Text("Chicken Tikka ").ContentTemplate(@<div class="e-content">  
				<img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-tikka.png" alt="chicken-tikka"> 
				<div class="ingredients">  
				Rate    : $100<br /> 
				Ingredients : onions, grilled chicken, chicken salami &amp; tomatoes.   
				<br />      
				Description: Juicy chunks of boneless chicken roasted on open fire.This takeaway favorite is freezer-friendly and quick to reheat, giving you the chance to get ahead. 
				</div>   
				</div>); 
				data.Add().ID("PaneerTikka").Text("Paneer Tikka  ").ContentTemplate(@<div class="e-content"> 
				<img src="http://js.syncfusion.com/demos/web/images/accordion/paneer-tikka.png" alt="paneer-tikka"> 
				<div class="ingredients"> 
				Rate    : $150  
				<br /> 
				Ingredients : onions, paneer & tomatoes.
				<br />
				Description: Delve into the tasty Paneer Tikka Kebabs made from marinated paneer or cottage cubes.
				Relish these grilled delicacies with green mint chutney and onion rings.
				</div> 
				</div>);
			})   
        }  
	</div>
{% endhighlight  %}
   
Add third tab contents in element during initialization using the content template option.

{% highlight CSHTML %}

/*ej-Tag Helper code to render Tab*/

<div style="width: 500px">

        <ej-tab id="tabSample">
            <e-tab-items>
                <e-tab-item id="Pizza" text="Pizza Menu">
                    <e-content-template>
                        <div>
                            Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                        </div>
                    </e-content-template>
                </e-tab-item>
                <e-tab-item id="Sandwich" text="Sandwich Menu ">
                    <e-content-template>
                        <p>Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health</p>
                    </e-content-template>
                </e-tab-item>
                <e-tab-item id="Pasta" text="Pasta Menu">
                    <e-content-template>
                        <div>
                            <div>
                                Rating :
                                <div>
                                    <ej-rating id="gradenPizza" allow-reset="false" read-only="true" value="4" />
                                </div>
                                <p>Pasta cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
                            </div>
                        </div>
                        <ej-tab id="tabSample12" header-position="@HeaderPosition.Left">
                            <e-tab-items>
                                <e-tab-item id="GardenVeggie" text="Garden Veggie">
                                    <e-content-template>
                                        <div class="e-content">
                                            <img src="http://js.syncfusion.com/demos/web/images/accordion/garden-veggie.png" alt="garden-veggie ">
                                            <div class="ingredients">
                                                Rate    : $55<br />
                                                Ingredients : grilled chicken, corn &amp;olives.
                                                <br />
                                                Description: To make an appetizer pizza made with crescent roll dough, baked and topped with flavored cream cheese and crispy fresh vegetables.
                                                Broccoli, carrots, and bell peppers make this a wonderfully delicious vegetarian treat
                                            </div>
                                        </div>
                                    </e-content-template>
                                </e-tab-item>
                                <e-tab-item id="ChickenTikka" text="Chicken Tikka ">
                                    <e-content-template>
                                        <div class="e-content">
                                            <img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-tikka.png" alt="chicken-tikka">
                                            <div class="ingredients">
                                                Rate    : $100<br />
                                                Ingredients : onions, grilled chicken, chicken salami &amp; tomatoes.
                                                <br />
                                                Description: Juicy chunks of boneless chicken roasted on open fire.This takeaway favorite is freezer-friendly and quick to reheat, giving you the chance to get ahead.
                                            </div>
                                        </div>
                                    </e-content-template>
                                </e-tab-item>
                                <e-tab-item id="PaneerTikka" text="Paneer Tikka ">
                                    <e-content-template>
                                        <div class="e-content">
                                            <img src="http://js.syncfusion.com/demos/web/images/accordion/paneer-tikka.png" alt="chicken-tikka">
                                            <div class="ingredients">
                                                Rate    : $150
                                                <br />
                                                Ingredients : onions, paneer & tomatoes.
                                                <br />
                                                Description: Delve into the tasty Paneer Tikka Kebabs made from marinated paneer or cottage cubes.
                                                Relish these grilled delicacies with green mint chutney and onion rings.
                                            </div>
                                        </div>
                                    </e-content-template>
                                </e-tab-item>
                            </e-tab-items>
                        </ej-tab>
                    </e-content-template>
                </e-tab-item>
            </e-tab-items>
        </ej-tab>

    </div>

{% endhighlight  %}

{% highlight Razor %}

/*Razor code to render Tab*/

@{Html.EJ().Tab("DishType").Items(data =>  
   {   
		data.Add().ID("type").Text("Pizza Menu").ContentTemplate(@<div>
		Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
		@firstTab()  
		</div>); 
		data.Add().ID("sandwich").Text("Sandwich Menu").ContentTemplate(@<div>
		Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health. 
		@secondTab() 
		</div>); 
		data.Add().ID("Pasta").Text("Pasta Menu").ContentTemplate(@<div>
		Pasta cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.  
		@thirdTab() 
		</div>); 
		}).Render();   

 @helper thirdTab(){
 @Html.EJ().Tab("PastaMenu").HeaderPosition(HeaderPosition.Left).Height("221").Items(data =>
 {     
	data.Add().ID("KheemaPasta").Text("Kheema Pasta ").ContentTemplate(@<div class="e-content">
	<img src="http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach.png" alt="kheema-pasta "> 
	<div class="ingredients"> 
	<p>     
	Rate : $30<br /> 
	Ingredients : chicken, onions, chilly, garlic &amp; tomatoes.<br />
	Description: Kheema pasta dish make with veg or non-veg type.It is delicious and can be served for dinner, brunch or evening snack. 
	</p> 
	</div>  
	</div>); 
	data.Add().ID("TunaPasta").Text("Tuna Pasta").ContentTemplate(@<div class="e-content">
	<img src="http://js.syncfusion.com/demos/web/images/accordion/garden-fresh.png" alt="tuna-pasta">
	<div class="ingredients">  
	<p>     
	Rate : $55<br /> 
	Ingredients : tomato ,olive, onions &amp;garlic.<br />  
	Description: Canned tuna is used to make this yummy tomato sauce.
	</p>       
	</div> 
	</div> );   
	data.Add().ID("ChannaPasta").Text("Channa Pasta").ContentTemplate(@<div class="e-content"> 
	<img src="http://js.syncfusion.com/demos/web/images/accordion/zesty-mushroons-and-tomatoes.png" alt="channa-asta"> 
	<div class="ingredients">   
	<p>              
	Rate : $30<br />     
	Ingredients : sauntered spinach mix, sweet corn, parsley &amp;mozzarella cheese.<br /> 
	Description: This is a pasta dish make with leftover Channa masala. This can be made from scratch too by making the Channa masala first and then tossing in the cooked pasta.
	</p>     
	</div>      
	</div>); 
	})     
}
{% endhighlight  %}

Apply the following styles to the tab.

{% highlight css %}

<style type="text/css" class="cssStyles">

	/*to reuse the previous style section code and following css*/        
   .sandwichImg, .pastaImg 
   {
		height: 25px;
		width: 25px;
	}
	.sandwichImg 
	{
		background: url("http://js.syncfusion.com/UG/Web/Content/rsz_garden-fresh.png") no-repeat;                       
	}
	.pastaImg 
	{
		background: url("http://js.syncfusion.com/UG/Web/Content/rsz_garden-veggie.png") no-repeat;                 
	}        
</style>

{% endhighlight %}

The following screenshot shows the second tab content in tab and the final hotel menu with rating, description, and ingredients of the item in the tab interface.

![Getting-Started_images6](Getting-Started_images/Getting-Started_img6.png)

