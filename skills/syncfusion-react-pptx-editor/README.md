# Syncfusion<sup>®</sup> React PPTX Editor Skill

## Overview

Build Microsoft PowerPoint–like presentation viewer applications in React using the Syncfusion PPTX Editor. This skill provides AI-guided code generation and integration support for loading, viewing, navigating, presenting, and printing `.pptx` presentations.

See **[SKILL.md](SKILL.md)** for the full intent-routing guide and rules.

---

## Key Capabilities

- **Presentation viewing:** Open and view `.pptx` presentations (text boxes, placeholders, basic auto shapes, images, tables, and basic paragraph and text formatting).
- **Viewer interface:** A PowerPoint-like toolbar/ribbon with tab-based commands.
- **Slide navigation:** Navigate slides using touch, keyboard, mouse, and the thumbnail pane.
- **Zoom:** Zoom in and out of the presentation.
- **Slideshow and presenter view:** Full-screen slideshow, slide notes, and presenter view with speaker notes.
- **Print:** Print the presentation with default print settings.

---

## Getting Started

### How to Integrate Skills

**Step 1: Checkout and copy the required skills**

Clone or download the pptx-editor-sdk-skills repository and copy the **syncfusion-react-pptx-editor** skill from the `skills/` directory.

**Step 2: Install the skill**

Place the copied skill folder in your workspace following this structure:

```
your-workspace/
├── .github/skills/ or .claude/skills/ or .codestudio/skills/
│   └── syncfusion-react-pptx-editor/
│       ├── SKILL.md
│       └── references/
└── your-project-files...
```

**Step 3: Verify and manage your skills**

Type `/skills` in the GitHub Copilot or Code Studio chat to quickly access the Configure Skills menu and manage your installed skills.

**Step 4: Use skills in VS Code**

There are two ways to use skills:

1. **Slash commands** - Type `/` in the GitHub Copilot chat to see available skills. For example:
   ```
   /syncfusion-react-pptx-editor Create a React PPTX Editor that opens a PowerPoint presentation with toolbar, thumbnails, zoom and slideshow
   ```

2. **Automatic loading** - Simply describe your task naturally, and your AI Agent automatically loads the relevant skill:
   ```
   Create a React PPTX Editor that opens a PowerPoint presentation with toolbar, thumbnails, zoom and slideshow
   ```

When a skill is loaded, the AI Agent gains specialized knowledge of the Syncfusion React PPTX Editor and can help you generate code snippets or build complete presentation viewer features.

---

## Prerequisites

### Runnable project

To integrate the PPTX Editor directly into your project files, you need a working React application (Vite recommended). If you don't have one yet, follow the [Getting Started guide](https://help.syncfusion.com/document-processing/powerpoint/pptx-editor/react/getting-started).

**Alternative option:**
- **No project needed:** You can request code snippets directly in the chat window for learning or reference purposes.

---

## Example Prompts

- "Create a PPTX Editor component that loads a presentation from a URL"
- "Create a PPTX Editor with only the thumbnail pane and navigation modules"
- "Show me how to apply the Material 3 theme to the PPTX Editor"

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| **License watermark appears** | Verify that your license key is properly registered. See [Licensing](https://help.syncfusion.com/document-processing/licensing/overview). |
| **Style/Theme not applied** | Import the theme CSS as shown in `references/getting-started.md` and make sure the theme package and import path are correct. Do not use a `theme` property on the editor. |
| **Toolbar, thumbnails, zoom, or slideshow missing** | The feature modules were not injected. See `references/modules-and-features.md`. |
| **Presentation does not load** | Check that `documentPath` is a reachable `.pptx` URL (CORS must allow your origin). |

---

## Resources

- [Documentation](https://help.syncfusion.com/document-processing/powerpoint/pptx-editor/react/overview)
- [Getting Started](https://help.syncfusion.com/document-processing/powerpoint/pptx-editor/react/getting-started)

---

## License

Syncfusion PPTX Editor requires a [commercial license](https://www.syncfusion.com/products/communitylicense) for production use. A free Community License is also available for individual developers and small businesses.
