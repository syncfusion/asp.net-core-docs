---
title: How-to
description: Custom Configuration with Schedule control
platform: aspnet-core
control: schedule
documentation: ug
keywords: globalize, localize, localization, globalization 
---
# How To

## Validate the Custom Appointment Window Fields

The client-side validation of the fields present within the custom appointment window can be handled before submitting it, by adding appropriate validation classes to each field.

Refer the steps [here](/aspnetmvc/schedule/customization#appointment-window-customization) and create a sample for Custom Appointment window, before proceeding with the following validations.

In the custom appointment window sample, create an additional CSS class **validation** as mentioned below to add it to the appropriate fields, if the validation of such fields fails.

{% highlight css %}

<style> 
    .validation {
        border-color: red;
    }
</style>

{% endhighlight %}

The sample contains the fields like Subject, Description, StartTime and EndTime which needs to be validated at client-side. To do so, add the required validation code within the script section as follows.

{% highlight html %}

<script type="text/javascript">

// To Validate the Subject field.
$("#subject").focusout(function() {
    if ($.trim($("#subject").val()) == "") {
        $("#subject").addClass("validation");
        return false;
    }
})

// To Validate the Description field.
$("#customdescription").focusout(function() {
    if ($.trim($("#customdescription").val()) == "") {
        $("#customdescription").addClass("validation");
        return false;
    }
})

// To Validate the Time duration of the appointments
$("#EndTime").focusout(function() {
    if (new Date($("#EndTime").val()).getDate() >= new Date($("#StartTime").val()).getDate()) {
        if (new Date($("#StartTime").val()).getTime() >= new Date($("#EndTime").val()).getTime())
            alert("EndTime value is lesser than the StartTime value");
    }
})

</script>

{% endhighlight %}

Now, after adding the above validations – whenever the fields within the custom appointment window are skipped without filling any information, it will be notified to the users appropriately.

## Highlight Different Work Hours for Each Resources

By default, the work hours of the Scheduler is highlighted based on the start and end values provided within the `WorkHours` property. It remains same for all the resources, when the Scheduler is rendered with multiple resources. To customize this behavior so as to highlight different working hour range for each of the resources, the following workaround can be utilized by making use of the Scheduler events `Create` and `ActionComplete`.

Initially, set the `Highlight` as false for the `WorkHours`, so as to disable the highlighting of default work hour range.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", OwnerId = "1" });

    <!-- Datasource for Grouping -->
    List<String> Group = new List<String>();
    Group.Add("Owners");

    <!-- Datasource for Owners -->
    List<ResourceFields> Owner = new List<ResourceFields>();
    Owner.Add(new ResourceFields { Id = "1", Text = "Nancy", Color = "#f8a398" });
    Owner.Add(new ResourceFields { Id = "3", Text = "Steven", Color = "#56ca85" });
    Owner.Add(new ResourceFields { Id = "5", Text = "Michael", Color = "#51a0ed" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Workweek" show-current-time-indicator="false" create="onCreate" action-complete="onCreate">
    <e-work-hours highlight="false"></e-work-hours>
    <e-group resources="Group"></e-group>
    <e-resources>
        <e-resource allow-multiple="true" field="OwnerId" title="Owner" name="Owners">
            <e-resource-settings datasource="Owner" text="Text" id="Id" color="Color"></e-resource-settings>
        </e-resource>
    </e-resources>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' resource-fields='"OwnerId"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

{% highlight js %}
<script>
// This function executes during the initial control creation and also on completion of each action like date/view navigation.
function onCreate(args) {
    if (args.requestType == "viewNavigate" || args.requestType == "dateNavigate" || args.type == "create") {
        // declare different start and end work hour values for each resources
        var resourceOneStart = 9,
            resourceOneEnd = 18;

        var resourceTwoStart = 13,
            resourceTwoEnd = 18;

        var resourceThreeStart = 10,
            resourceThreeEnd = 18;

        this.option("workHours.highlight", (this.currentView() != "month") ? false : true);
        var trElements = this.$WorkCellDiv.find("tr");    // Get the Scheduler workcell rows

        for (var i = 0; i < trElements.length; i++) {
            var tdElements = $(trElements[i]).find("td");  // Get the Scheduler workcell columns
            for (var j = 0; j < tdElements.length; j++) {
                switch (this.currentView()) {
                    case "day":
                        switch (j) {
                            case 0: // column index 0 represents first resource in day view
                                $(tdElements[j]).addClass(((i > (resourceOneStart * 2) - 1) && (i <= (resourceOneEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                            case 1: // column index 1 represents second resource in day view
                                $(tdElements[j]).addClass(((i > (resourceTwoStart * 2) - 1) && (i <= (resourceTwoEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                            case 2: // column index 2 represents third resource in day view
                                $(tdElements[j]).addClass(((i > (resourceThreeStart * 2) - 1) && (i <= (resourceThreeEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                        }
                        break;
                    case "week":
                        switch (j) {
                            case 0:
                            case 1:
                            case 2:
                            case 3:
                            case 4:
                            case 5:
                            case 6: // column indexes 0 to 6 belongs to first resource in week view (7 days)
                                $(tdElements[j]).addClass(((i > (resourceOneStart * 2) - 1) && (i <= (resourceOneEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                            case 7:
                            case 8:
                            case 9:
                            case 10:
                            case 11:
                            case 12:
                            case 13: // column indexes 7 to 13 belongs to second resource in week view (7 days)
                                $(tdElements[j]).addClass(((i > (resourceTwoStart * 2) - 1) && (i <= (resourceTwoEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                            case 14:
                            case 15:
                            case 16:
                            case 17:
                            case 18:
                            case 19:
                            case 20: // column indexes 14 to 20 belongs to third resource in week view (7 days)
                                $(tdElements[j]).addClass(((i > (resourceThreeStart * 2) - 1) && (i <= (resourceThreeEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                        }
                        break;
                    case "workweek":
                        switch (j) {
                            case 0:
                            case 1:
                            case 2:
                            case 3:
                            case 4: // column indexes 0 to 4 belongs to first resource in workweek view (5 days)
                                $(tdElements[j]).addClass(((i > (resourceOneStart * 2) - 1) && (i <= (resourceOneEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                            case 5:
                            case 6:
                            case 7:
                            case 8:
                            case 9:
                                // column indexes 5 to 9 belongs to second resource in workweek view (5 days)
                                $(tdElements[j]).addClass(((i > (resourceTwoStart * 2) - 1) && (i <= (resourceTwoEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                            case 10:
                            case 11:
                            case 12:
                            case 13:
                            case 14:
                                // column indexes 10 to 14 belongs to third resource in workweek view (5 days)
                                $(tdElements[j]).addClass(((i > (resourceThreeStart * 2) - 1) && (i <= (resourceThreeEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                break;
                        }
                        break;
                }
            }
        }
    }
}
</script>

{% endhighlight %}

## Display Scheduler with Appointments Filtered by Subject

It is possible to display the Scheduler with appointments, which is filtered based on the Subject. For example, if we keep a text box and start typing a character – the list of appointments whose subject matches the typed character alone will be shown on the Scheduler. The following code example depicts the way to achieve this.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
    Appoint.Add(new ScheduleFields { Id = "2", Subject = "Bering Sea Gold", StartTime = new DateTime(2015, 11, 10, 01, 00, 00), EndTime = new DateTime(2015, 11, 10, 02, 30, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
    Appoint.Add(new ScheduleFields { Id = "3", Subject = "Deadest Catch", StartTime = new DateTime(2015, 11, 10, 11, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 30, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
    Appoint.Add(new ScheduleFields { Id = "4", Subject = "What Happened Next?", StartTime = new DateTime(2015, 11, 10, 15, 00, 00), EndTime = new DateTime(2015, 11, 10, 17, 30, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
    Appoint.Add(new ScheduleFields { Id = "5", Subject = "Daily Planet", StartTime = new DateTime(2015, 11, 10, 20, 00, 00), EndTime = new DateTime(2015, 11, 10, 22, 30, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" show-current-time-indicator="false">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

{% highlight html %}

<!-- Textbox for entering search character -->
<input id='txtSearch' type='text' onkeyup='searchKeyUp()' />

<script>
    function searchKeyUp() {
        var searchString = $("#txtSearch").val();
        var schObj = $("#Schedule1").data("ejSchedule");
        var result = schObj.searchAppointments(searchString);
        schObj.option("appointmentSettings", { dataSource: [] });
        if (!ej.isNullOrUndefined(result) && result.length != 0 && searchString != "")
            schObj.option("appointmentSettings", { dataSource: result });
        else
            schObj.option("appointmentSettings", { dataSource: schObj._currentAppointmentData });
    }
</script>

{% endhighlight %}

## Customize the Default Appointment Window

Apart from the custom appointment window, it is possible to customize the default appointment window by adding/removing the required number of fields into it. This can be achieved through the `Create` event of the scheduler.

The following code example depicts the way to achieve the customization of default appointment window.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" create="onCreate" appointment-window-open="onAppointmentOpen">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

{% highlight js %}

    // This function executes when the checkboxes are checked/unchecked
    function onCreate(args) {
        var customDesign = "<tr class='customfields'><td class='e-textlabel'>Event Type</td><td><input class='apptype' type='text'/></td><td class='e-textlabel'>Event Status </td><td><input class='status' type='text'/></td></tr>";
        $("." + this._id + "parrow").after(customDesign);
    }

    // This function executes before the appointment window gets opened.
    function onAppointmentOpen(args) {
        if (!ej.isNullOrUndefined(args.appointment)) {
            // if double clicked on the appointments, retrieve the custom field values from the appointment object and fills it in the appropriate fields.               this._appointmentAddWindow.find(".apptype").val(args.appointment.AppointmentType);
            this._appointmentAddWindow.find(".status").val(args.appointment.Status);
        } else {
            // if double clicked on the cells, clears the field values.               
            this._appointmentAddWindow.find(".apptype").val("");
            this._appointmentAddWindow.find(".status").val("");
        }
    }

{% endhighlight %}

