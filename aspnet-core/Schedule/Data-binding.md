---
title: Data binding with Schedule	
description: Binding local and remote data to Scheduler
platform: aspnet-core
control: schedule
documentation: ug
keywords: data binding, local data, remote data 
---
# Data Binding

## Appointment Fields

The below listed names are the appointment fields which holds the appropriate column names from the dataSource.

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Id<br/><br/></td><td>
Binds the <b>Id</b> field name for indexing and performing CRUD operation on the appointments. It’s optional.<br/><br/></td></tr>
<tr>
<td>
StartTime<br/><br/></td><td>
Binds the appointment start time field name which is <b>mandatory</b> and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
StartTimeZone<br/><br/></td><td>
Binds the name of the start timezone field in the dataSource and also its related validation rules. If the <b>StartTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td></tr>
<tr>
<td>
EndTime<br/><br/></td><td>
Binds the appointment end time field name which is <b>mandatory</b> and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
EndTimeZone<br/><br/></td><td>
Binds the name of the end timezone field in the dataSource and also its related validation rules. If the <b>EndTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td></tr>
<tr>
<td>
Subject<br/><br/></td><td>
Binds the appointment subject field name which holds the summary of the appointment and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
Location<br/><br/></td><td>
Binds the name of the location field and also its related validation rules. It indicates the appointment location/occurrence place. This field needs to be bind to the Scheduler, when an API <b>ShowLocationField</b> is set to true.<br/><br/></td></tr>
<tr>
<td>
Description<br/><br/></td><td>
Binds the appointment description field name and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
AllDay<br/><br/></td><td>
Binds the name of the <b>AllDay</b> field. It accepts the <b>boolean</b> value and indicates whether the appointment is an all-day appointment or not.<br/><br/></td></tr>
<tr>
<td>
Categorize<br/><br/></td><td>
Binds the name of the categorize field and also its related validation rules. It indicates the category or status value (red categorize, green, yellow and so on). <br/><br/></td></tr>
<tr>
<td>
Priority<br/><br/></td><td>
Binds the name of the priority field and its related validation rules, which indicates the priority (high, low, medium and none) of the appointments. This field should be bind to the Scheduler, when <b>PrioritySettings.Enable</b> is set to true.<br/><br/></td></tr>
<tr>
<td>
ResourceFields<br/><br/></td><td>
Binds one or more fields in the resource collection. It maps the resource field names with the appointments, denoting to which resource the appointments actually belongs.<br/><br/></td></tr>
<tr>
<td>
Recurrence<br/><br/></td><td>
Binds the name of the recurrence field. It accepts the <b>boolean</b> value and indicates whether the appointment is a recurrence appointment or not.<br/><br/></td></tr>
<tr>
<td>
RecurrenceRule<br/><br/></td><td>
Binds the name of the recurrenceRule field. It holds the recurrence pattern associated with the appointments.<br/><br/></td></tr>
<tr>
<td>
RecurrenceId<br/><br/></td><td>
Binds the recurrence Id field which acts as a parent id for Scheduler recurrence appointments.<br/><br/></td></tr>
<tr>
<td>
RecurrenceExDate<br/><br/></td><td>
Binds the recurrence Exception field which accepts the recurrence Exception date values.<br/><br/></td></tr>
</table>

The below example depicts the appointment fields accepting the string type mapper fields.

Create a new Class **ScheduleData** to define the appointment related data to be passed to the Scheduler as mentioned below,

