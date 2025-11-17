# Copilot Instructions for React + Vite Practice Project

## Project Overview
This is a minimal React 19 practice project using Vite as the build tool. It follows a Single Page Application (SPA) architecture where all content is dynamically rendered via JavaScript/React.

## Architecture & Key Files

### Entry Points
- **`index.html`** — Root HTML file with a `<div id="root">` mounting point
- **`src/main.jsx`** — Vite entry point that mounts the React app using `createRoot()`
- **`src/App.jsx`** — Root React component; start here for UI logic

### Build & Development Setup
- **Vite** (v7.2.2) for bundling and dev server with HMR (Hot Module Replacement)
- **React 19** with Babel transpilation via `@vitejs/plugin-react`
- No TypeScript — JavaScript/JSX only
- Configuration in `vite.config.js` (minimal setup, no customization needed)

## Development Workflow

### Common Commands
```bash
npm run dev      # Start dev server with HMR (http://localhost:5173 by default)
npm run build    # Build for production to /dist
npm run lint     # Run ESLint on all .js and .jsx files
npm run preview  # Preview production build locally
```

### Code Structure
- **`src/`** — All source code (components, styles, assets)
  - Components as `.jsx` files (e.g., `App.jsx`)
  - Stylesheets as `.css` files (e.g., `App.css`, `index.css`)
  - Static assets in `assets/` folder
- **`public/`** — Static files copied as-is to dist root during build
- **`dist/`** — Production output (gitignored)

## Conventions & Rules

### ESLint Configuration
Defined in `eslint.config.js` with flat config format:
- **Standard plugins:** ESLint recommended rules + React Hooks rules + React Refresh rules
- **Custom rule:** `no-unused-vars` allows PascalCase variables (component names)
- **Ignored:** `/dist` directory
- Run linter frequently: unused variables must be removed or properly ignored

### Component & Naming Patterns
- React components are `.jsx` files with PascalCase names (e.g., `App.jsx`)
- Use functional components (class components avoided)
- `StrictMode` wrapper in `main.jsx` for development warnings

### Styling
- CSS modules or plain CSS files alongside components (no CSS-in-JS library configured)
- Link stylesheets in the component file, e.g., `import './App.css'`
- Global styles in `index.css` (imported in `main.jsx`)

## Integration Points & External Dependencies

### React Ecosystem
- **React 19** + React DOM — UI rendering
- **React Hooks** — state management (hooks linting enabled via ESLint)
- **React Refresh** — fast refresh for HMR during development

### No Additional State Management
This is a learning project with minimal dependencies. Use React hooks (`useState`, `useContext`, etc.) for state. If complex state is needed, consider Redux/Zustand (not yet integrated).

### No Compiler Optimization
The React Compiler is intentionally disabled (see README) due to performance impact on dev/build. Enable only for production-critical applications.

## Development Notes
- HMR is active — component changes reflect instantly without full page reload
- TypeScript not enabled — add `typescript-eslint` if moving to TS (see README)
- No authentication, routing, or backend integration currently configured
- Practice project — feel free to add features and experiment with React patterns
