# lexical-variable-demo [![Built on Blockly](https://tinyurl.com/built-on-blockly)](https://github.com/google/blockly)

A demo of the [Blockly lexical variables plugin](https://github.com/mit-cml/blockly-plugins/tree/main/block-lexical-variables). This project uses Webpack and ES6 modules.

## Prerequisites

- [Node.js](https://nodejs.org/en/download): Install Node.js 18 or newer.
- npm: Installed automatically with Node.js.

Verify your installation:

```powershell
node -v
npm -v
```

## Installation

Clone the repository and open its directory:

```powershell
git clone https://github.com/mit-cml/lexical-variable-demo.git
cd lexical-variable-demo
```

Install dependencies:

```powershell
npm install --legacy-peer-deps
```

The `--legacy-peer-deps` option skips strict peer-dependency conflict checks during installation. This project uses it in its existing setup instructions.

The demo uses `blockly` version `11.2.2` and `@mit-app-inventor/blockly-block-lexical-variables` version `11.0.3`.

## Running the Demo

Start the development server:

```powershell
npm run start
```

Open [http://localhost:8080](http://localhost:8080).

Select blocks from the toolbox, arrange them in the workspace, and click **Generate Code**. The generated code is printed in the browser console.

Press `Ctrl+C` in the terminal to stop the development server.

## Build a Deployable Version

Run:

```powershell
npm run build
```

Webpack generates the production files in the `docs` directory.

## Troubleshooting

### 1. `npm` or `node` is not recognized

- Install Node.js from the [official download page](https://nodejs.org/en/download).
- Close and reopen your shell after installation.
- Verify the installation using `node -v` and `npm -v`.

### 2. Dependency installation fails

If npm reports peer-dependency conflicts, try:

```powershell
npm install --legacy-peer-deps
```

If dependencies appear to be missing, first check that you are in the project directory and that `package.json` exists.

If installation still fails, read the complete npm error before removing files or changing dependency versions.

### 3. Port 8080 is already in use

**Windows (PowerShell):**

Find the process using port 8080:

```powershell
netstat -ano | findstr :8080
```

The last column shows the process ID (PID). Identify the process before stopping it:

```powershell
tasklist /FI "PID eq <PID>"
```

If it is a development server you started, stop it with `Ctrl+C` in its terminal.

**Mac/Linux:**

Find the process using port 8080:

```bash
lsof -i :8080
```

Check the process before stopping it. If it is a development server you started, stop it with `Ctrl+C` in its terminal.

If needed, configure Webpack Dev Server to use another available port.

### 4. `npm run start` fails

- Check that dependency installation completed successfully.
- Run `npm install --legacy-peer-deps` if dependencies are missing.
- Check the terminal for port conflicts or compilation errors.
- Open the browser console to inspect client-side errors.

### 5. `npm run build` fails

- Read the first relevant error in the terminal output.
- Confirm that dependencies are installed.
- Check for missing modules and incompatible package versions.
- Run `npm ls blockly @mit-app-inventor/blockly-block-lexical-variables` to inspect the installed packages.

Webpack may also display asset-size warnings. These warnings do not necessarily mean that the build failed; check whether compilation completed successfully.

## Learn More

- [Blockly](https://developers.google.com/blockly)
- [Webpack](https://webpack.js.org/)
- [Blockly lexical variables plugin](https://github.com/mit-cml/blockly-plugins/tree/main/block-lexical-variables)
