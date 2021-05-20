---
layout: post
title: About Essential Studio ASP.NET Core Licensing | Syncfusion
description: Learn here about Syncfusion Essential Studio ASP.NET Core license key, how to generate the license key, how to register the license key, and more details.
platform: aspnet-core
control: Essential Studio
documentation: ug
---

# License Key Registration

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.

### ASP.NET Core

You can register the license key in Configure method of **Startup.cs**

{% tabs %}
{% highlight c# %}
// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
{
	//Register Syncfusion license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
	
	loggerFactory.AddConsole(Configuration.GetSection("Logging"));
	loggerFactory.AddDebug();

	...
	
}
{% endhighlight %}
{% endtabs %} 