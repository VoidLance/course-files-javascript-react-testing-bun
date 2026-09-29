# JavaScript, React, and Bun Course Files

Small, runnable examples for experimenting with React applications, Bun's
development server, API routes, and Phaser game integration.

## Projects

| Directory | Description |
| --- | --- |
| [`Test Website`](./Test%20Website) | A TypeScript React app served by Bun. It includes a simple production-jobs UI and an API tester for the example routes. |
| [`testphasergame`](./testphasergame) | A JavaScript React + Phaser 3 game template bundled with Vite. It demonstrates communication between React and Phaser scenes. |

## Why use these examples?

- Learn a minimal Bun + React application with server-side API routes.
- Try `GET` and `PUT` requests against a local endpoint from the browser.
- Experiment with React state, event handlers, and a small job dashboard.
- Build Phaser scenes while controlling game state from React.
- Use hot reloading during development and production builds when ready to deploy.

## Getting started

### Prerequisites

- [Bun](https://bun.com/) 1.3 or newer for `Test Website`.
- [Node.js](https://nodejs.org/) and npm, or Bun, for `testphasergame`.

Clone the repository, then run each project from its own directory. Dependencies
are intentionally kept separate because the projects use different toolchains.

### Test Website

```bash
cd "Test Website"
bun install
bun dev
```

Open the local URL printed by Bun. The application displays the job dashboard.
The API tester can call the bundled routes:

```text
GET /api/hello
PUT /api/hello
GET /api/hello/Ada
```

To create a production bundle and run the production server:

```bash
bun run build
bun start
```

The server implementation is in [`src/index.ts`](./Test%20Website/src/index.ts).
Add React UI in [`src`](./Test%20Website/src) and add or update Bun routes in
that file.

### Phaser React game

```bash
cd testphasergame
npm install
npm run dev
```

Open the development URL shown by Vite. The page provides controls for
switching scenes, moving the logo, reading its position, and adding animated
sprites.

Create a deployable build with:

```bash
npm run build
```

The output is written to `testphasergame/dist`. The equivalent Bun commands
(`bun install`, `bun run dev`, and `bun run build`) also work.

## Project layout

```text
.
├── Test Website/
│   └── src/
│       ├── index.ts       # Bun server and API routes
│       ├── App.tsx        # React application entry component
│       └── CreateJob.tsx  # Example job dashboard
└── testphasergame/
    ├── src/PhaserGame.jsx # React-to-Phaser bridge
    ├── src/game/          # Phaser configuration and scenes
    └── public/assets/     # Game assets
```

The Phaser bridge exposes the game and active scene through a React ref.
`src/game/EventBus.js` provides the event channel used to notify React when a
scene is ready.

## Help and documentation

- Read the project-specific notes in [`Test Website/README.md`](./Test%20Website/README.md)
  and [`testphasergame/README.md`](./testphasergame/README.md).
- See the [Bun documentation](https://bun.com/docs), [React documentation](https://react.dev/),
  [Vite documentation](https://vite.dev/), and [Phaser documentation](https://docs.phaser.io/).
- For a reproducible bug or question, [open an issue](https://github.com/VoidLance/course-files-javascript-react-testing-bun/issues)
  with the project directory, command, and error output.

## Contributing and maintenance

The repository is maintained by [VoidLance](https://github.com/VoidLance).
Contributions are welcome:

1. Create a focused branch from the current default branch.
2. Keep changes limited to the relevant example and update its documentation
   when behavior or commands change.
3. Run the affected development or build command before opening a pull request.
4. Describe what changed and include reproduction steps or screenshots when
   useful.

The Phaser example includes its license in [`testphasergame/LICENSE`](./testphasergame/LICENSE).
