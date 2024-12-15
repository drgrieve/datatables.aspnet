# Datatables.AspNet

Simplified opinionated model binding and mapping from jQuery DataTables into .NET typed models with support for `.NET 8.0`.

This is a fork from (https://github.com/ALMMa/datatables.aspnet) which is the orginal author, but no longer maintained

## Compatibility

This library is compatible with the following stacks:

- `.NET 8.0`

## Basic usage

services.RegisterDataTables();

or 

[ModelBinder(typeof(ModelBinder))] IDataTablesRequest model

public virtual IActionResult ListData(IDataTablesRequest model)
{
    var data = _service.Users_Query(model);
    var total = _service.Users_Total();

    return model.GetActionResult(total, data.TotalCount, data);
}

## Standard NuGet packages

- [DataTables.AspNet.AspNetCore](https://www.nuget.org/packages/DataTables.AspNet.AspNetCore/) with support for AspNetCore, dependency injection and automatic binders

### Write your own code!

DataTables.AspNet ships with a core project called [DataTables.AspNet.Core](https://www.nuget.org/packages/DataTables.AspNet.Core/), which contains basic interfaces and core elements just the way DataTables needs.<br />
Feel free to use it and implement your own classes, methods and extend DataTables.AspNet in <i>your</i> very own way.

## Samples

Samples are provided on the `samples` folder.<br />

## Eager for some new code?

If you are, check out [v3](https://github.com/drgrieve/datatables.aspnet) branch. It has the latest code for DataTables.AspNet, including samples and more.<br />
For every release (even unstable ones) there should be a nuget package.
