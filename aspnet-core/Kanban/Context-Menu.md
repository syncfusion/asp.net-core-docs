---
layout: post
title: Context Menu  | Kanban | ASP.NET Core | Syncfusion
description: Context Menu 
documentation: ug
control: Kanban
platform: aspnet-core
---

# Context Menu 

Context menu is used to improve user action with Kanban using popup menu. It can be shown by defining [`kanbancontext-menu-settings.enable`] as true. Context menu has option to add default items in [`kanbancontext-menu-settings.MenuItems`] and customized items in [`kanbancontext-menu-settings.custom-menu-items`].

## Default Context Menu items

Please find the below table for default context menu items and its actions.

<table>
        <tr>
            <th>
                Section 
            </th>
            <th>
               Context menu items 
            </th>
            <th>
                Action
            </th>
        </tr>
        <tr>
            <td rowspan="2">
                Header 
            </td>
            <td>
                Hide Column
            </td>
            <td>
               Hide the current column 
            </td>
        </tr>
        <tr>
            <td>
                Visible Columns
            </td>
            <td>
                Show the column if already hidden 
            </td>
        </tr>
       <tr>
            <td>
                Content
            </td>
            <td>
                Add Card 
            </td>
             <td>
                Start Add new card 
            </td>
        </tr>
        <tr>
            <td rowspan="10">
                Card
            </td>
            <td>
               Edit Card 
            </td>
            <td>
               Start Edit in current card 
            </td>
        </tr>
        <tr>
            <td>
               Delete Card 
            </td>
            <td>
                Delete the current card 
            </td>
        </tr>
        <tr>
            <td>
                Top of Row
            </td>
            <td>
                Move the card to Top of Row
            </td>
        </tr>
        <tr>
            <td>
               Bottom of Row
            </td>
            <td>
                Move the card to Bottom of Row
            </td>
        </tr>
        <tr>
            <td>
               Move Up
            </td>
            <td>
                Move the card in Up direction 
            </td>
        </tr>
        <tr>
            <td>
               Move Down
            </td>
            <td>
               Move the card in Down direction
            </td>
        </tr>
        <tr>
            <td>
                Move Left
            </td>
            <td>
                Move the card in Left direction
            </td>
        </tr>
        <tr>
            <td>
               Move Right
            </td>
            <td>
                Move the card in Right direction
            </td>
        </tr>
        <tr>
            <td>
              Move to Swimlane
            </td>
            <td>
                Move the card to Swim lane which is chosen from given list
            </td>
        </tr>
          <tr>
            <td>
              Print Card
            </td>
            <td>
              Print the specific card
            </td>
        </tr>
  </table>

The following code example describes the above behavior.

{% tabs %}

{% highlight razor %}

   <ej-kanban id="KanbanBoard" key-field="Status" dataSource="ViewBag.datasource">
     <e-kanbancolumns>
        <e-kanbancolumn header-text="Backlog" key=@(new List<string>(){"Open"})  >
        </e-kanbancolumn>
        <e-kanbancolumn header-text="In Progress" key=@(new List<string>() {"InProgress"}) ></e-kanbancolumn>
        <e-kanbancolumn header-text="Testing" key=@(new List<string>() { "Testing" }) ></e-kanbancolumn>
        <e-kanbancolumn header-text="Done" key=@(new List<string>() {"Close"}) ></e-kanbancolumn>
     </e-kanbancolumns>
     <e-kanbanfield content="Summary" primary-key="Id">
     </e-kanbanfield>
   <e-kanbancontext-menu-settings enable="true">
     </e-kanbancontext-menu-settings>
     <e-kanbanedit-settings allow-editing="true" allow-adding="true">
        <e-kanbanedit-items>
            <e-kanbanedit-item field="Id" edit-type="String"></e-kanbanedit-item>
            <e-kanbanedit-item field="Status" edit-type="Dropdown"></e-kanbanedit-item>
            <e-kanbanedit-item field="Assignee" edit-type="Dropdown"></e-kanbanedit-item>
            <e-kanbanedit-item field="Estimate" edit-type="Numeric"></e-kanbanedit-item>
            <e-kanbanedit-item field="Summary" edit-type="TextArea"></e-kanbanedit-item>
        </e-kanbanedit-items>
   </e-kanbanedit-settings>
</ej-kanban>
  
{% endhighlight  %}

