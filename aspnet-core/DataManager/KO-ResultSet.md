---
layout: post
title: KO-ResultSet | DataManager | ASP.NET Core | Syncfusion
description: ko resultset
platform: aspnet-core
control: DataManager
documentation: ug
keywords : KO ResultSet
---

# KO ResultSet

The **DataManager** contains a default method to subscribe the view model properties as KO observable. This is done at the success of the **executeQuery** using the **getKnockoutModel.** You can also provide computed properties to the view model using the getKnockoutModel.

The following code example illustrates on how the model is made observable and updated.

{% tabs %}

{% highlight c# %}

    public IActionResult KOResult()
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
                    <tbody data-bind="foreach: employees">
                        <tr>
                            <td data-bind="text: EmployeeID"></td>
                            <td data-bind="text: FullName"></td>
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

    <script type="text/javascript">
        $(function () {
           
            window.pageModel = {
                employees: []
            };
          
            var query = ej.Query();
            var promise = window.myData.executeQuery(query);
            promise.done(function (e) {
                pageModel.employees = e.getKnockoutModel({
                    FullName: function () {
                        return this.FirstName() + " " + this.LastName();
                    }
                });
                ko.applyBindings(pageModel);
            });
        });
        $("#formsubmit").click(function (e) {
            var empId = parseInt($("#empId").val(), 10);
            var fName = $("#first").val();
            var lName = $("#last").val();
            employee = window.pageModel.employees()[empId - 1];
            employee.FirstName(fName);
            employee.LastName(lName);
        });
    </script>

{% endhighlight %}

{% endtabs %}

The result of the above code example is illustrated as follows.

Before changing the model, EmployeeID 1 has FullName value as Nancy Davolio. After changing, the result is as follows.

![](KO-ResultSet_images/KO-ResultSet_img1.png) 

