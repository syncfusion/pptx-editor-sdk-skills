# Getting started with JavaScript PPTX Editor
> PPTX Editor control creation — view and print PowerPoint presentations.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [ES6 / TypeScript](#es6--typescript)
- [ES5 (global scripts)](#es5-global-scripts)
- [Available themes](#available-themes)
- [Placeholders](#placeholders)
- [Common Setup Gotchas](#common-setup-gotchas)

## When to Use This Reference

Use this reference when you need to:
- Create a new JavaScript application that hosts the PPTX Editor
- Install the PPTX Editor package and register the Syncfusion license
- Apply a theme and initialize the editor with a presentation

## ES6 / TypeScript

### Set up the environment

Prerequisites: [Git](https://git-scm.com/downloads) and [Node.js](https://nodejs.org/en/).

```bash
git clone https://github.com/SyncfusionExamples/ej2-quickstart-webpack ej2-quickstart
cd ej2-quickstart
```

### Install the package

The quickstart ships with `@syncfusion/ej2` (all controls). To install only the PPTX Editor, replace the dependency in `package.json`:

```js
"dependencies": {
  "@syncfusion/ej2-pptxeditor": "*"
}
```

```bash
npm install
npm install @syncfusion/ej2-tailwind3-theme
```

### License Key

- [Generate a Syncfusion License Key](https://help.syncfusion.com/document-processing/licensing/how-to-generate)
- [Register a Syncfusion License Key in JavaScript ES6 / TypeScript](https://help.syncfusion.com/document-processing/licensing/how-to-register-in-an-application#javascript-es6--typescript)

### CSS

Clear the default `~/src/styles/styles.css`, then add (the Tailwind 3 theme is used as an example; see "Available themes" below):

```css
@import "../../node_modules/@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
```

### Initialize

`index.html`:

```html
<body>
    <!-- Element which will render as PPTX Editor -->
    <div id="pptxEditor"></div>
</body>
```

`app.ts`:

```ts
// Import the PPTX Editor and the feature modules
import {
  PptxEditor,
  Toolbar,
  ThumbnailView,
  Magnification,
  Navigation,
  Print,
  SlideShow
} from '@syncfusion/ej2-pptxeditor';

PptxEditor.Inject(Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow);

let editor: PptxEditor = new PptxEditor({
  documentPath: 'https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx'
});
editor.appendTo('#pptxEditor');
```

### Run

```bash
npm start
```

## ES5 (global scripts)

### Application structure

```text
pptx-editor-app/
├── index.html
└── index.js
```

### Add resources

Add these at the end of `<head>` in `index.html`. The example uses CDN links; `{{RELEASE_VERSION}}` is the Syncfusion release version to use. For local resources, download the PPTX Editor SDK, copy the packages from `<Install path>/Syncfusion/Essential Studio/PPTX Editor SDK/<version>/Web (Essential JS 2)/JavaScript` into a `resources` folder and point each `href`/`src` at `resources/<package>/...` instead of the CDN.

```html
<!-- PPTX Editor dependent theme -->
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-base/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-buttons/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-inputs/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-popups/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-lists/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-navigations/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-splitbuttons/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-dropdowns/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<!-- PPTX Editor theme -->
<link href="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-pptxeditor/styles/tailwind3.css" rel="stylesheet" type="text/css" />
<!-- PPTX Editor dependent scripts -->
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-base/dist/global/ej2-base.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-data/dist/global/ej2-data.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-buttons/dist/global/ej2-buttons.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-popups/dist/global/ej2-popups.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-splitbuttons/dist/global/ej2-splitbuttons.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-inputs/dist/global/ej2-inputs.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-lists/dist/global/ej2-lists.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-navigations/dist/global/ej2-navigations.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-dropdowns/dist/global/ej2-dropdowns.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-charts/dist/global/ej2-charts.min.js" type="text/javascript"></script>
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-office-chart/dist/global/ej2-office-chart.min.js" type="text/javascript"></script>
<!-- PPTX Editor script -->
<script src="https://cdn.syncfusion.com/ej2/{{RELEASE_VERSION}}/ej2-pptxeditor/dist/global/ej2-pptxeditor.min.js" type="text/javascript"></script>
```

### License Key

- [Register a Syncfusion License Key in JavaScript ES5](https://help.syncfusion.com/document-processing/licensing/how-to-register-in-an-application#javascript-es5)

### Initialize

`index.html`:

```html
<body>
    <!-- Element that renders the PPTX Editor -->
    <div id='pptxEditor'></div>
    <script src="index.js" type="text/javascript"></script>
</body>
```

`index.js`:

```js
// Inject the required modules
ej.pptxeditor.PptxEditor.Inject(
    ej.pptxeditor.Toolbar,
    ej.pptxeditor.ThumbnailView,
    ej.pptxeditor.Magnification,
    ej.pptxeditor.Navigation,
    ej.pptxeditor.Print,
    ej.pptxeditor.SlideShow
);

// Initialize PPTX Editor component
var editor = new ej.pptxeditor.PptxEditor({
    documentPath: 'https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx'
});

// Render the PPTX Editor
editor.appendTo('#pptxEditor');
```

Open `index.html` in a browser to run it.

## Available themes

Themes are shipped as separate npm packages. Install the theme you want, then replace the package name and the theme name in the CSS import path.

| Theme | npm package |
|-------|-------------|
| `tailwind3` (used in the examples above) | `@syncfusion/ej2-tailwind3-theme` |
| `material3` | `@syncfusion/ej2-material3-theme` |
| `bootstrap5` | `@syncfusion/ej2-bootstrap5-theme` |
| `fluent2` | `@syncfusion/ej2-fluent2-theme` |
| `fabric` | `@syncfusion/ej2-fabric-theme` |
| `highcontrast` | `@syncfusion/ej2-highcontrast-theme` |

Every package exposes the PPTX Editor styles at `styles/pptxeditor/index.css`. See the [themes documentation](https://ej2.syncfusion.com/javascript/documentation/appearance/theme) for the full list.

Example - switch to the Material 3 theme:

```bash
npm install @syncfusion/ej2-material3-theme
```

```css
@import "../node_modules/@syncfusion/ej2-material3-theme/styles/pptxeditor/index.css";
```

## Placeholders

| Placeholder | Meaning |
|-------------|---------|
| `documentPath` value (`https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx`) | URL of the `.pptx` file to load. Replace with the user's presentation URL. |
| Theme stylesheet (`tailwind3` shown) | Theme is applied only through the imported CSS from the installed theme package. Install another theme package and update the import path; see the "Available themes" table. |
| `{{RELEASE_VERSION}}` | Syncfusion release version used in CDN URLs. |

## Common Setup Gotchas

- Inject modules **before** constructing the editor.
- The container element id passed to `appendTo` (`#pptxEditor`) must exist in the DOM when the script runs.
- ES5 requires the dependent scripts (including `ej2-charts` and `ej2-office-chart`) to load before `ej2-pptxeditor.min.js`.
- Replace every `tailwind3.css` reference together when another theme is chosen.
- The sample presentation URL is for evaluation. Use the user's own file in production and make sure the host allows cross-origin requests from the app.

See [modules-and-features.md](modules-and-features.md) for the available feature modules.
