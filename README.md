Official repository to track issues related to [@fizzog/dish](https://www.npmjs.com/package/@fizzog/dish?activeTab=readme) or @fizzog/create-dish

# [D.I.S.H. - Dynamic Internationalization Scanner and Harvester](https://www.npmjs.com/package/@fizzog/dish?activeTab=readme)

A developer tool for managing localization files. Includes support for scanning and analyzing project usage, detecting orphaned keys, and providing a streamlined process for handling localization files in your project.

Specifically, this project is designed to work with `i18next` and `react-i18next` by tracking usage of `useTranslation` and `t('namespace:key')`.

## Features

- **Localization File Management**: Easily manage and maintain your localization JSON files.
- **Scanning**: Automatically scan your project for localization key usage.
- **Orphan Detection**: Identify orphaned or unused localization keys.
- **Usage Analysis**: Detect missing or unreferenced keys and streamline the translation process.

## Installation

To get started with `@fizzog/dish`, we recommend using `@fizzog/create-dish`, a tool that sets up everything for you with minimal configuration. Follow the steps below.

### Step 1: Install

Run the following command to install and initialize `dish` in your project:

```bash
npm init @fizzog/dish@latest
```

```bash
yarn create @fizzog/dish
```

### Step 2: Run the cli

```bash
npm run dish usage
```

Or leverage the package.json script that is optionally created.

## Supported config options

`dish.config.json`

```json
{
  "out": ".dish",
  "sourceGlob": "./src/**/*.{tsx,jsx}",
  "localeGlob": "./src/locales/**/*.json",
  "analysisFiles": ["used", "unused", "missing", "code"],
  "debug": false
}
```

1. `out` _string_ - The output directory where locale specific files for missing, used, and used data will be created.

1. `sourceGlob` _string_ - The glob expression for finding files that make use of translation code. e.g. `ts`, `tsx`, `js`, `jsx`.

1. `localeGlob` _string | string[]_ - The glob expression for finding files that store translation text. A string or array is valid ```json["**/locales/**/*.json", "**/modules/**/locales/*.json"]```

1. `analysisFiles` _string | string[]_ - What files should be generated when `dish` is run. _options: used, unused, missing, code_

1. `debug` _boolean | string[]_ – Need to troubleshoot? Set debug to true to see detailed logs of each data transformation step. Found something odd? Feel free to open an issue on the DISH repo. If string array, possible values are: ```json["scan", "validate", "index", "compare", "out", "config", "aliases"]```
