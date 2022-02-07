# With Nuxt.js 3
## setting
``` shell
yarn add -D tailwindcss@latest postcss@last autoprefixer@latest
```

``` shell
npx tailwindcss init -p
```

``` js
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

## create file
create `assets/styles/main.css` and input follow as : 

``` css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

setting and import to `nuxt.config.ts` :

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