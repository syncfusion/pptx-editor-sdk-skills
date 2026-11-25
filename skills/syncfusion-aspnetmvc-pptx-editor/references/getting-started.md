# Getting started with ASP.NET MVC PPTX Editor
> PPTX Editor control creation — view and print PowerPoint presentations.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Create the application](#create-the-application)
- [Install the package](#install-the-package)
- [Add the namespace (`~/Views/Web.config`)](#add-the-namespace-viewswebconfig)
- [Style and script references (`~/Views/Shared/_Layout.cshtml`)](#style-and-script-references-viewssharedlayoutcshtml)
- [Available themes](#available-themes)
- [Script Manager](#script-manager)
- [License Key](#license-key)
- [Add the control (`~/Views/Home/Index.cshtml`)](#add-the-control-viewshomeindexcshtml)
- [Run](#run)
- [Placeholders](#placeholders)
- [Common Setup Gotchas](#common-setup-gotchas)

## When to Use This Reference

Use this reference when you need to:
- Create a new ASP.NET MVC (C#) application that hosts the PPTX Editor
- Install the PPTX Editor package and register the Syncfusion license
- Apply a theme and initialize the editor with a presentation

## Create the application

Create an ASP.NET MVC project with the [Microsoft templates](https://learn.microsoft.com/en-us/aspnet/mvc/overview/getting-started/introduction/getting-started#create-your-first-app) or the [Syncfusion ASP.NET MVC extension](https://ej2.syncfusion.com/aspnetmvc/documentation/visual-studio-integration/create-project).

## Install the package

Visual Studio: **Tools -> NuGet Package Manager -> Manage NuGet Packages for Solution**, search `Syncfusion.AspNetMvc.PptxEditor`. Or in the Package Manager Console:

```powershell
Install-Package Syncfusion.AspNetMvc.PptxEditor -Version {{SYNCFUSION_VERSION}}
```

## Add the namespace (`~/Views/Web.config`)

```xml
<namespaces>
    <add namespace="Syncfusion.EJ2" />
</namespaces>
```

## Style and script references (`~/Views/Shared/_Layout.cshtml`)

```cshtml
<head>
    <link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/tailwind3.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/dist/ej2.min.js"></script>
</head>
```

Other ways to include styles (NPM, CRG) are described in the [Themes topic](https://ej2.syncfusion.com/aspnetmvc/documentation/appearance/theme) and [Adding Script Reference](https://ej2.syncfusion.com/aspnetmvc/documentation/common/adding-script-references).

## Available themes

The theme is a single Syncfusion CDN stylesheet. Change the theme by replacing the file name in the `<link>` of `_Layout.cshtml` - no editor property is involved:

```cshtml
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/tailwind3.css" rel="stylesheet" />
```

| Theme | Stylesheet |
|-------|------------|
| `tailwind3` (shown in the example above) | `tailwind3.css` |
| `material3` | `material3.css` |
| `bootstrap5` | `bootstrap5.css` |
| `fluent2` | `fluent2.css` |
| `fabric` | `fabric.css` |
| `highcontrast` | `highcontrast.css` |

The same theme names apply to the npm and CRG packages described in the [Themes topic](https://ej2.syncfusion.com/aspnetmvc/documentation/appearance/theme).

## Script Manager

Before the closing `</body>` in `_Layout.cshtml`:

```cshtml
<!-- Syncfusion ASP.NET MVC Script Manager -->
@Html.EJS().ScriptManager()
```

## License Key

Register a key before the control renders:
- [Generate a Syncfusion License Key](https://help.syncfusion.com/document-processing/licensing/how-to-generate)
- [Register a Syncfusion License Key in an application](https://help.syncfusion.com/document-processing/licensing/how-to-register-in-an-application)

Never hardcode the key in generated snippets.

## Add the control (`~/Views/Home/Index.cshtml`)

```cshtml
@Html.EJS().PptxEditor("pptxeditor").DocumentPath("https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx").Render()
```

## Run

Press Ctrl+F5 (Windows) or Cmd+F5 (macOS).

## Placeholders

| Placeholder | Meaning |
|-------------|---------|
| `documentPath` value (`https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx`) | URL of the `.pptx` file to load. Replace with the user's presentation URL. |
| Theme stylesheet (`tailwind3` shown) | Theme is applied only through the CDN stylesheet. Replace the file name with any theme from the "Available themes" table. |
| `{{RELEASE_VERSION}}` | Syncfusion release version used in CDN URLs. |
| `{{SYNCFUSION_VERSION}}` | Version of the Syncfusion NuGet packages to install. |

## Common Setup Gotchas

- `@Html.EJS().ScriptManager()` must be present in `_Layout.cshtml`; without it the control renders no UI.
- The `Syncfusion.EJ2` namespace must be added to `~/Views/Web.config` (not the root `Web.config`).
- The CDN stylesheet and `ej2.min.js` must use the same release version as the installed NuGet package.
- The sample presentation URL is for evaluation. Use the user's own file in production and make sure the host allows cross-origin requests from the app.

See [modules-and-features.md](modules-and-features.md) for the available feature modules.
