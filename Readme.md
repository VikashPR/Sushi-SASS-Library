# Documentation for the project

## Introduction

This is a custom build SASS framework for the project.

## Prerequisites

- [Node.js](https://nodejs.org/en/)
- [Gulp](https://gulpjs.com/)

### Gulp Installation

```bash
npm i gulp gulp-sass sass --save-dev
```

### GulpFile.js

```javascript
const { src, dest, watch, series } = require("gulp");
const sass = require("gulp-sass")(require("sass"));

function buildStyles() {
  return src("index.scss").pipe(sass()).pipe(dest("css"));
}

function watchTask() {
  watch(["index.scss"], buildStyles);
}

exports.default = series(buildStyles, watchTask);
```

## Usage

```bash
npx gulp
```
