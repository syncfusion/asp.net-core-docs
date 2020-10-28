---
title: Globalization and Localization
description: Globalizing and localizing Scheduler
platform: aspnet-core
control: schedule
documentation: ug
keywords: globalize, localize, localization, globalization 
---
# Globalization and Localization

## Globalization

The Scheduler control is built with default **globalization** support as it format the dates according to the user’s locale automatically and processes it internally without any need for manual conversions. This kind of default handling of Scheduler dates is achieved through the built-in **ej.globalize** library which globalize the date, day and month names accordingly.

## Localization

Scheduler also comes with default localization support which allows it to customize the display of text within the Scheduler in a user-specific culture and locale. The Schedule control can be localized in specific culture using the common API `locale` along with the collection of localized words defined for that culture using the ej.Schedule.Locale [**culture-code**].

N> By default, the Schedule control is localized in **en-US** culture.

To localize Scheduler into any particular culture, it is necessary to refer the culture-specific script files in your application after the reference of **ej.web.all.min.js** file, which are available under the following location.                   

_<**Installed location**>\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n_

The following code example shows how to localize the Schedule control in **fr-FR** culture.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" locale="fr-FR">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

{% highlight html %}
<script src="@Url.Content("~/Scripts/i18n/ej.culture.fr-FR.min.js")"></script>
<script>
    ej.Schedule.Locale["fr-FR"] = {
    ReminderWindowTitle: "fenêtre Rappel",
    CreateAppointmentTitle: "Créer un rendez",
    RecurrenceEditTitle: "Modifier Répéter rendez-vous",
    RecurrenceEditMessage: "Comment voulez-vous changer le rendez-vous dans la série?",
    RecurrenceEditOnly: "Seulement cette nomination",
    RecurrenceEditSeries: "La série entière",
    PreviousAppointment: "Nomination précédente",
    NextAppointment: "Prochain rendez-vous",
    AppointmentSubject: "Assujettir",
    StartTime: "Heure de départ",
    EndTime: "Heure de fin",
    AllDay: "Toute la journée",
    StartTimeZone: "Démarrez TimeZone",
    EndTimeZone: "End Time Zone",
    Today: "Aujourd'hui",
    Recurrence: "Répéter",
    Done: "Terminé",
    Cancel: "Annuler",
    Ok: "D'accord",
    Repeat: "Répéter",
    RepeatBy: "Répéter par",
    RepeatEvery: "Répéter chaque",
    RepeatOn: "Répéter l'opération sur",
    StartsOn: "Démarre sur",
    Ends: "Prend fin",
    Summary: "Résumé",
    Daily: "Tous les jours",
    Weekly: "Hebdomadaire",
    Monthly: "Mensuel",
    Yearly: "Annuel",
    Every: "Chaque",
    EveryWeekDay: "Tous les jours de la semaine",
    Never: "Jamais",
    After: "Après",
    Occurrence: "Occurrences",
    On: "Sur",
    Edit: "modifier",
    RecurrenceDay: "Journées",
    RecurrenceWeek: "Semaines",
    RecurrenceMonth: "Mois",
    RecurrenceYear: "Années",
    The: "le",
    OfEvery: "de toute",
    First: "Premier",
    Second: "Seconde",
    Third: "Troisième",
    Fourth: "Quatrième",
    Last: "Dernier",
    WeekDay: "Jour de la semaine",
    WeekEndDay: "Jour de weekend",
    Subject: "Assujettir",
    Categorize: "Catégories",
    DueIn: "Dû en",
    DismissAll: "Rejeter la totalité",
    Dismiss: "Rejeter",
    OpenItem: "Élément ouvert",
    Snooze: "Roupillon",
    Day: "journées",
    Week: "Semaine",
    WorkWeek: "Semaine de travail",
    Month: "Mois",
    AddEvent: "Ajouter un évènement",
    CustomView: "Vue personnalisée",
    Agenda: "Ordre du jour",
    Detailed: "Modifier Rendez-vous",
    EventBeginsin: "Nomination commence dans",
    Editevent: "Modifier Rendez-vous",
    Editseries: "Modifier la série",
    Times: "fois",
    Until: "jusqu'à",
    Eventwas: "Rendez-vous était",
    Hours: "hrs",
    Minutes: "mins",
    Overdue: "Nomination Overdue",
    Days: "journées)",
    Event: "un événement",
    Select: "sélectionner",
    Previous: "précédent",
    Next: "Prochain",
    Close: "Fermer",
    Delete: "Effacer",
    Date: "date",
    Showin: "Montre",
    Gotodate: "Aller à la date",
    Resources: "RESSOURCES",
    RecurrenceDeleteTitle: "Supprimer Répéter rendez-vous",
    Location: "Emplacement",
    Priority: "Priorité",
    RecurrenceAlert: "Alerte",
    NoTitle: "Pas de titre",
    OverFlowAppCount: "plus de nominations",
    AppointmentIndicator: "Cliquez pour plus de rendez-vous",
    WrongPattern: "Le modèle de récurrence est pas valide",
    CreateError: "La durée de la nomination doit être plus courte que la fréquence elle se produit. Raccourcir la durée, ou modifier le modèle de récurrence dans la boîte de dialogue Récurrence de rendez.",
    DragResizeError: "Vous ne pouvez pas reporter une occurrence du rendez-vous périodique si elle saute sur une occurrence ultérieure du même rendez-vous.",
    StartEndError: "L'heure de fin doit être supérieure à l'heure de début",
    MouseOverDeleteTitle: "Supprimer Nomination",
    DeleteConfirmation: "Êtes-vous sûr de vouloir supprimer ce rendez-vous?",
    Time: "Temps",
    EmptyResultText: "Pas de suggestions",
    BlockIntervalAlertTitle: "Alerte",
    BlockIntervalError: "L'intervalle de temps choisi a été bloqué et est indisponible pour la sélection."
};
</script>

