# Getting started with ASP.NET Core PPTX Editor
> PPTX Editor control creation — view and print PowerPoint presentations.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Create the application](#create-the-application)
- [Install the packages](#install-the-packages)
- [Add the Tag Helpers](#add-the-tag-helpers)
- [License Key](#license-key)
- [Stylesheet and script resources](#stylesheet-and-script-resources)
- [Available themes](#available-themes)
- [Script Manager](#script-manager)
- [Add the control (`~/Pages/Index.cshtml`)](#add-the-control-pagesindexcshtml)
- [Run](#run)
- [Placeholders](#placeholders)
- [Common Setup Gotchas](#common-setup-gotchas)

## When to Use This Reference

Use this reference when you need to:
- Create a new ASP.NET Core (C#) application that hosts the PPTX Editor
- Install the PPTX Editor package and register the Syncfusion license
- Apply a theme and initialize the editor with a presentation

## Create the application

```bash
dotnet new webapp -o PptxEditorApp
code -r PptxEditorApp
```

Or create an **ASP.NET Core Web App** in Visual Studio (Microsoft template or the Syncfusion ASP.NET Core extension).

## Install the packages

```bash
dotnet add package Syncfusion.AspNetCore.PptxEditor -v {{SYNCFUSION_VERSION}}
dotnet add package Syncfusion.AspNetCore.Themes -v {{SYNCFUSION_VERSION}}
```

In Visual Studio: **Tools -> NuGet Package Manager -> Manage NuGet Packages for Solution**, or `Install-Package Syncfusion.AspNetCore.PptxEditor -Version {{SYNCFUSION_VERSION}}` in the Package Manager Console.

## Add the Tag Helpers

`~/Pages/_ViewImports.cshtml` (keep the existing imports):

```cshtml
@addTagHelper *, Syncfusion.AspNetCore.Base
@addTagHelper *, Syncfusion.AspNetCore.PptxEditor
```

## License Key

- [Generate a Syncfusion License Key](https://help.syncfusion.com/document-processing/licensing/how-to-generate)
- [Register a license key in ASP.NET Core](https://help.syncfusion.com/document-processing/licensing/how-to-register-in-an-application#aspnet-core)

Never hardcode the key; read it from configuration or an environment variable.

## Stylesheet and script resources

Inside `<head>` of `~/Pages/Shared/_Layout.cshtml` (Tailwind 3 theme shown):

```cshtml
<link rel="stylesheet" href="_content/Syncfusion.AspNetCore.Themes/styles/tailwind3.css" />
<script src="_content/Syncfusion.AspNetCore.PptxEditor/scripts/sf-pptxeditor.min.js"></script>
```

## Available themes

The `Syncfusion.AspNetCore.Themes` package ships the themes as static web assets under `_content/Syncfusion.AspNetCore.Themes/styles/`. Change the theme by replacing the stylesheet file name in the `<link>` - no editor property is involved:

```cshtml
<link rel="stylesheet" href="_content/Syncfusion.AspNetCore.Themes/styles/tailwind3.css" />
```

| Theme | Stylesheet |
|-------|------------|
| `tailwind3` (shown in the example above) | `tailwind3.css` |
| `material3` | `material3.css` |
| `bootstrap5` | `bootstrap5.css` |
| `fluent2` | `fluent2.css` |
| `fabric` | `fabric.css` |
| `highcontrast` | `highcontrast.css` |

## Script Manager

At the end of `<body>` in `_Layout.cshtml`:

```cshtml
<!-- Syncfusion ASP.NET Core Script Manager -->
<ejs-scripts></ejs-scripts>
```

## Add the control (`~/Pages/Index.cshtml`)

```cshtml
@page
@model IndexModel

<ejs-pptxeditor id="pptxeditor"
                documentPath="https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx">
</ejs-pptxeditor>

@section Scripts {
    <script>
        ej.pptxeditor.PptxEditor.Inject(ej.pptxeditor.Toolbar, ej.pptxeditor.ThumbnailView, ej.pptxeditor.Magnification, ej.pptxeditor.Navigation, ej.pptxeditor.Print, ej.pptxeditor.SlideShow);
    </script>
}
```

## Run

```bash
dotnet run
```

(Visual Studio: Ctrl+F5.)

## Placeholders

| Placeholder | Meaning |
|-------------|---------|
| `documentPath` value (`https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx`) | URL of the `.pptx` file to load. Replace with the user's presentation URL. |
| Theme stylesheet (`tailwind3.css` shown) | File name under `_content/Syncfusion.AspNetCore.Themes/styles/`. Pick any name from the "Available themes" table. |
| `{{SYNCFUSION_VERSION}}` | Version of the Syncfusion NuGet packages to install. |

## Common Setup Gotchas

- `<ejs-scripts></ejs-scripts>` must be registered at the end of `<body>` in `_Layout.cshtml`, and the layout must render the `Scripts` section (`@await RenderSectionAsync("Scripts", required: false)`) for the `Inject` call to run.
- Both `Syncfusion.AspNetCore.Base` and `Syncfusion.AspNetCore.PptxEditor` Tag Helpers must be added in `_ViewImports.cshtml`.
- Use the same version for `Syncfusion.AspNetCore.PptxEditor` and `Syncfusion.AspNetCore.Themes`.
- The sample presentation URL is for evaluation. Use the user's own file in production and make sure the host allows cross-origin requests from the app.

See [modules-and-features.md](modules-and-features.md) for the available feature modules.
