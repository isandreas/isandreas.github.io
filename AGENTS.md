# Agent Instructions & Project Knowledge Base

> [!IMPORTANT]
> **Single Source of Truth Policy**:
> - **DO NOT directly modify or overwrite the symlink files** (`CLAUDE.md`, `GEMINI.md`, and `.github/copilot-instructions.md`).
> - Doing so may break or convert symbolic links into disconnected duplicate files.
> - **Always make documentation updates directly in `AGENTS.md`**.

---

## 1. Project Overview

- **Repository**: Personal portfolio website for **Andreas Isnawan** (Senior Software Engineer).
- **Live URL**: [https://isandreas.github.io/](https://isandreas.github.io/)
- **Architecture**: Static Site Generation (SSG) with SvelteKit and `@sveltejs/adapter-static`, hosted on GitHub Pages via automated GitHub Actions CI/CD.

---

## 2. Technology Stack & Tooling

| Category | Technology / Version | Notes |
| :--- | :--- | :--- |
| **Framework** | SvelteKit 2 (`@sveltejs/kit` ^2.70.3) | Using `@sveltejs/adapter-static` for SSG |
| **Component Model** | Svelte 5 (`svelte` ^5.57.2) | Standardized on Svelte 5 Runes (`$state`, `$derived`, etc.) |
| **Language** | TypeScript 5 (`typescript` ^5.9.3) | Strict type checking enabled via `tsconfig.json` |
| **Styling** | Tailwind CSS 3 (`tailwindcss` ^3.4.19) | Utility-first CSS with PostCSS & Autoprefixer |
| **UI Primitives** | shadcn-svelte (`bits-ui` ^0.21.16) | Headless accessible components with `tailwind-variants` |
| **Icons** | Lucide Svelte (`lucide-svelte` ^0.468.0) | Consistent iconography across components |
| **Theme Management** | Mode Watcher (`mode-watcher` ^0.4.1) | Dark/Light theme switching support |
| **Bundler & Build** | Vite 5 (`vite` ^5.4.21) | `@sveltejs/vite-plugin-svelte` |
| **Package Manager** | `pnpm` / `npm` | `pnpm-lock.yaml` tracked in repository |

---

## 3. Directory Structure

```text
├── .github/
│   ├── agents/                     # Specialized agent configurations (e.g. svelte-file-editor)
│   ├── skills/                     # Agent skills (e.g. svelte-code-writer, svelte-core-bestpractices)
│   └── workflows/
│       └── deploy.yml              # GitHub Actions automated deployment to GitHub Pages
├── src/
│   ├── app.css                     # Global Tailwind styles & CSS custom property tokens
│   ├── app.html                    # Root HTML document shell
│   ├── lib/
│   │   ├── components/
│   │   │   ├── ui/                 # Reusable shadcn-svelte primitives (badge, button, card)
│   │   │   ├── Contact.svelte      # Contact details and channels
│   │   │   ├── Hero.svelte         # Hero landing section, intro, and social links
│   │   │   ├── Portfolio.svelte    # Featured projects carousel with modal screenshot viewer
│   │   │   ├── Skills.svelte       # About me bio & animated marquee skills
│   │   │   └── ThemeToggle.svelte  # Light/Dark mode toggle button
│   │   └── utils.ts                # Tailwind clsx + twMerge utility function (`cn`)
│   └── routes/
│       ├── +layout.svelte          # Root layout shell with ModeWatcher & navbar
│       ├── +page.svelte            # Main landing page assembling all sections
│       └── +page.ts                # Page prerender configuration (`export const prerender = true`)
├── static/                         # Static assets (.nojekyll, project screenshots)
├── svelte.config.js                # SvelteKit static adapter configuration
├── tailwind.config.js              # Tailwind themes, colors, and animation tokens
├── tsconfig.json                   # TypeScript project path aliases & configuration
└── vite.config.ts                  # Vite build tooling configuration
```

---

## 4. Common Development Commands

All commands can be executed using `pnpm` or `npm`:

```bash
# Start local development server (with HMR)
pnpm dev

# Type checking and diagnostics across Svelte and TypeScript
pnpm check

# Production build (outputs static HTML/JS/CSS to build/)
pnpm build

# Preview static production build locally
pnpm preview
```

---

## 5. Coding & Svelte 5 Best Practices

When writing or refactoring code in this repository:

1. **Use Svelte 5 Runes**:
   - Declare reactive state with `let value = $state(...)`.
   - Declare computed values with `let double = $derived(...)`.
   - Never use legacy Svelte 4 syntax (`export let`, `<slot>`, `$: reactive`).
2. **Modern Event Handlers**:
   - Use standard event attributes such as `onclick={...}` and `onkeydown={...}` instead of deprecated `on:click` directives.
3. **Keyed Loops**:
   - Always supply an explicit key expression in `{#each}` blocks: `{#each items as item, index (item.id ?? index)}`.
4. **Accessibility (a11y)**:
   - Provide informative `aria-label` attributes on icon-only buttons.
   - Always include descriptive `alt` attributes on `<img>` tags.
   - Keep interactive handlers on proper interactive elements (`<button>`, `<a>`, or `<svelte:window>`).
5. **Static Site Constraints**:
   - Every page is statically prerendered. Avoid server-only runtime dependencies or dynamic server endpoints.
6. **Path Aliases**:
   - Use `$lib/...` when importing shared components, utilities, or assets.

---

## 6. Svelte MCP Server Guidelines

When working on Svelte or SvelteKit components, adhere to the Svelte MCP server workflows:

### 1. `list-sections`
- Use this **first** to discover all available documentation sections when researching Svelte or SvelteKit topics.

### 2. `get-documentation`
- Retrieves full documentation content for specific sections.
- Fetch relevant sections discovered via `list-sections` to verify syntax or patterns before implementing complex features.

### 3. `svelte-autofixer`
- **Mandatory Validation**: Whenever creating or editing `.svelte` files or Svelte modules, run `svelte-autofixer` before finalizing code.
- Continue iterating until **zero issues and zero suggestions** are returned.

### 4. `playground-link`
- Only generate playground links upon explicit user request.
- **NEVER** call this tool when code has already been written directly to workspace files.