{% endhighlight %}

N> Refer the **ej.culture.fr-FR.min.js** file in your HTML application and also define the **Locale** property for the Schedule control with the appropriate **culture-code** [**fr-FR**].

For further information on – how to refer the required culture scripts into your application, refer [here](/aspnetmvc/localization).

### Localizing Specific Words

To customize or localize only some specific words in the default `ej.Schedule.Locale["en-US"]` collection, the words to be localized/customized can be defined in a separate variable and then extended to the original collection as depicted in the following code example.

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

{% highlight html %}

<script>
var customizationMessage = {
    // customize the appointment window title
    CreateAppointmentTitle: "Create Event",
    // customize the view options text in the Schedule header
    Day: "1 Day",
    Week: "7 Days",
    WorkWeek: "5 Days",
    Month: "Month"
};

// Extend only the required changes to the original locale collection
$.extend(ej.Schedule.Locale["en-US"], customizationMessage);

</script>

{% endhighlight %}

## Time Zone

The Scheduler makes use of the System time zone by default. If it needs to follow some other user-specific time zone, then the API `TimeZone` can be used. Also, the Scheduler can be set to observe the Daylight Saving Time (DST) with its **isDST** property which is set to **false** by default. 

When `IsDST` property is set to **true**, the Scheduler internally processes the time difference values (for the Start and end time of the appointments) related to the Scheduler time zone that observes daylight savings time. 

The following code example shows the way to set the specific time zone value with the daylight savings time observed in the Scheduler.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)"  time-zone="UTC +05:30" is-dst="true">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

### Different TimeZone for Scheduler Appointments

Apart from the default action of applying specific timezone to the entire Scheduler, it is also possible to set different time zone values for each appointments through the properties **startTimeZone** and **endTimeZone** which can be defined as separate fields within the appointment dataSource. When these properties are not explicitly defined for appointments, the appointments Start and End time will be processed based on the Scheduler time zone.

N> The **IsDST** property closely relies on the appointment fields like `StartTimeZone` and `EndTimeZone`, for appropriate time difference calculations. If these two fields are not defined for appointments, then **IsDST** depends on the System **TimeZone** value.

The following code snippet shows how to define isDST and the time zones for specific appointments.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "", StartTimeZone = "UTC +02:00", EndTimeZone = "UTC +02:00" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" is-dst="true">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"' start-time-zone='"StartTimeZone"' end-time-zone='"EndTimeZone"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

### Customizing TimeZone Collection

It is also possible to define or customize the default time zone collection of the Scheduler, by using the `TimeZoneCollection` API as follows.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });

    <!-- Datasource for TimezoneCollection -->
    List<TimezoneCollection> TimeZone = new List<TimezoneCollection>();
    TimeZone.Add(new TimezoneCollection { Text = "UTC -04:00", Id = "10", Value = "UTC -04:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC -03:30", Id = "11", Value = "UTC -03:30" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC -03:00", Id = "12", Value = "UTC -03:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC -02:00", Id = "13", Value = "UTC -02:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC -01:00", Id = "14", Value = "UTC -01:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +00:00", Id = "15", Value = "UTC +00:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +01:00", Id = "16", Value = "UTC +01:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +02:00", Id = "17", Value = "UTC +02:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +03:00", Id = "18", Value = "UTC +03:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +03:30", Id = "19", Value = "UTC +03:30" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +04:00", Id = "20", Value = "UTC +04:00" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +04:30", Id = "21", Value = "UTC +04:30" });
    TimeZone.Add(new TimezoneCollection { Text = "UTC +05:00", Id = "22", Value = "UTC +05:00" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)">
    <e-time-zone-collection datasource="TimeZone" text="Text" id="Id" value="Value">
    </e-time-zone-collection>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> The values defined within the **TimeZoneCollection** dataSource are usually the only options displayed within the start and end time zone dropdown fields of the appointment window.

## Time Mode

The time mode of the Scheduler can be either **12** or **24 hours** format which is based on the `locale` set to the Scheduler. Since the default locale value of the Scheduler is **en-US**, therefore the time mode will be set to **12 hours** format (by default) automatically based on the culture. 

The user can also set specific time mode for the Scheduler using `time-mode` property which accepts either **String** or **enum** value. It accepts the following **enum** values,

* TimeMode.Hour12
* TimeMode.Hour24

The following code snippet shows the way to set specific **24 hour format** time mode for the Scheduler.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" time-mode="TimeMode.Hour24">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> If the **TimeMode** property is not set with specific value, then the value will be taken based on the locale assigned for the Scheduler.

## Date Format

Scheduler can be used with all valid date formats. The default date format used in Scheduler is "MM/dd/yyyy". 

If the `date-format` property is not specified particularly, then it will be taken based on the locale that is assigned to the Scheduler. The default locale applied on the Scheduler is “en-US”, which makes it to follow the "MM/dd/yyyy" pattern by default.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" date-format="yyyy/MM/dd">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## First Day of Week

The `first-day-of-week` property allows to set any of the week days as start of the week/workweek/month view in Scheduler. It accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) value. The default value of this `first-day-of-week` property depends on the current culture (language) assigned to the Scheduler.

To set different first day of week in Scheduler,

{% highlight razor %}

@using Syncfusion.JavaScript.Models;
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" first-day-of-week="DayOfWeek.Monday">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> The sub-control datepicker which is used within Scheduler for start/end time fields in appointment window and for date navigation purposes will also follow the same first day of week. 