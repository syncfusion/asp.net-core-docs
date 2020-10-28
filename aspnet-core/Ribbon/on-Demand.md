---
layout: post
title: OnDemand | Ribbon | ASP.NET Core | Syncfusion
description: OnDemand
platform: aspnet-core
control: Ribbon
documentation: ug
keywords: onDemand
---

# Load on Demand

Set `enable-on-demand` as true to enable load tab and backstage contents dynamically. Loading content on demand improves the initial rendering time of the ribbon by rendering tab and backstage content when tabs and backstage items are clicked.
 
{% highlight html %}

   <div id="newCon">
        <table>
            <tr>
                <td>
                    <button id="btn1" class="e-bsnewbtnstyle">Blank WorkBook</button>
                </td>
            </tr>
        </table>
   </div>
   <div id="accountCon">
        <div class="e-userDiv">
            <span>User Information</span>
            <div>
                <div class="e-accuser e-newpageicon"></div>
                <div class="e-userCon">
                    <div>user</div>
                    <div>xy@syncfusion.com</div>
                </div>
            </div>
        </div>
        <a href="#">Sign out</a>
   </div>
                
  {% endhighlight  %}  
  
  {% highlight CSHTML %}
       
  <ej-ribbon id="defaultRibbon" width="50%" enable-on-demand="true">
     <e-application-tab type=Backstage>
        <e-backstage-settings text="FILE" height="360" width="600" headerWidth="125">
            <e-pages>
                <e-page-collection id="new" text="New" content-id="newCon"></e-page-collection>
                <e-page-collection id="close" text="Close" enable-separator="true" item-type=Button></e-page-collection>
                <e-page-collection id="account" text="Office Account" content-id="accountCon"></e-page-collection>
            </e-pages>
        </e-backstage-settings>
     </e-application-tab>
     <e-tabs>
      <e-tab id="home" text="HOME">
        <e-groups>
            <e-group text="Clipboard" align-type=Columns>
               <e-group-expander-settings tool-tip="Clipboard"></e-group-expander-settings>
                <e-content>
                    <e-contents>
                    <e-defaults width="50" height="70" type="Button" is-big="true"></e-defaults>
                        <e-content-groups>
                            <e-content-group id="paste" text="paste" tool-tip="Paste">
                                <e-button-settings content-type="ImageOnly" prefix-icon="e-icon e-ribbon e-ribbonpaste">
                                </e-button-settings>
                            </e-content-group>
                        </e-content-groups>                     
                    </e-contents>
                </e-content>
            </e-group>
            <e-group text="New" align-type=Rows>
                <e-content>
                    <e-contents>
                        <e-content-groups>
                            <e-content-group id="new" text="New" tool-tip="New">
                                <e-button-settings content-type=ImageOnly image-position=ImageTop prefix-icon="e-icon e-ribbon e-new">
                                </e-button-settings>
                            </e-content-group>
                        </e-content-groups>
                        <e-defaults type=Button width="60px" height="70px"></e-defaults>
                    </e-contents>
                </e-content>
            </e-group>
      </e-groups>
     </e-tab>
      <e-tab id="layout" text="LAYOUT">
          <e-groups>
              <e-group text="Alignment" align-type=Rows>
                  <e-content>
                      <e-contents>
                          <e-content-groups>
                              <e-content-group id="bullet" text="Bullet Format" tool-tip="Bullets">
                                  <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-ribbon e-bullet">
                                  </e-button-settings>
                              </e-content-group>
                              <e-content-group id="number" text="Number Format" tool-tip="Numbering">
                                  <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-ribbon e-numbericon">
                                  </e-button-settings>
                              </e-content-group>
                           </e-content-groups>
                          <e-defaults type=Button is-big="false"></e-defaults>
                      </e-contents>
                  </e-content>
              </e-group>
          </e-groups>
      </e-tab>
     </e-tabs>
   </ej-ribbon>

@section ScriptSection{
 <script>
        $("#btn1").ejButton({
           size: "large",
           height: 200,
           width: 205,
           contentType: "textandimage",
           imagePosition: "imagetop",
           prefixIcon: "e-icon e-blank e-infopageicon"
         });
</script>
}

@section StyleSection{
    <link href="@Url.Content("~/css/ejthemes/ribbon-css/ej.icons.css")" rel="stylesheet" />
    <style>
        .e-accuser {
            background-image: url('../css/ejthemes/common-images/ribbon/user.jpg');
        }
        .e-blank {
            background-image: url('../css/ejthemes/common-images/ribbon/blank.png');
        }
        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }
        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }
        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }
        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>
}

