# LanceDB

A JavaScript / Node.js library for [LanceDB](https://github.com/lancedb/lancedb).

## Installation

```bash
npm install vectordb
```

This will download the appropriate native library for your platform. We currently
support x86_64 Linux, Intel MacOS, and ARM (M1/M2) MacOS.

## Usage

### Basic Example

```javascript
const lancedb = require('vectordb');
const db = lancedb.connect('<PATH_TO_LANCEDB_DATASET>');
const table = await db.openTable('my_table');
const query = await table.search([0.1, 0.3]).setLimit(20).execute();
console.log(results);
```

The [examples](./examples) folder contains complete examples.

## Development

Build and install the rust library with:

```bash
npm run build
npm run pack-build
npm install --no-save ./dist/vectordb-*.tgz
```

The LanceDB javascript is built with npm:

```bash
npm run tsc
```

Run the tests with

```bash
npm test
```

To run the linter and have it automatically fix all errors

```bash
npm run lint -- --fix
```