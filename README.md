# LOCALIZE-TS

[![npm version](https://img.shields.io/npm/v/localize-ts.svg)](https://www.npmjs.com/package/localize-ts)
[![npm downloads](https://img.shields.io/npm/dt/localize-ts)](https://www.npmjs.com/package/localize-ts)

LOCALIZE-TS is a tool used to convert JSON translations into TypeScript definitions. This helps in maintaining type safety and consistency across your localization files.

## Installation

You can install LOCALIZE-TS globally or as a dev dependency in your project.

### Using npm

```sh
npm install -g localize-ts
# or as a dev dependency
npm install --save-dev localize-ts
```

### Using yarn

```sh
yarn global add localize-ts
# or as a dev dependency
yarn add --dev localize-ts
```

### Using pnpm

```sh
pnpm add -g localize-ts
# or as a dev dependency
pnpm add -D localize-ts
```

## Usage Example

### Input JSON (`input.json`)

```json
{
    "title": "LOCALIZE-TS",
    "description": "This is a {{description}} to show how to use {{package}}",
    "greetings": "Welcome {{name}}!"
}
```

### Output TypeScript (`output.ts`)

```ts
// GENERATED BY LOCALIZE-TS

export interface Translations {
 title: string;
 description: { description: string; package: string };
 greetings: { name: string };
}
```

### Command

To generate the TypeScript definitions, run the following command:

```sh
localize-ts -f input.json -o output.ts
```

This will read the `input.json` file and generate the TypeScript definitions in `output.ts`.
