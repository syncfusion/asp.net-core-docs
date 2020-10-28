---
title: Schedule - Customization	
description: Customization of working hours, date, and appointment window
platform: aspnet-core
control: schedule
documentation: ug
keywords: customization, work hours, appointment window, display hours, Query cell info
---
# Customization

The Scheduler can be customized in various aspects like - 

* Setting different Start/end hour limits
* Highlighting the working hours 
* Setting different [Date format](/aspnet-core/schedule/globalization-and-localization#date-format)
* Specifying minimum and maximum date ranges 
* Customize the entire appointment window with the user required fields
* Setting different time Slot duration
* Complete Scheduler customization using `QueryCellInfo` event
* Setting different [FirstDayOfWeek](/aspnet-core/schedule/globalization-and-localization#first-day-of-week)

## Hour Customization

It includes customization of displaying Scheduler with specific Start/End hours and also defining the working hour time range which is differentiated as business hours.

### Schedule Display Hours

It denotes the start and end hour time limits to be displayed on the Scheduler. To set this time limit, two properties namely `StartHour` and `EndHour` can be used. 

* **StartHour** - The hour from which the Scheduler time display actually starts.
* **EndHour** - The hour on which the Scheduler time display should end.

The following code example renders the scheduler from 7.00 AM to 6.00 PM.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" start-hour="7" end-hour="18">    
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

### Working Hours

Working hours indicates the work hour limit within the Scheduler, which is highlighted visually with white colored work cells. To enable the highlighting of work hours on the Scheduler, set the **Highlight** option available within the `WorkHours` property to **true**. By default, it is set to true and includes the below specified options,

* **Highlight** –  enables/disables the highlighting of work hours.
* **Start** - sets the start time of the working/business hour in a day. 
* **End** - sets the end time limit of the working/business hour in a day.  


{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-work-hours highlight="true" start="8" end="16"></e-work-hours>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> By default, work hour **Start** is set to **9** and **End** is set to **18**. Also, the Scheduler cells automatically scrolls up or down based on the starting work hour, to make the user to view that particular time initially.

## Hide Weekend days

The Scheduler can be customized to display only the working days, thus hiding the weekend days from it. The working days render based on the values given in the `WorkWeek` property. The days that are not mentioned in the `WorkWeek` collection is considered to be the weekend days and it can be hidden from the Scheduler by setting `false` to the `ShowWeekend` property.

The following code example renders the Scheduler by hiding the weekend days.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" show-weekend="false">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## TimeScale

The `TimeScale` allows the user to set the required time slot duration for the work cells that displays on the Scheduler. It provides option to customize both the major and minor slots using template option. It includes the below properties such as,

* `Enable` - It accepts true or false value, denoting whether to show or hide the time slots. Its default value is `true`.
* `MajorSlot` – Specifies the major time slot duration.
* `MinorSlotCount` – Specifies the value, based on which the minor time slots are divided into appropriate count. 
* TimeScale Templates – 2 template options available for customizing time scales namely `MinorSlotTemplateId` and `MajorSlotTemplateId`.  

The MajorSlot and MinorSlot can be customized with the following code example.

{% highlight razor %}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-time-scale enable="true" major-slot="60" minor-slot-count="6"></e-time-scale>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## Date Customization

The date in the Scheduler can be customized by setting specific minimum and maximum date ranges and also defining various date formats to it.

### Current Date

The Current date indicates the date with which the Scheduler loads initially and based on which the appropriate date range displays in the week/workweek/month/agenda views. To set the current date to the Scheduler – use the following code example,

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> By default, the System current date will be taken as Scheduler’s current date.

### MinDate and MaxDate

Providing the `MinDate` and `MaxDate` property with some date values, allows the Scheduler to set the minimum and maximum date range. The Scheduler date that lies beyond these minimum and maximum date range will be in a disabled state, so that the date navigation is blocked beyond these specified date range. Also, the appointments that lies beyond these date ranges will not be displayed on the Scheduler.    

The following code example shows how to set the `MinDate` and `MaxDate` properties of the Scheduler.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 5)" min-date="new DateTime(2015, 11, 4)" max-date="new DateTime(2015, 11, 8)">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> The **max-date** value provided should always be greater than that of **min-date** value.

## Appointment Window Customization

It is possible to use the custom appointment window option to design it with the user-required extra fields apart from the other default available fields. To make use of the customized appointment window, it is necessary to use the `AppointmentWindowOpen` event within which the display of default appointment window is prevented.

The following code example lets you create the custom appointment window (using recurrence editor feature) with a single extra field for defining the appointment type.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 5)" appointment-window-open="onAppointmentWindowOpen">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

{% highlight html %}

<div id="customWindow" style="display: none">
    <div id="appWindow">
        <form id="custom">
            <table width="100%" cellpadding="5">
                <tbody>
                    <tr style="display: none">
                        <td>
                            Id:
                        </td>
                        <td colspan="2">
                            <input id="customId" type="text" name="Id" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            Subject:
                        </td>
                        <td colspan="2">
                            <input id="subject" type="text" value="" name="Subject" onfocus="temp()" style="width: 100%" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            Description:
                        </td>
                        <td colspan="2">
                            <textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"></textarea>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            StartTime:
                        </td>
                        <td>
                            <ej-date-time-picker id="StartTime" width="150px"></ej-date-time-picker>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            EndTime:
                        </td>
                        <td>
                            <ej-date-time-picker id="EndTime" width="150px"></ej-date-time-picker>
                        </td>
                    </tr>
                    <tr>
                        <td colspan="3">
                            <div class="customcheck">AllDay:</div>
                            <div class="customcheck">
                                <input id="allday" type="checkbox" name="AllDay" onchange="alldayCheck()" />
                            </div>
                            <div class="customcheck">Recurrence:</div>
                            <div>
                                <input id="recurrence" type="checkbox" name="Recurrence" />
                            </div>
                        </td>
                    </tr>
                    <tr id="summaryTr" style="display:none;">
                        <td colspan="3">
                            <div class="recSummary">Summary:</div>
                            <div>
                                <label id="recSummary" name="Summary"></label>
                            </div>
                        </td>
                    </tr>
                    <tr id="editor" style="display:none;">
                        <td colspan="3">
                            <div><a id="recedit" onclick="recurrenceRule()">Edit</a></div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </form>
        <div>
            <button type="submit" onclick="cancel()" id="buttonCancel" style="float:right;margin-right:20px;margin-bottom:10px;">Cancel</button>
            <button type="submit" onclick="save()" id="buttonSubmit" style="float:right;margin-right:20px;margin-bottom:10px;">Submit</button>
        </div>
    </div>
    <div id="recWindow" style="display: none">
        <div style="margin: 0 15%;">
            @{
                List<string> Frequencies = new List<string> { "daily", "weekly", "monthly", "yearly", "everyweekday" };
            }
            <ej-recurrence-editor id="recurrenceEditor" selected-recurrence-type="0" frequencies="Frequencies"></ej-recurrence-editor>
        </div>
        <div>
            <button type="submit" id="recCancel">Cancel</button>
            <button type="submit" id="recSubmit">Submit</button>
        </div>
    </div>
</div>

{% endhighlight %}

The styles to be applied for the controls within the custom appointment window are as follows.

{% highlight html %}

<style>
    .customcheck {
    float: left;
    margin-right: 10px;
    }
	
    .error {
    background-color: #FF8A8A;
    }
	
    #custom table td {
    padding:5px;
    }
