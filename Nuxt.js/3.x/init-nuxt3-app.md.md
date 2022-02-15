# Initial Nuxt.js 3 App

> tags: #Nuxt

## environment require

- node v16+
- npm v8.4.1

## install and running

``` shell
npx nuxi init nuxt3-app
```

```shell
cd nuxt3-app
```

``` shell
code nuxt3-app
```

``` shell
yarn install

# or

npm install
```

``` shell
yarn dev -o
```

## Install with nuxt 3

### setting

``` shell
yarn add -D tailwindcss@latest postcss@last autoprefixer@latest
```

``` shell
npx tailwindcss init -p
```

```JavaScript

// setting tailwind.config.js
module.exports = {
  mode: 'jit',
  purge: [
    "./assets/**/*.css",
    "./components/*.{vue,js}",
    "./components/**/*.{vue,js}",
    "./pages/*.vue",
    "./pages/**/*.vue",
    "./plugins/**/*.{js,ts}",
    "./*.{vue,js,ts}",
    "./nuxt.config.{js,ts}"
],
 // ...
}
```

### create file

create `assets/styles/main.css` and input follow as :

``` css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

import to `nuxt.config.ts` :

``` ts
export default defineNuxtConfig({
 css: ['@/assets/styles/main.css'],
 build: {
  postcss: {
    postcssOptions: require('./postcss.config.js'),
  },
 },
});
```

