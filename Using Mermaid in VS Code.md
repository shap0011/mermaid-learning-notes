# Using Mermaid in VS Code

Install `Markdown Preview Mermaid Support` extension

## Markdown Preview Mermaid Support

Adds Mermaid diagram and flowchart support to VS Code's builtin Markdown preview and to Markdown cells in notebooks. A mermaid diagram in VS Code's built-in markdown preview.

Usage:
Create diagrams in markdown using mermaid fenced code blocks:

````
```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```
````

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

**Configuration:**
_markdown-mermaid.lightModeTheme_ — Configures the Mermaid theme used when VS Code is using a light color theme. Supported values are: "base", "forest", "dark", "default", "neutral". Currently not supported in notebooks.

_markdown-mermaid.darkModeTheme_ — Configures the Mermaid theme used when VS Code is using a dark color theme. Supported values are: "base", "forest", "dark", "default", "neutral". Currently not supported in notebooks.

_markdown-mermaid.languages_ — Configures language ids for Mermaid code blocks. The default is ["mermaid"].

````
```mermaid
graph LR
    A(["✅ Done"]) --> B(["☕ Break"])
```
````

```mermaid
graph LR
    A(["✅ Done"]) --> B(["☕ Break"])
```

---

Install `Markdown Preview Enhanced` extension
Author: Yiyi Wang
Downloads: 1M+
ID: shd101wyy.markdown-preview-enhanced

---
