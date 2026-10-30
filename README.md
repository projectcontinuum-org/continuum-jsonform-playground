<div align="center">
  <h1>Continuum JSONForms Playground</h1>
  <strong>Try out node dialog schemas and UI for <a href="https://github.com/projectcontinuum-org">Project Continuum</a> in the browser</strong>
</div>

<div align="center">
  <img src="https://img.shields.io/badge/License-Apache_2.0-green" alt="License: Apache 2.0">
  <img src="https://img.shields.io/badge/JSONForms-3.7.0-orange" alt="JSONForms 3.7.0">
  <img src="https://img.shields.io/badge/MUI-5-007fff?logo=mui&logoColor=white" alt="MUI 5">
  <img src="https://img.shields.io/badge/React-18-61dafb?logo=react&logoColor=white" alt="React 18">
  <img src="https://img.shields.io/badge/TypeScript-5-blue?logo=typescript&logoColor=white" alt="TypeScript">
</div>

---

## Part of Project Continuum

Every node in [Project Continuum](https://github.com/projectcontinuum-org) describes its configuration dialog with a JSON schema and a UI schema, rendered by [JSONForms](https://jsonforms.io/) in the [workbench](https://github.com/projectcontinuum-org/continuum-workbench). This playground lets you edit those schemas and see the resulting form immediately, without starting the full platform.

It uses the same JSONForms version and custom renderers as the workbench, so what you see here should match what users see.

## Features

- **Live editor:** edit the data schema, UI schema and data in a Monaco editor and watch the form update.
- **Examples:** built-in Continuum examples plus the upstream JSONForms examples.
- **Custom renderers:** the code editor and credential controls used by node dialogs, with mock credentials.
- **Node catalog (optional):** point it at a running Continuum API server to load the schemas of real nodes through the node-explorer API (`/api/v1/node-explorer/children`).
- **Dialog preview:** open the form in a modal that mimics the workbench node dialog.
- **Light and dark themes.**

## Live playground

The playground is hosted on GitHub Pages at [playground.projectcontinuum.org](https://playground.projectcontinuum.org). Every push to `main` builds and deploys it. The hosted version can only reach an API server that allows cross-origin requests from that site.

## Quick start

You need **Node.js 20 or later**.

```bash
git clone https://github.com/projectcontinuum-org/continuum-jsonform-playground.git
cd continuum-jsonform-playground
npm install
npm run dev
```

Open [http://localhost:4300](http://localhost:4300).

| Command | What it does |
|---|---|
| `npm run dev` | Start the Vite dev server on port 4300 |
| `npm run build` | Type-check and build to `dist/` |
| `npm run preview` | Serve the production build locally |

To load real nodes, start the platform with [continuum-local-setup](https://github.com/projectcontinuum-org/continuum-local-setup) and enter the API server URL in the playground.

## Project layout

```
src/
  App.tsx          Layout, example picker and node catalog
  examples/        Built-in and upstream JSONForms examples
  renderers/       Custom code editor and credential renderers
  components/      Editor, form preview and dialog preview panels
  api/             Node-explorer client
  mock/            Mock credentials
  theme.ts         Light and dark MUI themes
```

## Keeping in sync with the workbench

The playground is only useful if it renders like the workbench. When the workbench changes its JSONForms or MUI versions, or its custom renderers, update `package.json` and `src/renderers/` here to match. Installs use `legacy-peer-deps` (see `.npmrc`) because JSONForms Material renderers have peer dependency ranges that overlap with MUI 5.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) and the organization's [Code of Conduct](https://github.com/projectcontinuum-org/.github/blob/main/CODE_OF_CONDUCT.md).

## License

[Apache 2.0](LICENSE)
