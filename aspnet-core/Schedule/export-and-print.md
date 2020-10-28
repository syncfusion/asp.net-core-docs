---
title: Export, import and print the Schedule with its appointments	
description: Export-Import/Print the complete Scheduler or specific appointment alone
platform: aspnet-core
control: schedule
documentation: ug
keywords: export, import and print 
---
# Export and Print


## Print

Two types of Print options are available – either to print the entire Scheduler layout including all the appointments in it or else to print any particular appointment alone. The public method `Print` is used to print the entire Scheduler.

### Print the Scheduler

The following code example shows the way to print the entire Scheduler, by keeping an extra button in a page – on which clicking the button will print the entire Scheduler.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    //Datasource for appointments
    List<ScheduleData> Appoint = new List<ScheduleData>();
    Appoint.Add(new ScheduleData { Id = "1", Subject = "Meeting", StartTime = new DateTime(2016, 11, 10, 10, 00, 00), EndTime = new DateTime(2016, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

   <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2016, 11, 7)">
        <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
        </e-appointment-settings>
   </ej-schedule>
   
   <ej-button id="print" text="Print" click="onClick" />


{% endhighlight %}

{% highlight js %}

<script type="text/javascript">
    function onClick(args) {
        var obj = $("#Schedule1").data("ejSchedule");
        obj.print();
    }
</script>    

{% endhighlight %}

### Printing Specific Appointments

To print a particular appointment, either the default context menu **print** option can be used or else the `print` method can be used by passing the id of the appointment to be printed as its argument. 

N> To handle this functionality, the context menu settings needs to be enabled with print option added to the appointment items.

The following code example depicts the way to print a particular appointment.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{ 
    //Datasource for appointments
    List<ScheduleData> Appoint = new List<ScheduleData>();
    Appoint.Add(new ScheduleData { Id = "1", Subject = "Meeting", StartTime = new DateTime(2016, 11, 10, 10, 00, 00), EndTime = new DateTime(2016, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2016, 11, 7)">
        <e-context-menu-settings enable="true">
            <e-menu-items>
                <e-appointment-collection>
                    <e-appointment id="open" text="Open Appointment" />
                    <e-appointment id="delete" text="Delete Appointment" />
                    <e-appointment id="print" text="Print Appointment" />
                </e-appointment-collection>
            </e-menu-items>
        </e-context-menu-settings>
        <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

#### Using print() method

The client-side public method `print` needs to be used here by passing the appointment object as its argument, that needs to be printed.

For example, here the below code example depicts the way to print the particular appointment programmatically by calling the **print** function within the `AppointmentClick` event, which triggers whenever the user clicks on an appointment.

{% highlight razor %}

@using Syncfusion.JavaScript.Models;
@{ 
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2016, 11, 7)" appointment-click="onAppointmentClick">
        <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

{% highlight js %}

<script type="text/javascript">
    function onAppointmentClick(args) {
        var schObj = $("#Schedule1").data("ejSchedule");
        schObj.print(args.appointment);
    }
</script>

{% endhighlight %}
