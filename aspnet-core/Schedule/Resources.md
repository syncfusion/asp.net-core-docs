---
title: Schedule - Resource handling with multiple option
description: Handling multiple resources in Scheduler
platform: aspnet-core
control: schedule
documentation: ug
keywords: resource, resources, multiple resources, grouping 
---
# Resources

The Scheduler provides **Resources** support, with which the single Scheduler is shared by multiple resources simultaneously. Each resource in the Scheduler is arranged in a column/row wise, with individual spacing to display all its respective appointments on a single page. It also supports the grouping of resources, thus enabling the categorization of resources in a hierarchical structure and shows it either in expandable groups (**Horizontal** **view**) or else vertical hierarchy one after the other (**Vertical** **view**).

One or more resources can be assigned to the Scheduler appointments by making selection of the resource options available in the appointment window.

## Fields of Resources

The default options available within the `Resources` collection are as follows,

### Name (**String**)

A unique resource name which is used for differentiating various resource objects while grouping it in levels.

### Title (**String**)

It holds the title name of the resource field to be displayed on the Scheduler appointment window.

### Field (**String**)

It holds the name of the resource field to be bound to the Scheduler appointments which contains the resource Id.

### AllowMultiple (**Boolean**)

When set to true, allows multiple selection of resource names, thus creating multiple instances of same appointment for the selected resources.

### ResourceSettings (**Object**)

It holds the field names of the resources dataSource to be bound to the Scheduler.

The following are the resource fields which must be defined within the **ResourceSettings** that holds the appropriate column names from the dataSource.

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Text<br/><br/></td><td>
Binds the `Text` field name in the dataSource to the ResourceSettings <b>Text</b>. These text gets listed out in the resources field of the appointment window. It’s mandatory.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Id<br/><br/></td><td>
Binds the `Id` field name in the dataSource to the ResourceSettings <b>Id</b>. It’s mandatory.<br/><br/><br/><br/></td></tr>
<tr>
<td>
GroupId<br/><br/></td><td>
Binds the `GroupId` field name in the dataSource to the ResourceSettings <b>GroupId</b>. This field is not necessary for a resource object (resource data) defined as first level within the resources collection.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Color<br/><br/></td><td>
Binds the `Color` field name in the dataSource to the ResourceSettings <b>Color</b>. It is optional.<br/><br/><br/><br/></td></tr>
<tr>
<td>
AppointmentClass<br/><br/></td><td>
Binds the `AppointmentClass` field name in the dataSource. It applies the custom CSS class name to the appointments based on the resources.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Start<br/><br/></td><td>
Binds the starting work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the starting work hour for specific resources.<br/><br/><br/><br/></td></tr>
<tr>
<td>
End<br/><br/></td><td>
Binds the end work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the end work hour for specific resources.<br/><br/><br/><br/></td></tr>
<tr>
<td>
WorkWeek<br/><br/></td><td>
Binds the resources working days field name in the dataSource. It's optional, and accept array of strings which is nothing but only the week day names. When provided with some values (array of day names), only those days will render for the specific resources.<br/><br/><br/><br/></td></tr>
</table>

**Example**: To set the resources options using all the above specified fields,

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", RoomId = "2" });

    <!-- Datasource for Grouping -->
    List<String> Group = new List<String> {"Owners", "Rooms" };

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398" });
    Owner.Add(new ResourceFields { Id = "2", Text = "Steven", Color = "#56ca95" });

    <!-- Datasource for Rooms -->
    List<ResourceFields> Room = new List<ResourceFields>();
    Room.Add(new ResourceFields { Id = "1", Text = "Room1", Color = "#f8a398", GroupId = "1", WorkHourStart = 10, WorkHourEnd = 18, CustomDays = new List<string>() { "Monday", "Wednesday", "Friday" } });
    Room.Add(new ResourceFields { Id = "2", Text = "Room2", Color = "#56ca85", GroupId = "2", WorkHourStart = 6, WorkHourEnd = 10, CustomDays = new List<string>() { "Monday", "Saturday" } });
    Room.Add(new ResourceFields { Id = "3", Text = "Room3", Color = "#56ac88", GroupId = "2", WorkHourStart = 11, WorkHourEnd = 15, CustomDays = new List<string>() { "Tuesday", "Friday" } });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="false">
            <e-resource-settings datasource="Owner" text="Text" id="Id" color="Color" ></e-resource-settings>
        </e-resource>
        <e-resource field="RoomId" title="Room" name="Rooms" allow-multiple="true">
            <e-resource-settings datasource="Room" text="Text" id="Id" color="Color" group-id="GroupId" start="WorkHourStart" end="WorkHourEnd" work-week="CustomDays"></e-resource-settings>
        </e-resource>
    </e-resources>
    <e-group resources="Group"></e-group>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId,RoomId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> The resource object defined at **First Level** within the **Resources** collection doesn’t make use of the **GroupId** field, as there is no previous levels applicable to map.

