# PPTX Editor modules and features — JavaScript
> Feature modules, and `documentPath` for the JavaScript PPTX Editor.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Feature Modules](#feature-modules)
- [Registering Modules](#registering-modules)
- [Core Properties](#core-properties)
- [Notes](#notes)

## When to Use This Reference

Use this reference when the user wants to enable or remove viewer features, change the presentation being displayed, or change the theme.

## Feature Modules

The documented setup injects the following six modules. Together they provide the viewer experience listed in the [overview](https://help.syncfusion.com/document-processing/powerpoint/pptx-editor/javascript-es6/overview).

| Module | Purpose |
|--------|---------|
| `Toolbar` | PowerPoint-like viewer toolbar with tab-based commands |
| `ThumbnailView` | Thumbnail pane for slide navigation |
| `Magnification` | Zoom in and out |
| `Navigation` | Navigate slides with touch, keyboard, and mouse |
| `Print` | Print the presentation with default print settings |
| `SlideShow` | Full-screen slideshow mode |

## Registering Modules

Modules are registered with `PptxEditor.Inject(...)` before the editor is created (ES6/TypeScript), or `ej.pptxeditor.PptxEditor.Inject(...)` (ES5 global build).

```ts
PptxEditor.Inject(Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow);
```

```js
// ES5
ej.pptxeditor.PptxEditor.Inject(ej.pptxeditor.Toolbar, ej.pptxeditor.ThumbnailView, ej.pptxeditor.Magnification, ej.pptxeditor.Navigation, ej.pptxeditor.Print, ej.pptxeditor.SlideShow);
```

Remove a module from the list to remove its feature (for example, drop `Print` to omit printing).

## Core Properties

| Property | Description | Example |
|----------|-------------|---------|
| `documentPath` | URL of the `.pptx` file loaded on render | `https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx` |

## Notes

- Use only the documented modules and properties available for the PPTX Editor. Avoid mentioning undocumented properties, methods, or events.
- The PPTX Editor supports viewing text boxes, placeholders, basic auto shapes, images, tables, and basic paragraph/text formatting. Unsupported content may not render as in PowerPoint.
- To switch themes, install the matching theme package and update the CSS import path. See the theme list in `getting-started.md`.
