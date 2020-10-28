---
layout: post
title: Localization in ComboBox control for Syncfusion ASP.NET CORE
description: Localization support to ComboBox control for Syncfusion ASP.NET CORE
platform: core
control: ComboBox
documentation: ug
keywords: locale, ComboBox
---

# Localization

The Localization library allows you to localize the static text content of the **noRecordsTemplate** and **actionFailureTemplate** &nbsp;properties according to the culture currently assigned to the ComboBox.

| Locale key | en-US (default)  |
|------|------|-------------|
| noRecordsTemplate |  No records found |
| actionFailureTemplate | The request failed |

## Loading translations

To load translation object to your application, use the `load` function of **L10n** class.

In the following sample, French culture is set to the ComboBox and no data is loaded. Hence, the `noRecordsTemplate` property displays its text in French culture initially, and if the sample is run offline, the `actionFailureTemplate` property displays its text appropriately.


{% highlight html %}

<div class="frame">
        <div class="control">
            <ej-combo-box id="searchCustomer" query="ej.Query().from('Suppliers').select('SupplierID', 'ContactName').take(0)" no-records-template="<span class='norecord'> NO DATA AVAILABLE</span>" placeholder="Select a customer" width="100%" locale="fr-BE">
                <e-datamanager url="//js.syncfusion.com/ejServices/wcf/NorthWind.svc/" offline="false" cross-domain="true"></e-datamanager>
                <e-combo-box-fields text="ContactName" value="SupplierID" />
            </ej-combo-box>
        </div>
    </div>
    <script>
        ej.ComboBox.locale["fr-BE"]={
                'noRecordsTemplate': "Aucun enregistrement trouvé",
                'actionFailureTemplate': "Modèle d'échec d'action"
            }
        
    </script>


{% endhighlight %}

{% highlight c# %}

public ActionResult Databindingremote()
        {
            return View();
        }

{% endhighlight %}

![](Combobox_localization_images/localization.png)