</style>

{% endhighlight %}

Now, define the Schedule control with custom appointment window within script as shown below.

{% highlight html %}

<script>
 $(function () {
        // defining sub-controls used within custom appointment window
        $("#buttonCancel").ejButton({ width: '85px' });
        $("#buttonSubmit").ejButton({ width: '85px' });
        $("#recurrence").ejCheckBox({ change: "recurCheck" });
        $("#recCancel,#recSubmit").ejButton({ click: "onRecurrenceClick" });
        // defining dialog control to be used as custom appointment window
        $("#customWindow").ejDialog({
            width: 600,
            height: "auto",
            position: { X: 200, Y: 100 },
            showOnInit: false,
            enableModal: true,
            title: "Appointment Window",
            enableResize: false,
            allowKeyboardNavigation: false,
            close: "clearFields"
        });
    });
</script>

{% endhighlight %}

The following function needs to be defined within script section, which gets called before the default appointment window opens.

{% highlight js %}

<script>
function onAppointmentWindowOpen(args) {
        args.cancel = true; // prevents the display of default appointment window
        var schObj = $("#Schedule1").data("ejSchedule");
        // When double clicked on the Scheduler cells, fills the StartTime and EndTime fields appropriately
        $("#StartTime").ejDateTimePicker({ value: args.startTime });
        $("#EndTime").ejDateTimePicker({ value: args.endTime });
        $("#recWindow").css("display", "none");
        $("#appWindow").css("display", "");
        if (!ej.isNullOrUndefined(args.target)) {
            // When double clicked on the Scheduler cells, if the target is allDay or month cells – only then enable check mark on the allday checkbox
            if ($(args.target.currentTarget).hasClass("e-alldaycells") || (args.startTime.getHours() == 0 && args.endTime.getHours() == 23))
                $("#allDay").prop("checked", true);
            else
                args.model.currentView == "month" ? $("#allDay").prop("checked", true) : $("#allDay").prop("checked", false);
            // If the target is allDay or month cells – disable the StartTime and EndTime fields
            $("#StartTime,#EndTime").ejDateTimePicker({
                enabled: ($(args.target.currentTarget).hasClass("e-alldaycells") || (args.startTime.getHours() == 0 && args.endTime.getHours() == 23) || $(args.target.currentTarget).hasClass("e-monthcells") || args.model.currentView == "month") ? false : true
            });
        }
        // If double clicked on the appointments, fill the custom appointment window fields with appropriate values.
        if (!ej.isNullOrUndefined(args.appointment)) {
            $("#customId").val(args.appointment.Id);
            $("#subject").val(args.appointment.Subject);
            $("#StartTime").ejDateTimePicker({ value: new Date(args.appointment.StartTime) });
            $("#EndTime").ejDateTimePicker({ value: new Date(args.appointment.EndTime) });
            $("#recurrence").ejCheckBox({ checked: args.appointment.Recurrence });
            if (args.appointment.Recurrence) {
                $("#editor").css("display", "");
                $("#recSummary").html(args.appointment.RecurrenceRule);
                $("#summaryTr").css("display", "");
                recObj._recRule = args.appointment.RecurrenceRule; // app recurrence rule is stored in Recurrence editor object
                recObj.recurrenceRuleSplit(args.appointment.RecurrenceRule, args.appointment.recurrenceExDate); //splitting the recurrence rule
                recObj.showRecurrenceSummary(args.appointment.Id); // updating the recurrence rule in Recurrence editor
            }
        }
        $("#customWindow").ejDialog("open");
    }
