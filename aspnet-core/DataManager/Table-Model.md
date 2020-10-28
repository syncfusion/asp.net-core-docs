---
layout: post
title: Table-Model | DataManager | ASP.NET Core | Syncfusion
description: table model
platform: aspnet-core
control: DataManager
documentation: ug
keywords : Table Model, getTableModel
---

# Table Model

The **DataManager** contains a default support to bind a TableModel to the element. You can make the data observable using the **getTableModel** method. The **getTableModel** method also accept extra properties or properties with computed value that can be added to the TableModel. In the view, you can create a simple view by using the bindings **getTableModel**

Then the model is bound with the element using the **bindTo.** 

{% tabs %}

{% highlight c# %}

    public IActionResult TableModel()
    {
            List<Employyee> emp = new List<Employyee>();
            emp.Add(new Employyee( 1, "ALFKI","Berlin"));
            emp.Add(new Employyee(2, "ANATR","Madrid"));
            emp.Add(new Employyee(3, "ANTON","Cholchester"));
            emp.Add(new Employyee( 4, "BLONP" ,"Marseille"));
            emp.Add(new Employyee( 5, "BOLID", "Tsawassen"));
        
        ViewBag.empData = emp;
        return View();
    }
    public class Employyee
    {
        public Employyee()
        {

        }
        public Employyee(int EmployeeID, string FirstName, string LastName)
        {
            this.EmployeeID = EmployeeID;
            this.FirstName = FirstName;
            this.LastName = LastName;
            
        }

        public int? EmployeeID { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }
    }

{% endhighlight %}

{% highlight html %}

    <div class="datatable" style="padding:10px">
        <div class="row">
            <div class="col-md-7">
                <table id="table1" class="table table-striped table-bordered" style="width:700px">
                    <thead>
                        <tr>
                            <th>EmployeeID</th>
                            <th>Full Name</th>
                        </tr>
                    </thead>
                    <tbody id="tbody1">
                        <tr>
                            <td ej-observe="EmployeeID"></td>
                            <td ej-computed="FullName"></td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div class="col-md-5">
                <form class="form-horizontal" role="form">
                    <div class="form-group">
                        <label class="col-sm-4 control-label">EmployeeID</label>
                        <div class="col-sm-8">
                            <input type="text" class="form-control" id="empId">
                        </div>
                    </div>
                    <div class="form-group">
                        <label class="col-sm-4 control-label">FirstName</label>
                        <div class="col-sm-8">
                            <input type="text" class="form-control" id="first">
                        </div>
                    </div>
                    <div class="form-group">
                        <label class="col-sm-4 control-label">LastName</label>
                        <div class="col-sm-8">
                            <input type="text" class="form-control" id="last">
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="col-sm-offset-4 col-sm-4">
                            <button type="button" id="formsubmit" class="btn btn-default">Change</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
   
{% endhighlight %}

{% highlight Razor %}

    /*ej-Tag Helper code to render DataManager*/

    <e-datamanager id="myData" json="(IEnumerable<object>)ViewBag.empData"></e-datamanager>

    /*Razor code to render DataManager*/

    @{Html.EJ().DataManager("myData").Json((IEnumerable<object>)ViewBag.empData).Render();}

{% endhighlight %}

{% highlight javascript %}

    <script>
        setTimeout(function () {
            var query = ej.Query();
            var promise = window.myData.executeQuery(query);
            promise.done(function (e) {
                employees = e.getTableModel({
                    FullName: {
                        value: function () {
                            return this.FirstName + ' ' + this.LastName;
                        },
                        deps: ["FirstName", "LastName"]
                    }
                });
                employees.bindTo($("#tbody1"));
            });

        });
        $("#formsubmit").click(function (e) {
            var empId = parseInt($("#empId").val(), 10);
            var fName = $("#first").val();
            var lName = $("#last").val();
            emp = employees.get(empId - 1);
            emp.set("FirstName", fName);
            emp.set("LastName", lName);
        });
    </script>

{% endhighlight %}

{% endtabs %}

The result for the above code example is illustrated as follows.

![](Table-Model_images/Table-Model_img1.png) 



