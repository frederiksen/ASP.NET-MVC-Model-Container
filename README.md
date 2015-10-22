# ASP.NET-MVC-Model-Container
Container class that holds multiple models that are shared by a ASP.NET MVC controller and a Razor view

Controller use:
```cs
public class ArchiveController : Controller
{
  public ActionResult Index()
  {
    var model1 = new Model1();
    var model2 = new Model2();
    var model3 = new Model3();

    // Do something
  
    var modelCollection = new ModelCollection();
    modelCollection.AddModel(model1);
    modelCollection.AddModel(model2);
    modelCollection.AddModel(model3);
    return View(modelCollection);
  }
}
```

View use:
```cs
@using Models
@model ModelCollection

@{
  ViewBag.Title = "Model1: " + ((Model.GetModel<Model1>()).Name);
}

<h2>Model2: @((Model.GetModel<Model2>()).Number</h2>

@((Model.GetModel<Model3>()).SomeProperty

```
