# PPTX Editor modules and features — Vue
> Feature modules, and `documentPath` for the Vue PPTX Editor.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Feature Modules](#feature-modules)
- [Registering Modules](#registering-modules)
- [Core Properties](#core-properties)
- [Notes](#notes)

## When to Use This Reference

Use this reference when the user wants to enable or remove viewer features, change the presentation being displayed, or change the theme.

## Feature Modules

The documented setup injects the following six modules. Together they provide the viewer experience listed in the [overview](https://help.syncfusion.com/document-processing/powerpoint/pptx-editor/vue/overview).

| Module | Purpose |
|--------|---------|
| `Toolbar` | PowerPoint-like viewer toolbar with tab-based commands |
| `ThumbnailView` | Thumbnail pane for slide navigation |
| `Magnification` | Zoom in and out |
| `Navigation` | Navigate slides with touch, keyboard, and mouse |
| `Print` | Print the presentation with default print settings |
| `SlideShow` | Full-screen slideshow mode |

## Registering Modules

Modules are registered with `provide('pptxeditor', [...])` (Composition API) or the `provide: { pptxeditor: [...] }` option (Options API / Vue 2). The provide key must be exactly `pptxeditor`.

```js
provide('pptxeditor', [Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow]);
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