## Data Binding

The resources data can be bound to the Schedule control through the **ResourceSettings** option available within the **Resources** property. The data-binding can be done either using JSON object collection or DataManager (`ej.DataManager`) instance which contains the resources related data.

### List Data

**Example**: To set the resource data with array of **List** data collection

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398", GroupId = "1" });
    Owner.Add(new ResourceFields { Id = "2", Text = "Steven", Color = "#56ca95", GroupId = "1" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="false">
            <e-resource-settings datasource="Owner" text="Text" id="Id" color="Color"></e-resource-settings>
        </e-resource>
    </e-resources>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

### Remote Data

**Example**: To set the resource data through remote service URL,

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" views="views" current-view="Month">
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="false">
            <e-resource-settings text="CategoryName" id="CategoryId" query="ej.Query().select('CategoryID','CategoryName').from('Categories').take(5)">
                <e-datamanager url="http://mvc.syncfusion.com/OdataServices/Northwnd.svc"></e-datamanager>
            </e-resource-settings>
        </e-resource>
    </e-resources>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## Multiple Resources (Without Grouping)

It is possible to display the Scheduler in default look without visually showcasing all the resources on it, but it allow the user to assign the required resources to the appointments through the appointment window resource options.

The appointments belonging to all the resources will be displayed on the Scheduler which will be differentiated based on the resource color assigned in the **ResourceSettings** (depicting to which resource that particular appointment belongs). 

**Example**: To display default Scheduler with multiple resource options in the appointment window,

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398", GroupId = "1" });
    Owner.Add(new ResourceFields { Id = "2", Text = "Steven", Color = "#56ca95", GroupId = "1" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="true">
            <e-resource-settings datasource="Owner" text="Text" id="Id" color="Color">
            </e-resource-settings>
        </e-resource>
    </e-resources>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> Setting **allow-multiple** to **true** in the above code snippet allows the user to select multiple resources in the appointment window and also creates multiple copies of the same appointment in the Scheduler for each resources while saving.

## Grouping

Scheduler supports both single and multiple levels of resource grouping that can be customized either in horizontal or vertical Scheduler views. In Vertical view - the levels are displayed in a tree structure one after the other, but in horizontal view – the levels are grouped in a vertically expandable/collapsible structure.

### Single-Level

This type of grouping allows the Scheduler to display all the resources at a single level simultaneously. The appointments will make use of the **Color** defined for the first resource instance as its background color. 

**Example**: To display the Scheduler with single level resource grouping options,

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });

    <!-- Define the Group -->
    List<String> Group = new List<String>();
    Group.Add("Owners");

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398", GroupId = "1" });
    Owner.Add(new ResourceFields { Id = "2", Text = "Steven", Color = "#56ca95", GroupId = "1" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="true">
            <e-resource-settings datasource="Owner" text="Text" id="Id" color="Color">
            </e-resource-settings>
        </e-resource>
    </e-resources>
    <e-group resources="Group"></e-group>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> The **name** field mentioned in the **Resource** object needs to be specified within the **Group** property in order to enable the grouping option in Scheduler.

### Multi-Level

This type of grouping displays the resources in the Scheduler at multiple levels with a set of resources grouped under each parent. The appointments will make use of the **Color** defined for the first/top level resource instance as its background color.  

**Example**: To display the Scheduler with multiple level resource grouping options,

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", RoomId = "1", OwnerId = "1" });

    <!-- Datasource for Grouping -->
    List<String> Group = new List<String>();
    Group.Add("Owners");
    Group.Add("Rooms");

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398", GroupId = "1" });
    Owner.Add(new ResourceFields { Id = "2", Text = "Steven", Color = "#56ca95", GroupId = "1" });

    <!-- Datasource for Rooms -->
    List<ResourceFields> Room = new List<ResourceFields>();
    Room.Add(new ResourceFields { Id = "1", Text = "Room1", Color = "#f8a398", GroupId = "1" });
    Room.Add(new ResourceFields { Id = "2", Text = "Room2", Color = "#56ca85", GroupId = "2" });
    Room.Add(new ResourceFields { Id = "3", Text = "Room3", Color = "#56ac88", GroupId = "2" });

}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="false">
            <e-resource-settings datasource="Owner" text="Text" id="Id" color="Color">
            </e-resource-settings>
        </e-resource>
        <e-resource field="RoomId" title="Room" name="Rooms" allow-multiple="true">
            <e-resource-settings datasource="Room" text="Text" id="Id" group-id="GroupId" color="Color">
            </e-resource-settings>
        </e-resource>
    </e-resources>
    <e-group resources="Group"></e-group>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId,RoomId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> Here, the appointments will make use of the **Color** defined for the Owners resource instance as its background color.

### Different Working days and Hours for Resources

It is possible to assign different workdays and workhours for each resources present within the Scheduler. The process of assigning different working days for every individual resources is applicable only for the vertical Scheduler mode and not for timeline view, whereas the customization of workhours for each resources is applicable on both the Scheduler orientation. The custom workdays and workhours needs to be defined within the `ResourceSettings` property using the following 3 sub-properties available within it.

* **Start** – To define the work start hour for each individual resources
* **End** – To define the work end hour for each individual resources
* **WorkWeek** – To define the working days for each individual resources

**Example**: To display the Scheduler with each resources having different workhours and workdays, the code example is depicted below.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", RoomId = "1", OwnerId = "5" });

    <!-- Datasource for Grouping -->
    List<String> Group = new List<String>();
    Group.Add("Rooms");
    Group.Add("Owners");

    <!-- Datasource for Rooms -->
    List<ResourceFields> Room = new List<ResourceFields>();
    Room.Add(new ResourceFields { Id = "1", Text = "Room1", Color = "#f8a398", GroupId = "1" });
    Room.Add(new ResourceFields { Id = "2", Text = "Room2", Color = "#56ca95", GroupId = "1" });

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Text = "Nancy", Id = "1", GroupId = "1", Color = "#ffaa00", WorkHourStart = 10, WorkHourEnd = 18, CustomDays = new List<string> { "monday", "wednesday", "friday" } });
    Owner.Add(new ResourceFields { Text = "Steven", Id = "3", GroupId = "2", Color = "#f8a398", WorkHourStart = 6, WorkHourEnd = 10, CustomDays = new List<string> { "tuesday", "thursday" } });
    Owner.Add(new ResourceFields { Text = "Michael", Id = "5", GroupId = "1", Color = "#7499e1", WorkHourStart = 11, WorkHourEnd = 15, CustomDays = new List<string> { "sunday", "tuesday", "thursday", "saturday" } });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-resources>
        <e-resource field="RoomId" title="Room" name="Rooms" allow-multiple="false">
            <e-resource-settings datasource="Room" text="Text" id="Id" group-id="GroupId" color="Color">
            </e-resource-settings>
        </e-resource>
        <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="true">
            <e-resource-settings datasource="Owner" text="Text" id="Id" group-id="GroupId" color="Color" start="WorkHourStart" end="WorkHourEnd" work-week="CustomDays">
            </e-resource-settings>
        </e-resource>
    </e-resources>
    <e-group resources="Group"></e-group>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"RoomId,OwnerId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}