{% highlight c# %}

    public partial class KanbanBoardController : Controller
    {
        List<Tasks> Task = new List<Tasks>();

        public ActionResult Default()
        {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven walker", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael Suyama", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert King", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura Callahan", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven walker", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael Suyama", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert King", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura Callahan", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            ViewBag.datasource = Task;
            return View();
        }
    }
    public class Tasks
    {
        public Tasks()
        {
        }
        public Tasks(int Id, string Status, string Summary, string Type, string Priority, string Tags, double Estimate, string Assignee, string ImageUrl, int RankId)
        {
            this.Id = Id;
            this.Status = Status;
            this.Summary = Summary;
            this.Type = Type;
            this.Priority = Priority;
            this.Tags = Tags;
            this.Estimate = Estimate;
            this.Assignee = Assignee;
            this.ImageUrl = ImageUrl;
            this.RankId = RankId;
        }
        public int Id { get; set; }
        public string Status { get; set; }
        public string Summary { get; set; }
        public string Type { get; set; }
        public string Priority { get; set; }
        public string Tags { get; set; }
        public double Estimate { get; set; }
        public string Assignee { get; set; }
        public string ImageUrl { get; set; }
        public int RankId { get; set; }
    }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![Default Context Menu items](Context_images/context_img1.png)

![Default Context Menu](Context_images/context_img2.png)

## Custom Context Menu

Custom context menu is used to create your own menu item and its action. To add customized context menu items, you need to use [`kanbancontext-menu-settings.kanbancustom-menu-items`] property and to bind required actions for this, use `context-click` event.

The following code example describes the above behavior.

{% tabs %}

{% highlight razor %}

  <ej-kanban id="KanbanBoard" key-field="Status" dataSource="ViewBag.datasource" context-click="contextClick">
     <e-kanbancolumns>
        <e-kanbancolumn header-text="Backlog" key=@(new List<string>(){"Open"})  >
        </e-kanbancolumn>
        <e-kanbancolumn header-text="In Progress" key=@(new List<string>() {"InProgress"}) ></e-kanbancolumn>
        <e-kanbancolumn header-text="Done" key=@(new List<string>() {"Close"}) ></e-kanbancolumn>
     </e-kanbancolumns>
     <e-kanbanfield content="Summary" primary-key="Id" swimlane-key="Assignee" tag="Tags">
     </e-kanbanfield>
     <e-kanbancontext-menu-settings enable="true" menu-items=@(new List<string>() {" "})>
       <e-kanbancustom-menu-items>
            <e-kanbancustom-menu-item text="Clear Selection"></e-kanbancustom-menu-item>
       </e-kanbancustom-menu-items>
     </e-kanbancontext-menu-settings>
     <e-kanbanedit-settings allow-editing="true" allow-adding="true">
        <e-kanbanedit-items>
            <e-kanbanedit-item field="Id" edit-type="String"></e-kanbanedit-item>
            <e-kanbanedit-item field="Status" edit-type="Dropdown"></e-kanbanedit-item>
            <e-kanbanedit-item field="Assignee" edit-type="Dropdown"></e-kanbanedit-item>
            <e-kanbanedit-item field="Estimate" edit-type="Numeric"></e-kanbanedit-item>
            <e-kanbanedit-item field="Summary" edit-type="TextArea"></e-kanbanedit-item>
        </e-kanbanedit-items>
     </e-kanbanedit-settings>
</ej-kanban>

@section ScriptSection{
<script type="text/javascript">
    function contextClick(args) {
         if (args.text == "Clear Selection")
              this.KanbanSelection.clear();
    }
</script>
}
  
{% endhighlight  %}

{% highlight c# %}

    public partial class KanbanBoardController : Controller
    {
        List<Tasks> Task = new List<Tasks>();

        public ActionResult Default()
        {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven walker", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael Suyama", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert King", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura Callahan", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven walker", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael Suyama", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert King", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura Callahan", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            ViewBag.datasource = Task;
            return View();
        }
    }
    public class Tasks
    {
        public Tasks()
        {
        }
        public Tasks(int Id, string Status, string Summary, string Type, string Priority, string Tags, double Estimate, string Assignee, string ImageUrl, int RankId)
        {
            this.Id = Id;
            this.Status = Status;
            this.Summary = Summary;
            this.Type = Type;
            this.Priority = Priority;
            this.Tags = Tags;
            this.Estimate = Estimate;
            this.Assignee = Assignee;
            this.ImageUrl = ImageUrl;
            this.RankId = RankId;
        }
        public int Id { get; set; }
        public string Status { get; set; }
        public string Summary { get; set; }
        public string Type { get; set; }
        public string Priority { get; set; }
        public string Tags { get; set; }
        public double Estimate { get; set; }
        public string Assignee { get; set; }
        public string ImageUrl { get; set; }
        public int RankId { get; set; }
    }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![Custom Context Menu](Context_images/context_img3.png)

## Sub Context Menu

Sub context menu is used to add customized sub menu to the custom context menu item. To add a sub context menu, you need to use [`kanbancontext-menu-settings.sub-menu`] property and to bind required actions for this, use `context-click` event.

The following code example describes the above behavior.

{% tabs %}

{% highlight razor %}

<ej-kanban id="KanbanBoard" key-field="Status" dataSource="ViewBag.datasource" context-click="contextClick">
    <e-kanbancolumns>
        <e-kanbancolumn header-text="Backlog" key=@(new List<string>(){"Open"})  >
        </e-kanbancolumn>
        <e-kanbancolumn header-text="In Progress" key=@(new List<string>() {"InProgress"}) ></e-kanbancolumn>
        <e-kanbancolumn header-text="Done" key=@(new List<string>() {"Close"}) ></e-kanbancolumn>
    </e-kanbancolumns>
    <e-kanbanfield content="Summary" primary-key="Id" swimlane-key="Assignee" tag="Tags">
    </e-kanbanfield>
     <e-kanbancontext-menu-settings enable="true" menu-items=@(new List<string>() {" "})>
       <e-kanbancustom-menu-items>
            <e-kanbancustom-menu-item text="Clear Selection"></e-kanbancustom-menu-item>
           <e-kanbancustom-menu-item text="Move to Column" template="#submenu"></e-kanbancustom-menu-item>
       </e-kanbancustom-menu-items>
    </e-kanbancontext-menu-settings>
    <e-kanbanedit-settings allow-editing="true" allow-adding="true">
        <e-kanbanedit-items>
            <e-kanbanedit-item field="Id"></e-kanbanedit-item>
            <e-kanbanedit-item field="Status" edit-type="Dropdown"></e-kanbanedit-item>
            <e-kanbanedit-item field="Assignee" edit-type="Dropdown"></e-kanbanedit-item>
            <e-kanbanedit-item field="Estimate" edit-type="Numeric"></e-kanbanedit-item>
            <e-kanbanedit-item field="Summary" edit-type="TextArea"></e-kanbanedit-item>
        </e-kanbanedit-items>
    </e-kanbanedit-settings>
</ej-kanban>
<ul id="submenu">
    <li><a>Open</a></li>
    <li><a>InProgress</a></li>
    <li><a>Close</a></li>
</ul>

<script type="text/javascript">
    function contextClick(args) {
                    if (args.text == "Clear Selection")
                        this.KanbanSelection.clear();
                    else if (args.text != "Move to Column")
                        this.updateCard(args.cardData.Id, args.cardData);
    }

</script>    
	
{% endhighlight  %}

{% highlight c# %}

    public partial class KanbanBoardController : Controller
    {
        List<Tasks> Task = new List<Tasks>();

        public ActionResult Default()
        {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven walker", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael Suyama", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert King", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura Callahan", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven walker", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael Suyama", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert King", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura Callahan", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            ViewBag.datasource = Task;
            return View();
        }
    }
    public class Tasks
    {
        public Tasks()
        {
        }
        public Tasks(int Id, string Status, string Summary, string Type, string Priority, string Tags, double Estimate, string Assignee, string ImageUrl, int RankId)
        {
            this.Id = Id;
            this.Status = Status;
            this.Summary = Summary;
            this.Type = Type;
            this.Priority = Priority;
            this.Tags = Tags;
            this.Estimate = Estimate;
            this.Assignee = Assignee;
            this.ImageUrl = ImageUrl;
            this.RankId = RankId;
        }
        public int Id { get; set; }
        public string Status { get; set; }
        public string Summary { get; set; }
        public string Type { get; set; }
        public string Priority { get; set; }
        public string Tags { get; set; }
        public double Estimate { get; set; }
        public string Assignee { get; set; }
        public string ImageUrl { get; set; }
        public int RankId { get; set; }
    }
 
{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![Sub Context Menu](Context_images/context_img4.png)
