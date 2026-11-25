# Getting started with Vue PPTX Editor
> PPTX Editor control creation — view and print PowerPoint presentations.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Create the application](#create-the-application)
- [Installation](#installation)
- [License Key](#license-key)
- [Theme and CSS](#theme-and-css)
- [Available themes](#available-themes)
- [Initialize the PPTX Editor (`src/App.vue`)](#initialize-the-pptx-editor-srcappvue)
- [Run](#run)
- [Placeholders](#placeholders)
- [Common Setup Gotchas](#common-setup-gotchas)

## When to Use This Reference

Use this reference when you need to:
- Create a new Vue application that hosts the PPTX Editor
- Install the PPTX Editor package and register the Syncfusion license
- Apply a theme and initialize the editor with a presentation

## Create the application

### Vue 3 (Vite)

```bash
npm create vite@latest
# Project name: pptx-editor-app, Framework: Vue, Variant: JavaScript
cd pptx-editor-app
npm install
```

### Vue 2 (Vue CLI)

```bash
npm install -g @vue/cli
vue create quickstart
# choose: Default ([Vue 2] babel, eslint)
cd quickstart
```

## Installation

```bash
npm install @syncfusion/ej2-vue-pptxeditor --save
```

## License Key

- [Generate a Syncfusion License Key](https://help.syncfusion.com/document-processing/licensing/how-to-generate)
- [Register a Syncfusion License Key in Vue](https://help.syncfusion.com/document-processing/licensing/how-to-register-in-an-application#vuejs)

Never hardcode the key in generated snippets.

## Theme and CSS

```bash
npm install @syncfusion/ej2-tailwind3-theme
```

Clear the default styles in `src/style.css` (Vue 3) or the `<style>` section of `App.vue` (Vue 2) to avoid conflicts. Import the theme in the `<style>` section of `src/App.vue`:

```html
<style>
@import "@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
</style>
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

Every package exposes the PPTX Editor styles at `styles/pptxeditor/index.css`. See the [themes documentation](https://ej2.syncfusion.com/vue/documentation/appearance/theme) for the full list.

Example - switch to the Material 3 theme:

```bash
npm install @syncfusion/ej2-material3-theme
```

```css
@import "../node_modules/@syncfusion/ej2-material3-theme/styles/pptxeditor/index.css";
```

## Initialize the PPTX Editor (`src/App.vue`)

### Vue 3 - Composition API

```html
<template>
  <div id="app">
    <ejs-pptxeditor id="container" documentPath="https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx">
    </ejs-pptxeditor>
  </div>
</template>

<script setup>
import { provide } from 'vue';
import {
  PptxEditorComponent as EjsPptxeditor,
  Toolbar,
  ThumbnailView,
  Magnification,
  Navigation,
  Print,
  SlideShow
} from '@syncfusion/ej2-vue-pptxeditor';

provide('pptxeditor', [Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow]);
</script>

<style>
@import "@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
</style>
```

### Vue 3 - Options API

```html
<template>
  <div id="app">
    <ejs-pptxeditor id="container" documentPath="https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx">
    </ejs-pptxeditor>
  </div>
</template>

<script>
import {
  PptxEditorComponent,
  Toolbar,
  ThumbnailView,
  Magnification,
  Navigation,
  Print,
  SlideShow
} from '@syncfusion/ej2-vue-pptxeditor';

export default {
  name: 'App',
  components: {
    'ejs-pptxeditor': PptxEditorComponent
  },
  provide: {
    'pptxeditor': [Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow]
  },
}
</script>

<style>
@import "@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
</style>
```

### Vue 2

```html
<template>
  <div id="app">
    <ejs-pptxeditor ref="editor" id="container" documentPath="https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx">
    </ejs-pptxeditor>
  </div>
</template>

<script>
import {
  PptxEditorComponent,
  Toolbar,
  ThumbnailView,
  Magnification,
  Navigation,
  Print,
  SlideShow
} from '@syncfusion/ej2-vue-pptxeditor';

export default {
  name: 'App',
  components: {
    'ejs-pptxeditor': PptxEditorComponent
  },
  provide: {
    pptxeditor: [Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow]
  }
};
</script>

<style>
@import "@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
</style>
```

## Run

```bash
npm run dev      # Vue 3 (Vite)
npm run serve    # Vue 2 (Vue CLI)
```

## Placeholders

| Placeholder | Meaning |
|-------------|---------|
| `documentPath` value (`https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx`) | URL of the `.pptx` file to load. Replace with the user's presentation URL. |
| Theme stylesheet (`tailwind3` shown) | Theme is applied only through the imported CSS from the installed theme package. Install another theme package and update the import path; see the "Available themes" table. |

## Common Setup Gotchas

- Vue 3 Composition API needs the `setup` attribute on `<script>` and the `PptxEditorComponent as EjsPptxeditor` alias so `<ejs-pptxeditor>` resolves.
- The provide key is `pptxeditor` (lowercase); use exactly this key so the modules are injected.
- Use the `@syncfusion/ej2-tailwind3-theme` package in the CSS import for both Vue 2 and Vue 3.
- The sample presentation URL is for evaluation. Use the user's own file in production and make sure the host allows cross-origin requests from the app.

See [modules-and-features.md](modules-and-features.md) for the available feature modules.
