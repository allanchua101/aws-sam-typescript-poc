# How to Setup TypeScript Pipelines for SAM-based Lambdas

This guide's purpose is to provide guidance on how to configure an efficient TypeScript development pipeline.

## Pre-requisites

You will need the following software installed in your machine to ease work related to TypeScript based lambdas.

- NVM - Used for switching to NodeJS version 14
- NodeJS version 14 - We'll need NodeJS version 14 and above to support TypeScript
- AWS SAM CLI Version 1.40.1
- TypeScript

### 1. Use NodeJS version 14

Make sure that you are using NodeJS version 14.

```sh
# You can ignore this step if you have installed
# your NodeJS version 14 without using NVM.
nvm use 14
```

### 2. Initialize SAM project

There are four ways to enable ESBUILD feature but I find it most convenient to setup an environment variable (`SAM_CLI_BETA_ESBUILD=1`) among the four options.
We have to scaffold a SAM project using AWS Quick Start templates, you can achieve this by running:

```sh
SAM_CLI_BETA_ESBUILD=1 sam init
```

then pick the following options:

- 1 -> AWS Quick Start Templates
- 1 -> Hello World Example
- N -> Refuse the selection of Python template
- 8 -> nodejs14.x
- 1 -> Zip
- 2 -> Hello World Example TypeScript
- Retain project name to sam-app (Feel free to change it to your desires)

### 3. Install Dependencies of Projects

```sh
cd ./sam-app/hello-world
npm i
```

### 4. Run unit tests

```sh
npm run test
```
