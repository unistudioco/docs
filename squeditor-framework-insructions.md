# ⚡️ Squeditor Framework

**Squeditor Framework** is a high-performance, developer-first framework for building lightning-fast, static websites. It combines the power of **PHP-style templating** with the modern performance of **Tailwind CSS**, the interactivity of **UIKit 3**, and the speed of **Vite**.

> [!IMPORTANT]
> Squeditor Framework is NOT a WordPress theme framework or a CMS. It is a build-time framework that uses PHP for development and outputs 100% flat, portable HTML/CSS/JS for production and compatible with Squeditor, Elementor, Gutenberg, and other page builders.

## 🚀 Key Features

### 🛠 Zero-Runtime PHP Templating
Develop using familiar WordPress-style functions like `get_template_part()` and `get_section()`, use PHP arrays as your data layer, and leverage loops to build complex layouts. The production build "snaps" everything into pure HTML, requiring zero server-side processing.

### 🧩 Selective UIKit 3 Integration
Stop loading massive component libraries. Squeditor Framework uses a **Component Manifest System** (via `uikit-manifest.json`) to tree-shake UIKit. Use only what you need (like a Slider or Modal) and Squeditor Framework will automatically bundle just the necessary SCSS and JS.

### 🎨 Token-Based Styling Architecture
Fully themeable via a centralized Design Token system (`_tokens.scss`). Every component and layout utility consumes CSS Custom Properties (`--sq-*`), allowing you to swap entire visual identities or color schemas (Light/Dark) instantly across the site.

### 🌓 Built-in Light/Dark Mode
Native support for `sq-theme-dark` classes and Tailwind's `dark:` utilities. The framework detects schema settings from the environment (or URL) and applies them globally to the body, ensuring a seamless and premium dark mode experience.

### 📚 Section-Based Workflow
Build pages in minutes using a library of pre-built, token-aware section variants:
- **Hero**: Video, Split, Centered
- **Cards**: Grids, Horizontal, Feature lists
- **CTA**: Split, Banner, In-line
- **Global**: Responsive Header, Deep-linked Footer

### 📖 Automatic Style Guide
Every project includes an automatically generated `style-guide.php` page that renders every active component and its variants, serving as your project's living documentation.

---

## 🏗 Project Architecture

```bash
[workspace-root]/
├── squeditor/              # 🏗 CORE - Framework engine and build scripts
├── project-template/       # 🚀 STARTER - Blank project generator
└── showcase/               # 💎 DEMO - Full-featured example project
```

---

## 🏁 Getting Started

### 1. Installation
Clone the repository to serve as your core workspace root:
```bash
git clone https://github.com/unistudioco/squeditor-workspace.git
cd squeditor-workspace
```

### 2. Scaffold a New Project
Squeditor includes a robust CLI scaffolding tool. It generates a completely clean, minimalist `project-template/` instance next to the core framework, fully pre-configured to utilize the advanced GSAP and UIKit engines without demo bloat.

To scaffold your new project, run the following command from the workspace root:
```bash
node squeditor/scripts/scaffold.js my-awesome-project
```

### 3. Development
Navigate into your newly generated project folder, install its dependencies, and start the development server:
```bash
cd my-awesome-project
npm install
npm run dev
```

> [!CAUTION]
> **Use Port 3001 for Development**
> Vite will show a link to `http://127.0.0.1:5173/` in your terminal. **Do not use that link.**
> Instead, always visit the PHP Server address: **`http://127.0.0.1:3001`**. This is because Squeditor Framework uses PHP for template rendering, and Vite only serves the static assets.

### 4. Build for Production
Generate the static `dist/` folder and a distributable ZIP archive:
```bash
npm run build
```

---

## 🛠 Technology Stack

- **Dev Engine**: PHP 8.2+ (as a templating pre-processor)
- **CSS Architecture**: Tailwind CSS + SCSS (Layered Overrides)
- **JS Interactivity**: UIKit 3 (Selective Component Bundling)
- **Bundler**: Vite 5
- **Static Generation**: Custom Snapshot Engine
- **Deployment**: Integrated Netlify/Vercel support

---

## 🤝 Contributing

We welcome contributions! Whether it's adding new section variants, improving the build pipeline, or refining the token system, feel free to open a PR.

---

## 📄 License

Squeditor Framework is released under the [MIT License](LICENSE).

---

Built with ❤️ by **Expert Developers** for the modern web.
