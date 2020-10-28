---
layout: post
title: Localization
description: localization
platform: aspnet-core
control: Gantt
documentation: ug
---
# Localization

Localization is the process of customizing the User Interface (UI) based on a culture, specific to a particular country or region, in order to display regional data. The culture is represented by a unique string like `en-US` for US English and `fr-FR` for French.

Localization is the key feature that provides solutions to global customers with the help of localized control. 

The following UIs are provided to localize based on culture. The default English Localization UIs are listed as follows:

<table>
<tr>
<td>
Localized string value for en-US culture</td><td></td></tr>
<tr>
<td>
Empty Record</td><td>
emptyRecord: "No records to display"</td></tr>
<tr>
<td>
Column Header Texts:<br/>
taskId<br/>
taskName<br/>
startDate<br/>
endDate<br/>
resourceInfo<br/>
duration<br/>
status<br/>
predecessor<br/>
baselineStartDate<br/>
baselineEndDate<br/>
WBS<br/>
WBSPredecessor</td><td>
{% highlight javascript %}
columnHeaderTexts: {   taskId: "ID",
      taskName: "Task Name",
      startDate: "Start Date",
      endDate: "End Date",
      resourceInfo: "Resources",
      duration: "Duration",
      status: "Progress",
      predecessor: "Predecessors",
      baselineStartDate: "Baseline Start Date",
      baselineEndDate: "Baseline End Date",
      WBS: "WBS",
      WBSPredecessor: "WBS Predecessor"  
},    
{% endhighlight %}    
 </td></tr>
