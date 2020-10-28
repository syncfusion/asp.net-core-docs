---
layout: post
title: Background Template | Menu | ASP.NET Core | Syncfusion
description: background template
platform: aspnet-core
control: Menu
documentation: ug
---

# Background Template

Menu control also provides support for template support. Normally Menu control can be created by using UL and LI tags in the preferred way. But in template supporting, you can customize the appearance of sub menu items rendering. 

Initialize the Template Menu as illustrated in the following code example. 

1. Add the following code in your View page.

{% highlight CSHTML %}

<ej-menu id="template" width="800px">
	<e-menu-items>
		<e-menu-item url="" text="Books">
			<e-menu-child-items>
				<e-menu-child-item>
					<e-content-template>
						<div class="temp temp1">
							<span>BOOKS</span>
							<ul>
								<li><a>New Releases</a></li>
								<li><a>Bestsellers</a></li>
								<li><a>Upcoming</a></li>
								<li><a>Box Sets</a></li>
							</ul>
							<ul>
								<li><a>HTML Basics</a></li>
								<li><a>JavaScript</a></li>
								<li><a>JQuery</a></li>
								<li><a>PHP Basics</a></li>
							</ul>
						</div>
					</e-content-template>
				</e-menu-child-item>
			</e-menu-child-items>
		</e-menu-item>
		<e-menu-item url="" text="Cameras">
			<e-menu-child-items>
				<e-menu-child-item>
					<e-content-template>
						<div class="temp temp1">
							<span>CAMERAS</span>
							<ul>
								<li><a>New Releases</a></li>
								<li><a>Bestsellers</a></li>
								<li><a>Upcoming</a></li>
								<li><a>Box Sets</a></li>
							</ul>
							<ul>
								<li><a>HTML Basics</a></li>
								<li><a>JavaScript</a></li>
								<li><a>JQuery</a></li>
								<li><a>PHP Basics</a></li>
							</ul>
						</div>
					</e-content-template>
				</e-menu-child-item>
			</e-menu-child-items>
		</e-menu-item>
		<e-menu-item url="" text="Movies">
			<e-menu-child-items>
				<e-menu-child-item>
					<e-content-template>
						<div class="temp temp3">
							<span>MOVIES</span>
							<ul>
								<li><a>Genobili Actions</a></li>
								<li><a>Jackie Rocks</a></li>
								<li><a>Men In Blue</a></li>
								<li><a>Human vs Alien</a></li>
							</ul>
							<ul>
								<li><a>Million Dreams</a></li>
								<li><a>Kung-fu</a></li>
							</ul>
						</div>
					</e-content-template>
				</e-menu-child-item>
			</e-menu-child-items>
		</e-menu-item>
		<e-menu-item url="" text="Musics">
			<e-menu-child-items>
				<e-menu-child-item>
					<e-content-template>
						<div class="temp temp4">
							<span>MUSICS</span>
							<ul>
								<li><a>New Releases</a></li>
								<li><a>Bestsellers</a></li>
								<li><a>Devotional</a></li>
								<li><a>Sufi & Ghazal</a></li>
							</ul>
							<ul>
								<li><a>Pop songs</a></li>
								<li><a>Rock Music</a></li>
							</ul>
						</div>
					</e-content-template>
				</e-menu-child-item>
			</e-menu-child-items>
		</e-menu-item>
		<e-menu-item url="" text="Gaming">
			<e-menu-child-items>
				<e-menu-child-item>
					<e-content-template>
						<div class="temp temp5">
							<span>GAMING</span>
							<ul>
								<li><a>Upcoming</a></li>
								<li><a>PC</a></li>
								<li><a>PS Vista</a></li>
								<li><a>PS3</a></li>
								<li><a>XBox</a></li>
								<li><a>Consoles</a></li>
							</ul>
							<ul>
								<li><a>FIFA 2999</a></li>
								<li><a>NBA Actions</a></li>
								<li><a>Crick Champions</a></li>
								<li><a>Carom legend</a></li>
							</ul>
						</div>
					</e-content-template>
				</e-menu-child-item>
			</e-menu-child-items>
		</e-menu-item>
	</e-menu-items>
</ej-menu>

{% endhighlight %}

2. Add the following code in your style section.

{% highlight css %}

<style type="text/css">
	 .temp {
        height: 237px;
        width: 375px;
        font-family: segoe UI;
        cursor: default;
        background-size: 100% 100%;
    }
    .temp span {
        color: red;
        float: left;
        font-size: 20px;
        left: 20px;
        position: relative;
        top: 25px;
        width: 100px;
    }
    .temp ul {
        float: left;
        font-size: 14px;
        left: -79px;
        list-style-type: none;
        margin: 0;
        padding: 0;
        position: relative;
        top: 50px;
        width: 128px;
    }
    .temp ul li {
        font-size: 13px;
    }
    .temp ul li a {
        text-decoration: underline;
        cursor: pointer;
        color: #000;
    }
    .temp1 {
        background-image: url("1.jpg");
    }
    .temp2 {
        background-image: url("2.jpg");
    }
    .temp3 {
        background-image: url("3.jpg");
    }
    .temp4 {
        background-image: url("4.jpg");
    }
    .e-menu.e-horizontal li > ul, .e-menu.e-horizontal li > ul > li:hover {
        background-color: #fff;
    }
    .e-menu.e-horizontal > li > ul:after {
        border-color: transparent transparent #fff;
    }
</style>

{% endhighlight %}
   
Execute the above code to render the following output.    
                   
![](Background-Template_images/Background-Template_img1.png)

Template
{:.caption}