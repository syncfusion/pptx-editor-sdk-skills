# Getting started with Angular PPTX Editor
> PPTX Editor control creation — view and print PowerPoint presentations.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Setup the environment and create the application](#setup-the-environment-and-create-the-application)
- [Installation](#installation)
- [License Key](#license-key)
- [Theme and CSS](#theme-and-css)
- [Available themes](#available-themes)
- [Initialize the PPTX Editor](#initialize-the-pptx-editor)
- [Run](#run)
- [Placeholders](#placeholders)
- [Common Setup Gotchas](#common-setup-gotchas)

## When to Use This Reference

Use this reference when you need to:
- Create a new Angular application that hosts the PPTX Editor
- Install the PPTX Editor package and register the Syncfusion license
- Apply a theme and initialize the editor with a presentation

## Setup the environment and create the application

```bash
npm install -g @angular/cli
ng new pptx-editor-app
cd pptx-editor-app
```

Suggested CLI answers: stylesheet `CSS`, SSR/SSG `No`, AI tools `None`.

## Installation

```bash
npm install @syncfusion/ej2-angular-pptxeditor --save
```

## License Key

- [Generate a Syncfusion License Key](https://help.syncfusion.com/document-processing/licensing/how-to-generate)
- [Register a Syncfusion License Key in Angular](https://help.syncfusion.com/document-processing/licensing/how-to-register-in-an-application#angular)

Never hardcode the key in generated snippets.

## Theme and CSS

```bash
npm install @syncfusion/ej2-tailwind3-theme
```

Add to `src/styles.css`:

```css
@import "../node_modules/@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
```

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

Every package exposes the PPTX Editor styles at `styles/pptxeditor/index.css`. See the [themes documentation](https://ej2.syncfusion.com/angular/documentation/appearance/theme) for the full list.

Example - switch to the Material 3 theme:

```bash
npm install @syncfusion/ej2-material3-theme
```

```css
@import "../node_modules/@syncfusion/ej2-material3-theme/styles/pptxeditor/index.css";
```

## Initialize the PPTX Editor

Add the following code in `src/app/app.ts`:

```ts
import { Component, ViewEncapsulation } from '@angular/core';
import {
    PptxEditorComponent, MagnificationService, NavigationService,
    PrintService, SlideShowService, ThumbnailViewService, ToolbarService
} from '@syncfusion/ej2-angular-pptxeditor';

@Component({
    selector: 'app-root',
    template: `<div class="content-wrapper">
        <ejs-pptxeditor id="container" documentPath="https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx">
        </ejs-pptxeditor>
    </div>`,
    encapsulation: ViewEncapsulation.None,
    styleUrl: './app.css',
    standalone: true,
    imports: [PptxEditorComponent],
    providers: [ToolbarService, ThumbnailViewService, MagnificationService, NavigationService, PrintService, SlideShowService]
})
export class App { }
```

## Run

```bash
ng serve --open
```

## Placeholders

| Placeholder | Meaning |
|-------------|---------|
| `documentPath` value (`https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx`) | URL of the `.pptx` file to load. Replace with the user's presentation URL. |
| Theme stylesheet (`tailwind3` shown) | Theme is applied only through the imported CSS from the installed theme package. Install another theme package and update the import path; see the "Available themes" table. |

## Common Setup Gotchas

- Use `ViewEncapsulation.None` so the Syncfusion theme styles reach the rendered editor.
- Each module is an Angular **service** (`ToolbarService`, etc.) and must be listed in `providers`; the plain class names (`Toolbar`) are not used in Angular.
- The sample presentation URL is for evaluation. Use the user's own file in production and make sure the host allows cross-origin requests from the app.

See [modules-and-features.md](modules-and-features.md) for the available feature modules.