{% endhighlight %}

![](On_Demand_images/onDemand_img1.png)

# Initially Collapsible

Set `collapsible` as true to render ribbon control in collapsed state, which results ribbon tabs to render without any content initially.
While using initially collapsible ribbon with `enable-on-demand` feature improves the performance by reducing initial loading time of ribbon.

{% highlight html %}

   <div id="newCon">
        <table>
            <tr>
                <td>
                    <button id="btn1" class="e-bsnewbtnstyle">Blank WorkBook</button>
                </td>
            </tr>
        </table>
   </div>
   <div id="accountCon">
        <div class="e-userDiv">
            <span>User Information</span>
            <div>
                <div class="e-accuser e-newpageicon"></div>
                <div class="e-userCon">
                    <div>user</div>
                    <div>xy@syncfusion.com</div>
                </div>
            </div>
        </div>
        <a href="#">Sign out</a>
   </div>
                
  {% endhighlight  %}  
  
  {% highlight CSHTML %}
       
  <ej-ribbon id="defaultRibbon" width="50%" enable-on-demand="true" collapsible="true">
     <e-application-tab type=Backstage>
        <e-backstage-settings text="FILE" height="360" width="600" headerWidth="125">
            <e-pages>
                <e-page-collection id="new" text="New" content-id="newCon"></e-page-collection>
                <e-page-collection id="close" text="Close" enable-separator="true" item-type=Button></e-page-collection>
                <e-page-collection id="account" text="Office Account" content-id="accountCon"></e-page-collection>
            </e-pages>
        </e-backstage-settings>
     </e-application-tab>
     <e-tabs>
      <e-tab id="home" text="HOME">
        <e-groups>
            <e-group text="Clipboard" align-type=Columns>
               <e-group-expander-settings tool-tip="Clipboard"></e-group-expander-settings>
                <e-content>
                    <e-contents>
                    <e-defaults width="50" height="70" type="Button" is-big="true"></e-defaults>
                        <e-content-groups>
                            <e-content-group id="paste" text="paste" tool-tip="Paste">
                                <e-button-settings content-type="ImageOnly" prefix-icon="e-icon e-ribbon e-ribbonpaste">
                                </e-button-settings>
                            </e-content-group>
                        </e-content-groups>                     
                    </e-contents>
                </e-content>
            </e-group>
            <e-group text="New" align-type=Rows>
                <e-content>
                    <e-contents>
                        <e-content-groups>
                            <e-content-group id="new" text="New" tool-tip="New">
                                <e-button-settings content-type=ImageOnly image-position=ImageTop prefix-icon="e-icon e-ribbon e-new">
                                </e-button-settings>
                            </e-content-group>
                        </e-content-groups>
                        <e-defaults type=Button width="60px" height="70px"></e-defaults>
                    </e-contents>
                </e-content>
            </e-group>
      </e-groups>
     </e-tab>
      <e-tab id="layout" text="LAYOUT">
          <e-groups>
              <e-group text="Alignment" align-type=Rows>
                  <e-content>
                      <e-contents>
                          <e-content-groups>
                              <e-content-group id="bullet" text="Bullet Format" tool-tip="Bullets">
                                  <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-ribbon e-bullet">
                                  </e-button-settings>
                              </e-content-group>
                              <e-content-group id="number" text="Number Format" tool-tip="Numbering">
                                  <e-button-settings content-type=ImageOnly prefix-icon="e-icon e-ribbon e-numbericon">
                                  </e-button-settings>
                              </e-content-group>
                           </e-content-groups>
                          <e-defaults type=Button is-big="false"></e-defaults>
                      </e-contents>
                  </e-content>
              </e-group>
          </e-groups>
      </e-tab>
     </e-tabs>
   </ej-ribbon>

@section ScriptSection{
 <script>
        $("#btn1").ejButton({
           size: "large",
           height: 200,
           width: 205,
           contentType: "textandimage",
           imagePosition: "imagetop",
           prefixIcon: "e-icon e-blank e-infopageicon"
         });
</script>
}

@section StyleSection{
    <link href="@Url.Content("~/css/ejthemes/ribbon-css/ej.icons.css")" rel="stylesheet" />
    <style>
        .e-accuser {
            background-image: url('../css/ejthemes/common-images/ribbon/user.jpg');
        }
        .e-blank {
            background-image: url('../css/ejthemes/common-images/ribbon/blank.png');
        }
        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }
        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }
        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }
        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>
}

{% endhighlight %}

![](On_Demand_images/onDemand_img2.png)