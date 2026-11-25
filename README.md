# Syncfusion PPTX Editor SDK Skills

Skills are specialized instruction sets that teach AI assistants how to build presentation viewing features using the platform-specific Syncfusion PPTX Editor. These skills follow the [Agent Skills open standard](https://agentskills.io/) and include a `SKILL.md` manifest plus topic-level references to guide automated code generation.

## About This Repository

This repository contains **AI-ready skills** for the PPTX Editor across web platforms. Each skill enables an AI to generate code snippets for loading, viewing, navigating, presenting, and printing PowerPoint presentations. The skills cover only what the PPTX Editor documentation currently covers (getting started and feature modules).

## Included Platform-Specific PPTX Editor Skills

- **React PPTX Editor** (`syncfusion-react-pptx-editor`)
- **Angular PPTX Editor** (`syncfusion-angular-pptx-editor`)
- **Vue PPTX Editor** (`syncfusion-vue-pptx-editor`) – Vue 3 (Composition/Options API) and Vue 2
- **JavaScript PPTX Editor** (`syncfusion-javascript-pptx-editor`) – ES6/TypeScript and ES5
- **ASP.NET Core PPTX Editor** (`syncfusion-aspnetcore-pptx-editor`)
- **ASP.NET MVC PPTX Editor** (`syncfusion-aspnetmvc-pptx-editor`)

## Getting Started

**Step 1:** Clone or download this repository and copy the skill folders you need from `skills/`.

**Step 2:** Place them in your workspace:

```
your-workspace/
├── .github/skills/ or .claude/skills/ or .codestudio/skills/
│   ├── syncfusion-react-pptx-editor/
│   │   ├── SKILL.md
│   │   └── references/
│   └── ...
└── your-project-files...
```

**Step 3:** Use the skills.

1. **Automatic loading** — describe the task naturally:
   ```
   Create a PPTX Editor that opens a presentation with thumbnails and slideshow
   ```
2. **Slash commands** — type `/` in GitHub Copilot or Syncfusion Code Studio chat:
   ```
   /syncfusion-react-pptx-editor Create a PPTX Editor with the Tailwind 3 theme.
   ```

## Contributing

See [docs/skill-authoring-guide.md](docs/skill-authoring-guide.md) and run `python scripts/validate_skills.py` before opening a pull request.
