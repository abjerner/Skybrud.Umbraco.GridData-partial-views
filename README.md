# Skybrud.Umbraco.GridData.PartialViews

This repository contains a set of partial views as an example on how the [Skybrud.Umbraco.GridData](https://github.com/skybrud/Skybrud.Umbraco.GridData) package can be used to render the Umbraco Grid using a strongly typed model rather than the default approach using `JObject` and `dynamic`.

The partial views are currently using a version of Skybrud.Umbraco.GridData that hasn't been released yet. The partial views are currently developed and tested against [dee138912a29b146afe28e2baac5354eb773c76e](https://github.com/skybrud/Skybrud.Umbraco.GridData/commit/dee138912a29b146afe28e2baac5354eb773c76e), so you can grab the code from there for now. I'm hoping to make a new release of Skybrud.Umbraco.GridData soon, so in the future, you should just grab the most recent version from NuGet.

The examples are based on the Fanoe starter kit.

**So how to I use the partial views?**  
When installing a new Umbraco installation with the Fanoe starter kit, the starting point for rendering the looks like:

```C#
@CurrentPage.GetGridHtml("content", "fanoe")
```

For the strongly typed model, that line can be changed to (I'll try making that prettier in the future):

```C#
@Html.Partial("TypedGrid/Fanoe", Model.Content.GetPropertyValue<GridDataModel>("content"))
```
