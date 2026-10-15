# tsup-lib-vite-demo-example

A simple example on how to include a demo vite app inside a tsup bundled library and debug it in vscode.

## Run the example

From the repository root:

```sh
npm ci
npm run build
cd demo
npm ci
npm run dev
```

The demo declares the parent library as a local `file:../` dependency. No global
`npm link` step is required. Its Vite configuration aliases that package to the
parent `src` directory, so development serves the TypeScript source directly;
the library build above supplies declarations for TypeScript tooling.

Open the repository root in VS Code and use the checked-in launch configuration
while the demo server is running. This setup does not by itself verify that
breakpoints in the parent library bind in every debugger environment.