</script>

{% endhighlight %}

On clicking the **Submit** button within the Custom Appointment window, the following function gets executed – which will validate the appointment fields and then save it appropriately.

{% highlight js %}

<script>
function save() {
    // checks if the subject value is not left blank before saving it.
        if ($.trim($("#subject").val()) == "") {
            $("#subject").addClass("error");
            return false;
        }
        var obj = {}, temp = {}, rType;
        var formElement = $("#customWindow").find("#custom").get(0);
        // looping through the custom form elements to get each value and form a JSON object
        for (var index = 0; index < formElement.length; index++) {
            var columnName = formElement[index].name, $element = $(formElement[index]);
            if (columnName != undefined) {
                if (columnName == "")
                    columnName = formElement[index].id.replace(this._id, "");
                if (columnName != "" && obj[columnName] == null) {
                    var value = formElement[index].value;
                    if (columnName == "Id" && value != "")
                        value = parseInt(value);
                    if ($element.hasClass("e-datetimepicker"))
                        value = new Date(value);
                    if (formElement[index].type == "checkbox")
                        value = formElement[index].checked;
                    obj[columnName] = value;
                }
            }
        }
        obj["RecurrenceRule"] = (obj.Recurrence) ? recurRule : null;
        $("#customWindow").ejDialog("close");
        var object = $("#Schedule1").data("ejSchedule");
        object.saveAppointment(obj);
        clearFields();
    }

// This function executes when the submit/cancel button in the recurrence editor window is pressed.
    function onRecurrenceClick(args) {
        if ($(args.e.currentTarget).attr("id") == "recSubmit") {
            recObj = $("#recurrenceEditor").ejRecurrenceEditor('instance');
            recObj.closeRecurPublic();
            recurRule = recObj._recRule;
            $("#recSummary").html(recurRule);
        }
        else
            if (($(args.e.currentTarget).attr("id") == "recCancel")) {
                if ($("#recSummary").html() == "") {
                    $("#editor").css("display", "none");
                    $("#recurrence").ejCheckBox({ checked: false });
                }
                else
                    $("#recurrence").ejCheckBox({ checked: true });
            }
        $("#recWindow").css("display", "none");
        $("#appWindow").css("display", "");
        if ($("#recSummary").html() != "")
            $("#summaryTr").css("display", "");
    }