<tr>
<td>
Edit Dialog Texts:<br/>
addFormTitle<br/>
editFormTitle<br/>
saveButton<br/>
deleteButton<br/>
cancelButton<br/>
addPredecessor<br/>
removePredecessor</td><td>
{% highlight javascript %}
editDialogTexts: {   addFormTitle: "New Task",
      editFormTitle: "Edit Task",
      saveButton: "Save",
      deleteButton: "Delete",
      cancelButton: "Cancel",
      addPredecessor: "Add New",
      removePredecessor: "Remove"  
},
{% endhighlight %}
</td></tr>
<tr>
<td>
alertTexts:<br/>
indentAlert<br/>
outdentAlert<br/>
predecessorEditingValidationAlert<br/>
predecessorAddingValidationAlert<br/>
idValidationAlert<br/>
dateValidationAlert</td><td>
{% highlight javascript %}
alertTexts: {   indentAlert: "There is no gantt record is selected to perform the Indent",
      outdentAlert: "There is no gantt record is selected to perform the Outdent",
      predecessorEditingValidationAlert: "Cyclic Dependency Occured, Please Check The Predecessor",
      predecessorAddingValidationAlert: "Fill all the columns in predecessor table",
      idValidationAlert: "Duplicate ID",
      dateValidationAlert: "Invalid End date"  
},     {% endhighlight %}   
</td></tr>
<tr>
<td>
columnDialogTexts:<br/>
field<br/>
editType<br/>
filterEditType<br/>
allowFiltering<br/>
allowFilteringBlankContent<br/>
allowSorting<br/>
visible<br/>
width<br/>
textAlign<br/>
headerTextAlign<br/>
isFrozen<br/>
allowFreezing<br/>
columnsDropdownData<br/>
dropdownTableText<br/>
dropdownTableValue<br/>
addData<br/>
deleteData<br/>
allowCellSelection</td><td>
{% highlight javascript %}
columnDialogTexts: {   field: "Field",
      headerText: "Header Text",
      editType: "Edit Type",
      filterEditType: "Filter Edit Type",
      allowFiltering: "Allow Filtering",
      allowFilteringBlankContent: "Allow Filtering Blank Content",
      allowSorting: "Allow Sorting",
      visible: "Visible",
      width: "Width",
      textAlign: "Text Alignment",
      headerTextAlign: "Header Text Alignment",
      isFrozen: "Is Frozen",
      allowFreezing: "Allow Freezing",
      columnsDropdownData: "Column Dropdown Data",
      dropdownTableText: "Text",
      dropdownTableValue: "Value",
      addData: "Add",
      deleteData: "Remove",
      allowCellSelection: "Allow Cell Selection"  
},
{% endhighlight %}
</td></tr>
<tr>
<td>
toolboxTooltipTexts:<br/>
addTool<br/>
editTool<br/>
saveTool<br/>
deleteTool<br/>
cancelTool<br/>
searchTool<br/>
indentTool<br/>
outdentTool<br/>
expandAllTool<br/>
collapseAllTool<br/>
nextTimeSpanTool<br/>
prevTimeSpanTool</td><td>
{% highlight javascript %}
toolboxTooltipTexts: {   addTool: "Add",
      editTool: "Edit",
      saveTool: "Update",
      deleteTool: "Delete",
      cancelTool: "Cancel",
      searchTool: "Search",
      indentTool: "Indent",
      outdentTool: "Outdent",
      expandAllTool: "ExpandAll",
      collapseAllTool: "CollapseAll",
      nextTimeSpanTool: "Next Timespan",
      prevTimeSpanTool: "Previous Timespan"  
},
{% endhighlight %}
</td></tr>
<tr>
<td>
contextMenuTexts:<br/>
taskDetailsText<br/>
addNewTaskText<br/>
indentText<br/>
outdentText<br/>
deleteText<br/>
aboveText<br/>
belowText</td><td>
{% highlight javascript %}
contextMenuTexts: {   taskDetailsText: "Task Details...",
      addNewTaskText: "Add New Task",
      indentText: "Indent",
      outdentText: "Outdent",
      deleteText: "Delete",
      aboveText: "Above",
      belowText: "Below"  
},{% endhighlight %}
</td></tr>
<tr>
<td>
newTaskTexts:
newTaskName</td><td>
{% highlight javascript %}
newTaskTexts: {
    newTaskName: "New Task"
},
{% endhighlight %}
</td></tr>
<tr>
<td>
columnMenuTexts:<br/>
sortAscendingText<br/>
sortDescendingText<br/>
columnsText<br/>
insertColumnLeft<br/>
insertColumnRight<br/>
deleteColumn<br/>
renameColumn</td><td>
{% highlight javascript %}
columnMenuTexts: {   sortAscendingText: "Sort Ascending",
      sortDescendingText: "Sort Descending",
      columnsText: "Columns",
      insertColumnLeft: "Insert Column Left",
      insertColumnRight: "Insert Column Right",
      deleteColumn: "Delete Column",
      renameColumn: "Rename Column"  
},
{% endhighlight %}
</td></tr>
<tr>
<td>
columnDialogTitle:<br/>
insertColumn<br/>
deleteColumn<br/>
renameColumn</td><td>
{% highlight javascript %}
columnDialogTitle: {   insertColumn: "Insert Column",
      deleteColumn: "Delete Column",
      renameColumn: "Rename Column"  
},
{% endhighlight %}
</td></tr>
<tr>
<td>
deleteColumnText</td><td>
"Are you sure you want to delete this column?"</td></tr>
<tr>
<td>
okButtonText</td><td>
"OK"</td></tr>
<tr>
<td>
cancelButtonText</td><td>
"Cancel"</td></tr>
<tr>
<td>
confirmDeleteText</td><td>
"Confirm Delete"</td></tr>
<tr>
<td>
predecessorEditingTexts:<br/>
fromText<br/>
toText</td><td>
{% highlight javascript %}
predecessorEditingTexts: {
    fromText: "From",
    toText: "To"
}
{% endhighlight %}
</td></tr>
</table>
To localize the Column Header Texts based on French culture, refer to the following code example.

Refer the external dependency to support localization

{% highlight html %}
<!--Need to add for localize the date Time object based on the culture settings-->

<script src="Scripts/ej.culture.fr.min.js"></script>

{% endhighlight %}

{% highlight javascript %}
ej.Gantt.Locale["fr-FR"] = {

    //headerText to be displayed in TreeGrid

    columnHeaderTexts: {

        taskId: "Tâche Ia",

        taskName: "Tâche Tâche",

        startDate: "Démarrer Date",

        endDate: "Fin Date",

        resourceInfo: "Resources",

        duration: "Durée",

        status: "Progrès",

        predecessor: "Prédécesseur",

        baselineStartDate: "Baseline Démarrer Date",

        baselineEndDate: "Baseline Fin Date"

    },

    //string to display in dialog 

    editDialogTexts: {

        addFormTitle: "Nouveau Tâche",

        editFormTitle: "Modifier Tâche",

        saveButton: "Sauver",

        cancelButton: "Annuler"

    },

}
{% endhighlight %}

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    locale="fr-FR">
</ejGantt> 

{% endhighlight %}

The following screenshot shows Gantt with French culture.

![](Localization_images/Localization_img1.png)