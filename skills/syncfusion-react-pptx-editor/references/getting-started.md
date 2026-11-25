# Getting started with React PPTX Editor
> PPTX Editor control creation — view and print PowerPoint presentations.

## Table of Contents

- [When to Use This Reference](#when-to-use-this-reference)
- [Create the application](#create-the-application)
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
- Create a new React application that hosts the PPTX Editor
- Install the PPTX Editor package and register the Syncfusion license
- Apply a theme and initialize the editor with a presentation

## Create the application

```bash
npm create vite@latest pptx-editor-app -- --template react-ts
cd pptx-editor-app
```

Use `--template react` for a JavaScript project.

## Installation

```bash
npm install @syncfusion/ej2-react-pptxeditor --save
```

## License Key

Generate a key and register it before the component renders:
- [Generate a Syncfusion License Key](https://help.syncfusion.com/document-processing/licensing/how-to-generate)
- [Register a Syncfusion License Key in React](https://ej2.syncfusion.com/react/documentation/licensing/license-key-registration)

Never hardcode the key in generated snippets; read it from an environment variable or config file.

## Theme and CSS

Install a theme package (Tailwind 3 shown):

```bash
npm install @syncfusion/ej2-tailwind3-theme
```

Clear the default content of `src/index.css` (Vite defaults conflict with Syncfusion styles), then add:

```css
@import "../node_modules/@syncfusion/ej2-tailwind3-theme/styles/pptxeditor/index.css";
```

The theme's `pptxeditor/index.css` loads all dependent styles automatically.

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

Every package exposes the PPTX Editor styles at `styles/pptxeditor/index.css`. See the [themes documentation](https://ej2.syncfusion.com/react/documentation/appearance/theme) for the full list.

Example - switch to the Material 3 theme:

```bash
npm install @syncfusion/ej2-material3-theme
```

```css
@import "../node_modules/@syncfusion/ej2-material3-theme/styles/pptxeditor/index.css";
```

## Initialize the PPTX Editor

Add the following code in `src/App.tsx`:

```tsx
import {
  PptxEditorComponent,
  Toolbar,
  ThumbnailView,
  Magnification,
  Navigation,
  Print,
  SlideShow,
  Inject
} from '@syncfusion/ej2-react-pptxeditor';

function App() {
  return (
    <div className='control-section'>
      <PptxEditorComponent id='container' documentPath='https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx'>
        <Inject services={[Toolbar, ThumbnailView, Magnification, Navigation, Print, SlideShow]} />
      </PptxEditorComponent>
    </div>
  );
}

export default App;
```

## Run

```bash
npm run dev
```

## Placeholders

| Placeholder | Meaning |
|-------------|---------|
| `documentPath` value (`https://document.syncfusion.com/content/pptxeditor-resources/Sample.pptx`) | URL of the `.pptx` file to load. Replace with the user's presentation URL. |
| Theme stylesheet (`tailwind3` shown) | Theme is applied only through the imported CSS from the installed theme package. Install another theme package and update the import path; see the "Available themes" table. |

## Common Setup Gotchas

- Leaving Vite's default `src/index.css` content causes style conflicts; clear it.
- Do not forget `<Inject services={[...]} />`; without it the toolbar, thumbnails, zoom, navigation, print and slideshow UI are not available.
- The sample presentation URL is for evaluation. Use the user's own file in production and make sure the host allows cross-origin requests from the app.

See [modules-and-features.md](modules-and-features.md) for the available feature modules.
