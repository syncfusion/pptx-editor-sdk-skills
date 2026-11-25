# PPTX Editor modules and features — ASP.NET Core
> Feature modules, and `documentPath` for the ASP.NET Core (C#) PPTX Editor.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Feature Modules](#feature-modules)
- [Registering Modules](#registering-modules)
- [Core Properties](#core-properties)
- [Notes](#notes)

## When to Use This Reference

Use this reference when the user wants to enable or remove viewer features, change the presentation being displayed, or change the theme.

## Feature Modules

The documented setup injects the following six modules. Together they provide the viewer experience listed in the [overview](https://help.syncfusion.com/document-processing/powerpoint/pptx-editor/asp-net-core/overview).

| Module | Purpose |
|--------|---------|
| `Toolbar` | PowerPoint-like viewer toolbar with tab-based commands |
| `ThumbnailView` | Thumbnail pane for slide navigation |
| `Magnification` | Zoom in and out |
| `Navigation` | Navigate slides with touch, keyboard, and mouse |
| `Print` | Print the presentation with default print settings |
| `SlideShow` | Full-screen slideshow mode |

## Registering Modules

Modules are registered in a `@section Scripts` block on the page using `ej.pptxeditor.PptxEditor.Inject(...)`.

```cshtml
@section Scripts {
    <script>
        ej.pptxeditor.PptxEditor.Inject(ej.pptxeditor.Toolbar, ej.pptxeditor.ThumbnailView, ej.pptxeditor.Magnification, ej.pptxeditor.Navigation, ej.pptxeditor.Print, ej.pptxeditor.SlideShow);
    </script>
}
```

Remove a module from the list to remove its feature (for example, drop `Print` to omit printing).

## Core Properties

| Property | Description | Example |
|----------|-------------|---------|
| `documentPath` | URL of the `.pptx` file loaded on render | `https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx` |

## Notes

- Use only the documented modules and properties available for the PPTX Editor. Avoid mentioning undocumented properties, methods, or events.
- The PPTX Editor supports viewing text boxes, placeholders, basic auto shapes, images, tables, and basic paragraph/text formatting. Unsupported content may not render as in PowerPoint.
- To switch themes, change the stylesheet file name in the `_content/Syncfusion.AspNetCore.Themes/styles/` link in `_Layout.cshtml` (for example `material3.css`). See the theme list in `getting-started.md`.