// This function executes when the Edit anchor tag in the edit appointment window is clicked.
    function recurrenceRule() {
        $("#recWindow").css("display", "");
        $("#appWindow").css("display", "none");
    }

// Clears all the field values of the custom window after saving appointments
    function clearFields() {
        $("#customId").val("");
        recObj.clearRecurrenceFields();
        $("#subject").val("");
        $("#recSummary").html("");
        $("#summaryTr").css("display", "none");
        $("#recurrence").ejCheckBox({ checked: false });
        $("#editor").css("display", "none");
        $("#StartTime,#EndTime").ejDateTimePicker({ enabled: true });
    }

// This function executes when the recurrence checkbox is checked in the custom appointment window
    function recurCheck(args) {
        if (args.isInteraction) {
            if ($("#recurrence").get(0).checked == true) {  // Displays the recurrence field, when recurrence checkbox is checked.
                $("#recWindow").css("display", "");
                $("#appWindow").css("display", "none");
                $("#editor").css("display", "");
            }
            else {
                $("#recWindow").css("display", "none");
                $("#editor").css("display", "none");
                $("#recSummary").html("");
                $("#summaryTr").css("display", "none");
            }
        }
    }

// This function executes when the All-day checkbox is checked in the custom appointment window
    function alldayCheck() {
        // Disables and sets the specific hours to the StartTime and EndTime fields, when the all-day checkbox is checked
        if ($("#allday").prop("checked")) {
            var a = $("#StartTime").data("ejDateTimePicker").model.value;
            a.setHours(0, 0, 0);
            var b = $("#EndTime").data("ejDateTimePicker").model.value;
            b.setHours(23, 59, 0);
            $("#StartTime").ejDateTimePicker({
                value: new Date(a),
                enabled: false
            });
            $("#EndTime").ejDateTimePicker({
                value: new Date(b),
                enabled: false
            });
        } else {
            $("#StartTime").ejDateTimePicker({
                enabled: true
            });
            $("#EndTime").ejDateTimePicker({
                enabled: true
            });
        }
    }

// This function executes when the subject text field is currently being focused
    function temp() {
        $("#subject").removeClass("error");
    }

// This function executes when the cancel button in the custom appointment window is pressed.
    function cancel() {
        recObj = $("#recurrenceEditor").ejRecurrenceEditor('instance');
        clearFields();
        $("#customWindow").ejDialog("close");
    }
</script>

{% endhighlight %}

## Scheduler Customization using QueryCellInfo

It is possible to format and customize almost every child elements of scheduler such as work cells, header cells, time cells and so on using `QueryCellInfo` event. 

The following code snippet shows how to customize the appointment and work cells based on the query cell info event.
     
{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" query-cell-info="checkFormat">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

While loading the scheduler using above code, the below function gets triggered by the `QueryCellInfo` event which customizes the corresponding DOM element.


{% highlight html %}

    <script type="text/javascript">
     function checkFormat(args) {
	    switch (args.requestType) {
		case "workcells":
			args.element.css("background-color", "#ffe9cc");
			break;
		case "monthcells":
			args.element.css("background-color", "#faa41a");
			args.element.css("border-color", "#faa41a");
			break;
		}
    }
    </script>

{% endhighlight %}

The Scheduler elements are listed below which can be formatted through this event. The names are listed in the format with which it can be accessed or used within the requestType argument of the event.

<table class="params">
    <thead>
        <tr>
            <th>Request Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">appointment</td>
            <td class="description">Depicts the appointment element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">agendacells</td>
            <td class="description">Depicts the Agenda Cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">alldaycells</td>
            <td class="description">Depicts the AllDay cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">headercells</td>
            <td class="description">Depicts the header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">resourceheadercells</td>
            <td class="description">Depicts the resource header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">leftheadercells</td>
            <td class="description">Depicts the left empty space on header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">leftindentcells</td>
            <td class="description">Depicts the left empty space on date cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">timecells</td>
            <td class="description">Depicts the left side time panel cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">headerdate</td>
            <td class="description">Depicts the header date cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">emptytd</td>
            <td class="description">Depicts the empty space above the vertical scroller within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">resourcegroupheader</td>
            <td class="description">Depicts the header group cell in horizontal orientation in the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">monthcells</td>
            <td class="description">Depicts the month cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">workcells</td>
            <td class="description">Depicts the work cell element within the Scheduler.</td>
        </tr>
    </tbody>
</table>