# Contributing

Contributions are welcome! Here's how to add your workflow.

## Adding a Workflow

1. **Fork** this repository
2. Create a folder: `your-workflow-name/`
3. Add your workflow: `your-workflow-name/workflows/your-workflow.json`
4. Add a README.md with description
5. Submit a **Pull Request**

## Folder Structure

```
your-workflow-name/
├── README.md           # Description, setup, screenshots
└── workflows/
    └── your-workflow.json
```

## README Template

```markdown
# Your Workflow Name

Brief description of what this workflow does.

## Setup

1. Import `workflows/your-workflow.json` into n8n
2. Configure credentials: [list required credentials]
3. Activate the workflow

## Nodes

- Node 1 — Purpose
- Node 2 — Purpose

## Screenshot

![Workflow](screenshot.png)
```

## Guidelines

- Use descriptive folder names (kebab-case)
- Include a README for each workflow
- Remove personal credentials before committing
- Test your workflow before submitting

## Questions?

Open an issue or reach out directly.
