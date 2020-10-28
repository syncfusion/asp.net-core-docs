---
layout: post
title: Gallery | Ribbon | ASP.NET Core | Syncfusion
description: Gallery
platform: aspnet-core
control: Ribbon
documentation: ug
keywords: gallery,ribbon gallery
---

# Gallery 

Galleries are used to display items that can be arranged in a grid-type layout. Items in the gallery can be customized as `Button/Menu` to display images, text, or both images and text. You can set `Type` of group as `Gallery`.

## Gallery Items

Gallery items are collection of the items to be included in the main gallery. You can set `Text` and `ToolTip` to gallery item which can also be customized with `ButtonSettings`. 

Number of `Columns` to display in gallery for each row should be specified and the Number of columns in Expanded State (`ExpandedColumns`) can be customized, if not set, `Columns` count will be set as default.
 
N> The `ItemHeight` and `ItemWidth` for gallery item can be set, if not set default values will be used.

{% highlight html %}

   <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>Open</a></li>
            </ul>
        </li>
   </ul>
   
{% endhighlight %}
   
{% highlight CSHTML %}
  
  <ej-ribbon id="defaultRibbon" width="500">
        <e-application-tab type=Menu menu-item-id="ribbonmenu">
        </e-application-tab>
        <e-tabs>
            <e-tab id="home" text="HOME">
                <e-groups>
                    <e-group text="Gallery" type="gallery">
                        <e-content>
                            <e-contents>
                                <e-content-groups>
                                    <e-content-group id="Gallery" columns="2" item-height="54" item-width="73" expanded-columns="3" type="Gallery">
                                        <e-gallery-items>
                                            <e-gallery-item text="GalleryContent1" tool-tip="GalleryContent1">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent1 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                            <e-gallery-item text="GalleryContent2" tool-tip="GalleryContent2">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent2 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                            <e-gallery-item text="GalleryContent3" tool-tip="GalleryContent3">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent3 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                            <e-gallery-item text="GalleryContent4" tool-tip="GalleryContent4">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent4 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                        </e-gallery-items>
                                    </e-content-group>
                                </e-content-groups>
                            </e-contents>
                        </e-content>
                    </e-group>
                </e-groups>
            </e-tab>
        </e-tabs>
  </ej-ribbon>
 
@section StyleSection {
       <link href="@Url.Content("~/css/ejthemes/ribbon-css/ej.icons.css")" rel="stylesheet" />
         <style type="text/css">
               .e-gallerycontent1 {
                   background-position: 0 -105px;
                }

               .e-gallerycontent2 {
                   background-position: -69px -105px;
                }

               .e-gallerycontent3 {
                    background-position: -136px -105px;
                }

               .e-gallerycontent4 {
                    background-position: 0 -53px;
                }

               .e-gbtnposition {
                    margin-top: 5px;
                }

              .e-gbtnimg {
                    background-image: url('../css/ejthemes/common-images/ribbon/homegallery.png');
                    background-repeat: no-repeat;
                    height: 64px;
                    width: 64px;
               }
          </style>
 }

{% endhighlight %}

![](Gallery_images/Gallery_img1.png)

Ribbon Gallery.
{:.caption}

![](Gallery_images/Gallery_img2.png)

Gallery at Expanded State
{:.caption}

## Custom Gallery Items

Custom gallery items are the additional items to be displayed at gallery expanded state. You can set `CustomItemType` as `Button` or `Menu`, Default is `Button`.

You can also set `Text` and `ToolTip` to custom gallery item which can also be customized with ButtonSettings/MenuSettings based on the CustomItemType specified.

{% highlight html %}

<ul id="ribbonmenu">
   <li>
      <a>FILE</a>
   </li>
</ul>
<ul id="custommenu">
   <li>
     <a>New Quick Step</a>
       <ul>
          <li>
            <a>Flag & Move</a>
          </li>
        </ul>
   </li>
</ul>      
    
{% endhighlight %}

{% highlight CSHTML %}

  <ej-ribbon id="defaultRibbon" width="500">
        <e-application-tab type=Menu menu-item-id="ribbonmenu">
        </e-application-tab>
        <e-tabs>
            <e-tab id="home" text="HOME">
                <e-groups>
                    <e-group text="Gallery" type="gallery">
                        <e-content>
                            <e-contents>
                                <e-content-groups>
                                    <e-content-group id="Gallery" columns="2" item-height="54" item-width="73" expanded-columns="3" type="Gallery">
                                        <e-gallery-items>
                                            <e-gallery-item text="GalleryContent1" tool-tip="GalleryContent1">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent1 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                            <e-gallery-item text="GalleryContent2" tool-tip="GalleryContent2">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent2 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                            <e-gallery-item text="GalleryContent3" tool-tip="GalleryContent3">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent3 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                            <e-gallery-item text="GalleryContent4" tool-tip="GalleryContent4">
                                                <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-gallerycontent4 e-gbtnimg" css-class="e-gbtnposition">
                                                </e-button-settings>
                                            </e-gallery-item>
                                        </e-gallery-items>
                                        <e-custom-gallery-items>
                                            <e-custom-gallery-item custom-item-type=Menu menu-id="custommenu">
                                                <e-menu-settings open-on-click="false">
                                                </e-menu-settings>
                                            </e-custom-gallery-item>
                                            <e-custom-gallery-item custom-item-type=Button text="Clear Formatting" tool-tip="Clear Formatting">
                                                <e-button-settings css-class="e-extrabtnstyle">
                                                </e-button-settings>
                                            </e-custom-gallery-item>
                                        </e-custom-gallery-items>
                                    </e-content-group>
                                </e-content-groups>
                            </e-contents>
                        </e-content>
                    </e-group>
                </e-groups>
            </e-tab>
        </e-tabs>
   </ej-ribbon>
    
   @section StyleSection{
       <link href="@Url.Content("~/css/ejthemes/ribbon-css/ej.icons.css")" rel="stylesheet" />
         <style type="text/css">
             .e-gallerycontent1{
		          background-position: 0 -105px;
              }
		      .e-gallerycontent2{
		          background-position: -69px -105px;
              }
		      .e-gallerycontent3{
		          background-position: -136px -105px;
               }
		      .e-gallerycontent4{
		          background-position: 0 -53px;
               }
		      .e-gbtnposition{
		          margin-top:5px;
               }
		      .e-gbtnimg{
		          background-image: url('../css/ejthemes/common-images/ribbon/homegallery.png');
		          background-repeat:no-repeat;
		          height:64px;
		          width:64px;
		       }
		       .e-extracontent .e-extrabtnstyle{
		         padding-left: 28px;
                 text-align: left;
	           }
              .e-pastetip {
                 background-image: url("../css/ejthemes/common-images/ribbon/paste.png");
                 background-repeat: no-repeat;
                 height: 64px;
                 width: 64px;
              }
         </style>
      }
      
{% endhighlight %}

![](Gallery_images/Gallery_img3.png)