{% highlight c# %}

public class ScheduleData 
    {
        public string Id { get; set; }
        public string Subject { get; set; }
        public string Description { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public string Categorize { get; set; }
        public string RoomId { get; set; }
        public string OwnerId { get; set; }
        public string Priority { get; set; }
        public bool AllDay { get; set; }
        public bool Recurrence { get; set; }
        public string RecurrenceRule { get; set; }
    }
{% endhighlight %}

Also, define the below model classes in your application, if there is a need to make use of the features such as multiple resources, categories, priorities, context menu and timezone collection in your sample application.
   
{% highlight c# %}

// Define the below class, whenever the multiple resources and grouping feature is used in your sample project.
public class ResourceFields
    {
        public string Text { set; get; }
        public string Id { set; get; }
        public string GroupId { set; get; }
        public string Color { set; get; }
        public int WorkHourStart { set; get; }
        public int WorkHourEnd { set; get; }
        public List<string> CustomDays { set; get; }
    }
    
// Define the below class, whenever the category related data is to be used in Scheduler.
public class CategorizeSettings
    {
        public string Text { set; get; }
        public string Id { set; get; }
        public string FontColor { set; get; }
        public string Color { set; get; }
    }

// Define the below class, whenever the priorities are to be used for Scheduler appointments.
public class PrioritySettings
    {
        public string Text { set; get; }
        public string Value { set; get; }
    }
    
// Define the below two classes (Appointment and Cells), if context menu items are to be used in the Scheduler.
public class Appointment
    {
        public string Text { set; get; }
        public string Id { set; get; }
    }
public class Cells
    {
        public string Text { set; get; }
        public string Id { set; get; }
        public string ParentId { set; get; }
    }
    
// Define the below class, if timezone collection to be specified for Scheduler.
public class TimezoneCollection
    {
        public string Text { set; get; }
        public string Id { set; get; }
        public string Value { set; get; }
    }

{% endhighlight %}


{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{ 
    //Datasource for appointments
    List<ScheduleData> Appoint = new List<ScheduleData>();
    Appoint.Add(new ScheduleData { Id = "1", Subject = "Meeting", StartTime = new DateTime(2016, 11, 10, 10, 00, 00), EndTime = new DateTime(2016, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", OwnerId = "1" });

    //Datasource for Grouping Resources
    List<String> Group = new List<String>();
    Group.Add("Owners");

    //Datasource for Resources
    List<ResourceFields> Resources = new List<ResourceFields>();
    Resources.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398" });
    Resources.Add(new ResourceFields { Id = "3", Text = "Steven", Color = "#56ca85" });
    Resources.Add(new ResourceFields { Id = "5", Text = "Michael", Color = "#51a0ed" });
}

   <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2016, 11, 7)" show-location-field="true">
        <e-resources>
            <e-resource field="OwnerId" title="Owner" name="Owners" allow-multiple="true">
                <e-resource-settings datasource="Resources" text="Text" id="Id" color="Color">
                </e-resource-settings>
            </e-resource>
        </e-resources>
        <e-group resources="Group"></e-group>
        <e-categorize-settings enable="true"></e-categorize-settings>
        <e-priority-settings enable="true"></e-priority-settings>
        <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' start-time-zone='"StartTimeZone"' end-time='"EndTime"' end-time-zone='"EndTimeZone"' description='"Description"' location='"Location"' all-day='"AllDay"' priority='"Priority"' categorize='"Categorize"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' recurrence-id="RecurrenceId" recurrence-ex-date="RecurrenceExDate" resource-fields='"OwnerId"'>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

## Appointment Field Validation

It is possible to validate the required fields of the appointment window from client-side before submitting it, by adding appropriate validation rules to each of the fields. The appointment fields have been extended to accept both String and object type values. Therefore, in order to perform validations, it is necessary to specify object values for the appointment fields.    

Refer the appointment fields specified with validation rules from the following code example.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    //Datasource for appointments
    List<ScheduleData> Appoint = new List<ScheduleData>();
    Appoint.Add(new ScheduleData { Id = "1", Subject = "Meeting", StartTime = new DateTime(2016, 11, 10, 10, 00, 00), EndTime = new DateTime(2016, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", Categorize = "4" });

    //Datasource for CategorizeSettings
    List<CategorizeSettings> CategorizeValue = new List<CategorizeSettings>();
    CategorizeValue.Add(new CategorizeSettings { Text = "Blue Category", Id = "1", Color = "#43b496", FontColor = "#ffffff" });
    CategorizeValue.Add(new CategorizeSettings { Text = "Green Category", Id = "2", Color = "#7f993e", FontColor = "#ffffff" });
    CategorizeValue.Add(new CategorizeSettings { Text = "Orange Category", Id = "3", Color = "#cc8638", FontColor = "#ffffff" });
    CategorizeValue.Add(new CategorizeSettings { Text = "Purple Category", Id = "4", Color = "#ab54a0", FontColor = "#ffffff" });
    CategorizeValue.Add(new CategorizeSettings { Text = "Red Category", Id = "5", Color = "#dd654e", FontColor = "#ffffff" });
    CategorizeValue.Add(new CategorizeSettings { Text = "Yellow Category", Id = "6", Color = "#d0af2b", FontColor = "#ffffff" });

    //Validation Rules
    AppointmentSettings Subject = new AppointmentSettings() { Field = "Subject", ValidationRules = new Dictionary<string, object>() { { "required", true } } };
    AppointmentSettings Location = new AppointmentSettings() { Field = "Location", ValidationRules = new Dictionary<string, object>() { { "required", true }, { "customRule", "/^[a-zA-Z0-9- ]*$/" } } };
    AppointmentSettings Description = new AppointmentSettings() { Field = "Description", ValidationRules = new Dictionary<string, object>() { { "required", true }, { "minlength", 5 }, { "maxlength", 500 } } };
    Dictionary<string, object> ValidationMessage = new Dictionary<string, object>();
    ValidationMessage.Add("required", "Categories are required.");
    AppointmentSettings Categorize = new AppointmentSettings() { Field = "Categorize", ValidationRules = new Dictionary<string, object>() { { "required", true }, { "messages", ValidationMessage } } };
}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2016, 11, 8)" show-location-field="true">
        <e-categorize-settings datasource="CategorizeValue" enable="true" allow-multiple="false" id="Id" text="Text" color="Color" font-color="FontColor"></e-categorize-settings>
        <e-appointment-settings datasource='Appoint' id="Id" subject='Subject' start-time='"StartTime"' end-time='"EndTime"' description='Description' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' location="Location" categorize="Categorize">
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

{% highlight html %}

<script src="@Url.Content("~/Scripts/jquery.validate.min.js")"></script>
<script src="@Url.Content("~/Scripts/jquery.validate.unobtrusive.min.js")"></script>
<script type="text/javascript">
    $(function () {
        $.validator.addMethod("customRule", function (value, element, options) {
            var ptn = /^[a-zA-Z0-9- ]*$/;
            return ptn.test(value);
        }, "Special character(s) not allowed in Location field");
    });
</script>

{% endhighlight %}

## Binding to Simple List Data Array

Scheduler supports binding the appointment data to it through the list of appointment object collection as depicted in the below code example.

**Example** - Array of List Data Binding

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    //Datasource for appointments
    List<ScheduleData> Appoint = new List<ScheduleData>();
    Appoint.Add(new ScheduleData { Id = "1", Subject = "Meeting", StartTime = new DateTime(2016, 11, 10, 10, 00, 00), EndTime = new DateTime(2016, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2016, 11, 8)">
        <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

## Binding Remote Data Service

The appointment data can be bound to the Scheduler through [Odata](http://www.odata.org) remote services, by configuring the service URL to the Schedule dataSource API.

{% highlight razor %}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2014, 5, 6)">
        <e-appointment-settings id="Id" query="ej.Query().from('Events').take(10)" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
            <e-datamanager url="//mvc.syncfusion.com/OdataServices/Northwnd.svc/"></e-datamanager>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

## OData V4

The OData v4 is an improved version of OData protocols. Scheduler supports retrieving and consuming appointment data from [OData v4](http://www.odata.org/documentation) services, just similar to the other remote services. 

{% highlight razor %}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2014, 5, 6)" enable-load-on-demand="true">
        <e-appointment-settings id="Id" subject='"ShipName"' start-time='"OrderDate"' end-time='"RequiredDate"' description='"ShipAddress"'>
            <e-datamanager url="http://services.odata.org/V4/Northwind/Northwind.svc/Orders/" adaptor="ODataV4Adaptor"></e-datamanager>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

## WebAPI Binding

The Schedule appointment data can also be bound through the Web API services. It is a programmatic interface to define the request and response messages system that is mostly exposed in **JSON** or **XML**.

{% highlight razor %}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2014, 5, 6)">
        <e-appointment-settings id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
            <e-datamanager url="http://mvc.syncfusion.com/OdataServices/api/ScheduleData/" cross-domain="true"></e-datamanager>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

The server-side code to retrieve the appointments are as follows.

{% highlight c# %}

    // To retrieve the appointments from database and bind it to Scheduler
    public IEnumerable<Event> GetData(String CurrentDate, String CurrentView, String CurrentAction)
    {
        return new NORTHWNDEntities().Events.ToList();
    }

{% endhighlight %}

