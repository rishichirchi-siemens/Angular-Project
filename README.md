# Angular Project

This repository contains notes and quick-start instructions for creating, running, and maintaining an Angular application.

This README is a friendly guide for Windows (PowerShell) users and covers the most common developer workflows: creating a new app, running it locally, building for production, testing, and simple deployment tips.

## Prerequisites

- Node.js (LTS) and npm - install from https://nodejs.org/
- Git (optional, for source control)

Check versions in PowerShell:

```powershell
node --version
npm --version
git --version  # optional
```

## Install Angular CLI

Install the Angular CLI globally so you can use the `ng` command:

```powershell
npm install -g @angular/cli
```

If you cannot install globally, you can use `npx @angular/cli new <project-name>` instead.

## Create a new Angular project

Create a new project (replace `<project-name>` with your app name):

```powershell
ng new <project-name>
cd <project-name>
```

Common options you may want to pass to `ng new`:

- `--routing` to add the router
- `--style=scss` (or `css`, `less`, `sass`) to choose stylesheet format
- `--skip-git` to avoid initializing a git repo

## Run the development server

Run the app locally with live reload:

```powershell
npm start        # or
ng serve --open  # opens default browser
```

The app will usually be available at http://localhost:4200/.

## Build for production

Create an optimized production build:

```powershell
ng build --configuration production
# or shorthand
ng build --prod
```

Built files will be in the `dist/<project-name>/` folder. Serve them using your static file host or a simple server (see Deploying section).

## Test and Lint

Run unit tests:

```powershell
ng test
```

Run end-to-end tests (if configured):

```powershell
ng e2e
```

Run the linter:

```powershell
ng lint
```

## Serve the production build locally (quick check)

Install a tiny static server and serve the `dist` output (example using `npx`):

```powershell
npx http-server ./dist/<project-name> -p 8080
# then open http://localhost:8080
```

Or use `npx serve`:

```powershell
npx serve -s ./dist/<project-name>
```

## Project structure (typical)

- `src/app/` — application source (components, services, modules)
- `src/assets/` — static assets
- `src/environments/` — environment-specific config
- `angular.json` — Angular CLI workspace settings
- `package.json` — npm scripts and dependencies

## Recommended editor & extensions

- Visual Studio Code
- Extensions: Angular Language Service, ESLint, Prettier

## Troubleshooting

- If `ng` is not recognized after installing CLI globally, restart your shell or ensure npm global bin is on PATH:

```powershell
# Show npm global bin path
npm bin -g
# Add it to PATH if necessary (example):
$env:Path += ";C:\Users\<you>\AppData\Roaming\npm"
```

- If you get permission errors installing globally on Windows, avoid `-g` and use `npx @angular/cli` or run PowerShell as Administrator.

- If the dev server port 4200 is busy, change it:

```powershell
ng serve --port 4300
```

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Commit changes and open a pull request describing the change.

Follow the project's code style and add tests for new features where appropriate.

## License

Add your preferred license here (e.g., MIT) or keep the repository's default licensing.

---

If you want, I can also:
- generate a sample Angular app inside this workspace,
- add a recommended `.gitignore`, or
- create a minimal `package.json` and scripts tailored to the project.

Tell me which of those you'd like next.