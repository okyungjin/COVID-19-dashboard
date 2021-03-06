# ๐ท Table of Contents
- [๐ท Table of Contents](#-table-of-contents)
- [๐ About COVID-19-dashboard](#-about-covid-19-dashboard)
- [๐ Dev Notes](#-dev-notes)
  - [JavaScript ํ๋ก์ ํธ์ TypeScript ์ ์ฉํ๊ธฐ](#javascript-ํ๋ก์ ํธ์-typescript-์ ์ฉํ๊ธฐ)
    - [1) JSDoc์ผ๋ก ์ ์ง์ ์ธ ํ์ ์ ์ฉ](#1-jsdoc์ผ๋ก-์ ์ง์ ์ธ-ํ์-์ ์ฉ)
    - [2) TypeScript ํ๊ฒฝ ๊ตฌ์ฑ](#2-typescript-ํ๊ฒฝ-๊ตฌ์ฑ)
    - [3) ๋ช์์ ์ธ any ์ ์ธํ๊ธฐ](#3-๋ช์์ ์ธ-any-์ ์ธํ๊ธฐ)
    - [4) ํ๋ก์ ํธ ํ๊ฒฝ ๊ตฌ์ฑ](#4-ํ๋ก์ ํธ-ํ๊ฒฝ-๊ตฌ์ฑ)
    - [5) ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ๋ชจ๋ํ](#5-์ธ๋ถ-๋ผ์ด๋ธ๋ฌ๋ฆฌ-๋ชจ๋ํ)
    - [6) `strict` ์ต์ ์ถ๊ฐ ๋ฐ ํ์ ์ ์](#6-strict-์ต์-์ถ๊ฐ-๋ฐ-ํ์-์ ์)
  - [Arrow Function](#arrow-function)
  - [DOM ํจ์ ํ์ ์ค๋ฅ ํด๊ฒฐํ๊ธฐ](#dom-ํจ์-ํ์-์ค๋ฅ-ํด๊ฒฐํ๊ธฐ)
  - [devDependencies์ ์ถ๊ฐํ ๋ผ์ด๋ธ๋ฌ๋ฆฌ](#devdependencies์-์ถ๊ฐํ-๋ผ์ด๋ธ๋ฌ๋ฆฌ)
    - [Babel](#babel)
    - [ESLint](#eslint)
    - [Prettier](#prettier)
  - [axios fetch ํจ์์ ํ์ ์ ์ํ๊ธฐ](#axios-fetch-ํจ์์-ํ์-์ ์ํ๊ธฐ)
    - [1) interface ์ ์](#1-interface-์ ์)
    - [2) sub interface ์ ์](#2-sub-interface-์ ์)
    - [3) fetch ํจ์ ๋ฐํ ํ์ ์ ์](#3-fetch-ํจ์-๋ฐํ-ํ์-์ ์)
  - [Optional Chaining](#optional-chaining)
  - [DOM แแฒแแตแฏ แแกแทแแฎ แแชแฏแแญแผแแฅแผแแณแฏ แแฉแแแตแแณแซ แแกแแตแธ แแฅแผแแด](#dom-แแฒแแตแฏ-แแกแทแแฎ-แแชแฏแแญแผแแฅแผแแณแฏ-แแฉแแแตแแณแซ-แแกแแตแธ-แแฅแผแแด)
- [๐ซ Troubleshooting](#-troubleshooting)
  - [TypeScript์์ Promise๋ฅผ ์ฌ์ฉํ  ๋ ๋ฐ์ํ๋ ์ค๋ฅ](#typescript์์-promise๋ฅผ-์ฌ์ฉํ -๋-๋ฐ์ํ๋-์ค๋ฅ)
  - [์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ import ์์ ๋ฐ์ํ๋ ์ค๋ฅ](#์ธ๋ถ-๋ผ์ด๋ธ๋ฌ๋ฆฌ-import-์์-๋ฐ์ํ๋-์ค๋ฅ)
    - [[CASE #1] ํ์ ์ ์ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ค์น](#case-1-ํ์-์ ์-๋ผ์ด๋ธ๋ฌ๋ฆฌ-์ค์น)
    - [[CASE #2] ํ์ ์ ์ธ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ ์ ๊ณต๋์ง ์๋ ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ฌ์ฉ](#case-2-ํ์-์ ์ธ-๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ-์ ๊ณต๋์ง-์๋-์ธ๋ถ-๋ผ์ด๋ธ๋ฌ๋ฆฌ-์ฌ์ฉ)
      - [1) `typeRoots` ์ ๊ฒฝ๋ก ์ง์ ](#1-typeroots-์-๊ฒฝ๋ก-์ง์ )
      - [2) `index.d.ts` ์์ฑ](#2-indexdts-์์ฑ)
  - [Uncaught SyntaxError: Unexpected token 'export'](#uncaught-syntaxerror-unexpected-token-export)
  - [No overload matches this call.](#no-overload-matches-this-call)
# ๐ About COVID-19-dashboard
JavaScript๋ก ์ ์๋ **COVID-19 Dashboard**์ TypeScript๋ฅผ ์ ์ง์ ์ผ๋ก ์ ์ฉํด๋๊ฐ๋ ํ๋ก์ ํธ์๋๋ค.

**๊ด๋ จ ๋ฌธ์**

- [์กด์ค ํํจ์ค ์ฝ๋ก๋ ํํฉ](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6)
- [Postman API](https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#27454960-ea1c-4b91-a0b6-0468bb4e6712)
- [Type Vue without Typescript](https://blog.usejournal.com/type-vue-without-typescript-b2b49210f0b)

# ๐ Dev Notes
## JavaScript ํ๋ก์ ํธ์ TypeScript ์ ์ฉํ๊ธฐ
JSDoc์ ์ฌ์ฉํ์ฌ ์ ์ง์ ์ธ ํ์ ์์คํ์ ๋์ํ๋ ๋ฐฉ๋ฒ์ด ์์ง๋ง, ์ฌ์ฉ๋ฒ์ด ๋ถํธํ์ฌ ๋น์ฉ์ด ๋ง์ด ๋ ๋ค.
### 1) JSDoc์ผ๋ก ์ ์ง์ ์ธ ํ์ ์ ์ฉ
```js
/**
 * @typedef {object} CovidSummary
 * @property {Array<object>} Country
 * @returns
 */

/**
 * @returns {Promise<CovidSummary>}
 */
function fetchCovidSummary() {
  const url = 'https://api.covid19api.com/summary';
  return axios.get(url);
}
```

### 2) TypeScript ํ๊ฒฝ ๊ตฌ์ฑ
**2-1. init npm & TypeScript ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ค์น**

```bash
npm init -y
npm i -D typescript
```

**2-2. TypeScript ์ค์  ํ์ผ ์์ฑ ๋ฐ ๊ธฐ๋ณธ๊ฐ ์ถ๊ฐ**

`tsconfig.json` ์ถ๊ฐ
```json
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5",
    "outDir": "./built",
    "moduleResolution": "Node"
  },
  "include": ["./src/**/*"]
}
```

- `"allowJs": true` ํ๋ก์ ํธ์ js ํ์ผ ์ฌ์ฉ ๊ฐ๋ฅํ๋๋ก ์ค์ 
- `"target": "ES5"` tsc๋ก ๋ณํํ  js์ ๋ฒ์ ์ ES5๋ก ์ค์ 
- `"outDir": "./built"` ๊ฒฐ๊ณผ๋ฌผ์ด ๋ด๊ธธ ๋๋ ํ ๋ฆฌ๋ฅผ `./built` ๋ก ์ง์ 
- `"moduleResolution": "Node"` Promise base๋ก ๊ตฌํํ  ์ ์๋๋ก Node ๊ธฐ๋ฐ์ผ๋ก ์ค์ 
- `"include": ["./src/*]` ํด๋น ํ๋ก์ ํธ์ ์ด๋ค ํ์ผ๋ค์ tsc๋ก ๋ณํํ  ๊ฒ์ธ์ง ์ค์ , `src` ๋๋ ํ ๋ฆฌ ์ดํ์ ๋ชจ๋  ํด๋์ ํ์ผ(`./**/*`์ ๋์์ผ๋ก ํ๊ฒ ๋ค.

**2-3. JavaScript ํ์ผ์ TypeScript๋ก ๋ณํ**
`app.js` ๋ฅผ `app.ts` ๋ก ๋ณํ

**2-4. `tsc` ๋ช๋ น์ด๋ก TypeScript ๋ณํ ์ํ**

`package.json` ์ `build` script ์ถ๊ฐ
```diff
"scripts": {
   "test": "echo \"Error: no test specified\" && exit 1",
+  "build": "tsc" 
},
```
### 3) ๋ช์์ ์ธ any ์ ์ธํ๊ธฐ
`tsconfig.json` ์ `noImplicitAny` ์์ฑ์ `true` ๋ก ์ค์ ํ๋ค.
๊ฐ๋ฅํ๋ฉด ๊ตฌ์ฒด์ ์ผ๋ก ํ์์ ์ ์ํ๋ค.

```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc๋ก ๋ณํํ  js version
    "outDir": "./built",
    "moduleResolution": "Node",
    "lib": ["ES2015", "DOM", "DOM.Iterable"],
+   "noImplicitAny": true
  },
  "include": ["./src/**/*"]
}
```
### 4) ํ๋ก์ ํธ ํ๊ฒฝ ๊ตฌ์ฑ
- Babel, ESLint, Prettier ํ๊ฒฝ ์ค์ 

### 5) ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ๋ชจ๋ํ


### 6) `strict` ์ต์ ์ถ๊ฐ ๋ฐ ํ์ ์ ์

`tsconfig.json` ์์ `strict` ์ต์์ `true` ๋ก ์ค์ ํ๋ค.

```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc๋ก ๋ณํํ  js version
    "outDir": "./built",
    "module": "ES2015",
    "moduleResolution": "Node",
    "lib": ["ES2015", "DOM", "DOM.Iterable"],
    "noImplicitAny": true,
    "typeRoots": ["./node_modules/@types", "types"],
+   "strict": true,
  },
  "include": ["./src/**/*"]
}
```

> `strict` ์ต์์ `true` ๋ก ์ค์ ํ๋ฉด ์ถํ์ ์ผ์ด๋  ์ ์๋ ํ์ ์ค๋ฅ๋ฅผ ๋ฏธ๋ฆฌ ํด๊ฒฐํ  ์ ์๋ค.

`"strict": true` ๋ก ์ค์ ํ๋ ๊ฒ์ ์๋ ์ต์๋ค์ ์ค์ ํ๋ ๊ฒ๊ณผ ๊ฐ์ ์๋ฏธ์ด๋ค.

```json
{
  "strictNullChecks": true,
  "strictFunctionTypes": true,
  "strictBindCallApply": true,
  "strictPropertyInitialization": true,
  "noImplicitAny": true,
  "alwaysStrict": true,
}
```

์ค์ ์ ์ ์ฉํ๋ฉด ๊ธฐ์กด์ ๋ฐ์ํ์ง ์๋ ํ์ ์๋ฌ๊ฐ ๋ฐ์ํ๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.

<img width="690" alt="activate-strict-option" src="https://user-images.githubusercontent.com/31913666/172038383-fa09d45c-f135-4cf7-b01f-c2652b0889fe.png">


## Arrow Function

**Arrow Function in JavaScript**

```js
// ES5 - ํจ์ ์ ์ธ๋ฌธ
function sum(a, b) {
  return a + b;
}

// ES5 - ํจ์ ํํ์
var sum = function(a, b) {
  return a + b;
}

// ES6+ - ํจ์ ํํ์ (ํ์ดํ ํจ์)
var sum = (a, b) => {
  return a + b;
};

var sum = (a, b) => a + b;
```

<br>

**Arrow Function in TypeScript**

```ts
// ํ์ดํ ํจ์ + TypeScript
var sum = (a: number, b: number): number => {
  return a + b;
};

var sum = (a: number, b: number): number => a + b;
```

## DOM ํจ์ ํ์ ์ค๋ฅ ํด๊ฒฐํ๊ธฐ
DOM ํจ์์ ๋ฐํ ๊ฐ์ `innerHTML` ์ ์ ๊ทผํ๋ ๋ค์๊ณผ ๊ฐ์ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค.

> any
> Property 'innerText' does not exist on type 'Element'.ts(2339)

<img width="700" alt="innerHTML does not exist" src="https://user-images.githubusercontent.com/31913666/169526577-6c011964-9cdb-46fc-bd40-d0036e02ab9a.png">

ํด๋น ์ด์๊ฐ ๋ฐ์ํ๋ ์์ธ์ TypeScript๊ฐ `document.querySelector()` ์ ๋ฐํ๊ฐ์ `Element` ํ์์ผ๋ก ์ถ๋ก ํ๊ธฐ ๋๋ฌธ์ด๋ค.

```ts
function $(selector: string) {
  return document.querySelector(selector);
}
```

VSCode๋ฅผ ์ด์ฉํ์ฌ `Element` ์ ์ธํฐํ์ด์ค๋ก ์ด๋ํด๋ณด๋ฉด `innerHTML` ์์ฑ์ด ์๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค. ์ฆ, `Element` ํ์์์ ์๋ ์์ฑ์ ์ ๊ทผํ๋ ค๋ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ ๊ฒ์ด๋ค.

`deathsTotal` ๋ณ์์ querySelector ์ธ์์ธ  `.deaths` ๋ฅผ index.html์์ ์ฐพ์๋ณด๋ฉด `<p>` ํ๊ทธ์ธ ๊ฒ์ ํ์ธํ  ์ ์๋ค.

```html
<p class="total deaths">0</p>
```

๋ฐ๋ผ์ ์ค๋ฅ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด์๋ TypeScript์๊ฒ ํ์ ๋จ์ธ์ผ๋ก ํ์ ๋ช์๋ฅผ ํด์ฃผ์ด์ผ ํ๋ค.

`HTMLParagraphElement` ํ์์ผ๋ก ๋จ์ธํด์ฃผ๋ฉด ์ค๋ฅ๊ฐ ์ฌ๋ผ์ง๋ค.

```ts
// p tag
const deathsTotal = $('.deaths') as HTMLParagraphElement;

// ์ฐธ๊ณ ๋ก span tag๋ ๋ค์๊ณผ ๊ฐ์ด ๋ช์ํด์ค๋ค.
const confirmedTotal = $('.confirmed-total') as HTMLSpanElement;
```
## devDependencies์ ์ถ๊ฐํ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
### Babel

```json
"@babel/core": "^7.18.0",
"@babel/preset-env": "^7.18.0",
"@babel/preset-typescript": "^7.17.12",
```
์ต์  JavaScript ๋ฌธ๋ฒ์ ๋ธ๋ผ์ฐ์ ์์ ํธํ ๊ฐ๋ฅํ ํ์ ๋ฒ์ ์ผ๋ก ๋ณ๊ฒฝํด์ฃผ๋ **JavaScript ์ปดํ์ผ๋ฌ**์ด๋ค. JavaScript ์์ค๋ฅผ JavaScript๋ก ๋ณํํด์ค๋ค๋ ์๋ฏธ์์ `transcompiler` ๋ผ๊ณ ๋ ํ๋ค.
(์ปดํ์ผ, ํธ๋์คํ์ผ, ํธ๋์ค์ปดํ์ผ ์ฉ์ด๊ฐ ํผ์ฉ๋์ด ์ฌ์ฉ๋จ)

`@babel/preset-env` ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ `preset` ์ด๋ผ๋ ์ฉ์ด๊ฐ ๋ณด์ด๋๋ฐ, ์ด๋ **plugin์ ์งํฉ**์ ๋งํ๋ค.

### ESLint

```json
"@typescript-eslint/eslint-plugin": "^5.25.0",
"@typescript-eslint/parser": "^5.25.0",
"eslint": "^8.15.0",
"eslint-plugin-prettier": "^4.0.0",
```

JavaScript ์์ค๋ฅผ ์์ฑํ  ๋ ์ค๋ฅ๊ฐ ๋  ๊ฒ ๊ฐ์ ๊ตฌ๋ฌธ๋ค์ ๋ํ ํํธ๋ฅผ ์ฃผ๋ ๋ณด์กฐ ๋๊ตฌ์ด๋ฉฐ, ๋ฌธ๋ฒ ํํธ ์ธ์๋ ํฌ๋งทํ์ ๊ธฐ๋ฅ๋ ์๋ค.

`.eslintrc.js` ํ์ผ์ ์ต์์ ์์ ํ์ฌ ESLint ์ค์ ์ ์ปค์คํํ  ์ ์๋ค.

> **TSLint๋ฅผ ์ฌ์ฉํ์ง ์๊ณ  ESLint๋ฅผ ์ฌ์ฉํ๋ ์ด์ **
> 
> ESLint๊ฐ TSLint ๋ณด๋ค ์ฑ๋ฅ์ด ์ข์์, TypeScript๋ฅผ ๋ง๋  ํ์ฌ์ธ Microsoft๊ฐ TSLint๋ฅผ deprecateํ๊ณ  ESLint์ contributeํ๋ ๋ฐฉํฅ์ผ๋ก ์งํํ๊ฒ ๋ค๊ณ  ๋ฐํ๋ค. ๋ฐ๋ผ์ ESLint์ TypeScript์ ๋ํ ์ค์ ์ ์ถ๊ฐํ๋ ๋ฐฉ์์ผ๋ก ์ฌ์ฉ๋๋ค.


### Prettier

```json
"prettier": "^2.6.2",
```

Prettier๋ฅผ ์ฝ๋ ํฌ๋งทํ ๊ท์น์ ์ปค์คํํ  ์ ์๋ค.
ํ ๋จ์๋ก ์ฝ๋ฉ ์ปจ๋ฒค์์ ์ ์ํ์ฌ ์ ์ฉํ๋ ๊ฒฝ์ฐ๊ฐ ๋ง๊ณ , ์ปจ๋ฒค์ ์ ๋ฌด์ ๋ฐ๋ผ ๊ฐ๋์ฑ์ ํฐ ์ฐจ์ด๊ฐ ์์ผ๋ ๊ฐ๊ธ์  ์ฌ์ฉํ๋ ๊ฒ์ ์ถ์ฒํ๋ค.

Prettier์ ์ค์ ์ด `.eslintrc.js` ํ์ผ์ `rules` ์ ์์นํ๊ณ  ์๋๋ฐ, ์ด๋ `eslint-plugin-prettier` ๊ฐ ์ค์น๋์ด ์๊ธฐ ๋๋ฌธ์ด๋ค. ESLint ์ค์  ํ์ผ์์ Prettier ์ต์์ ์ธ์ํ  ์ ์๋๋ก ๋์์ฃผ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ด๋ค.

```js
{
  rules: {
    'prettier/prettier': [
      'error',
      {
        singleQuote: true,
        semi: true,
        useTabs: false,
        tabWidth: 2,
        printWidth: 80,
        bracketSpacing: true,
        arrowParens: 'avoid',
      },
    ],
  },
}
```

<br>

## axios fetch ํจ์์ ํ์ ์ ์ํ๊ธฐ
axios๋ก ๋ฐ์ดํฐ๋ฅผ fetchํ๋ ํจ์์ธ `fetchCovidSummary()` ์ ๋ฐํ ํ์์ ์ ์ํด๋ณด์.

```ts
function fetchCovidSummary() {
  const url = 'https://api.covid19api.com/summary';
  return axios.get(url);
}
```

### 1) interface ์ ์
chrome devtools์ network ํญ์ด๋ API spec์ ํ์ธํ์ฌ interface๋ฅผ ์์ฑํ๋ค.

object์ ๊ฒฝ์ฐ ์ฐ์  `any` ๋ก ์ ์ํ ํ ํ์ฅํ๋๋ก ํ๋ค.

```ts
export interface CovidSummaryResponse {
  Countries: any[];
  Date: string;
  Global: any;
  Message: string;
}
```

<br>

### 2) sub interface ์ ์
object ํํ์ธ `Countries` ์ `Global` ์ ํ์์ ์ ์ํด์ค๋ค.

```ts
export interface Country {
  Country: string;
  CountryCode: string;
  Date: string;
  ID: string;
  NewConfirmed: number;
  NewDeaths: number;
  NewRecovered: number;
  Premium: any;
  Slug: string;
  TotalConfirmed: number;
  TotalDeaths: number;
  TotalRecovered: number;
}

export interface Global {
  Date: string;
  NewConfirmed: number;
  NewDeaths: number;
  NewRecovered: number;
  TotalConfirmed: number;
  TotalDeaths: number;
  TotalRecovered: number;
}
```

์ด์  ๋จ๊ณ์์ `any` ๋ก ์ค์ ํด๋ `CovidSummaryResponse` ์ ํ์์ ๊ตฌ์ฒดํํด์ค๋ค.
```ts
export interface CovidSummaryResponse {
  Countries: Country[];
  Date: string;
  Global: Global;
  Message: string;
}
```

<br>

### 3) fetch ํจ์ ๋ฐํ ํ์ ์ ์
`axios` ์ ๋ฐํ ๊ฐ์ ํ์์ `Promise<AxiosResponse<T>>` ์ด๋ฏ๋ก ํ์์ ๋ค์๊ณผ ๊ฐ์ด ์ ์ํ๋ค.

```ts
import { AxiosResponse } from 'axios';
import { CovidSummaryResponse } from './model/covid';

function fetchCovidSummary(): Promise<AxiosResponse<CovidSummaryResponse>> {
  const url = 'https://api.covid19api.com/summary';
  return axios.get(url);
}
```

> ์ด๋ ๊ฒ ์ ์ํด์ฃผ๋ฉด ์ ๊ทผํ  ์ ์๋ property์ ์๋ ์์ฑ์ด ์ง์๋๋ค. ๐

![fetchCovidSummary](https://user-images.githubusercontent.com/31913666/171782124-8bf9b4af-e7d5-410f-9d73-20ab60816ec5.png)


<br>

## Optional Chaining

Optional Chaining์ ์ฌ์ฉํ๋ฉด ๊ฐ๊ฒฐํ ๋ฌธ๋ฒ์ผ๋ก null ํน์ undefined ๊ฐ์ ์ฒดํฌํ  ์ ์๋ค.

```ts
recoveredList?.appendChild(li);

// Optional Chaining์ ํ์ด์ ์ฐ๋ฉด ๋ค์๊ณผ ๊ฐ๋ค.
if (recoveredList === null || recoveredList === undefined) {
  return;
} else {
  recoveredList.appendChild(li);
}
```

<br>

## DOM แแฒแแตแฏ แแกแทแแฎ แแชแฏแแญแผแแฅแผแแณแฏ แแฉแแแตแแณแซ แแกแแตแธ แแฅแผแแด

```ts
function $(selector: string) {
  return document.querySelector(selector);
}
```

DOM ์ ํธ ํจ์์ธ `$` ํจ์์ ๋ฐํ ํ์์ด `Element | null` ์ด๊ธฐ ๋๋ฌธ์ ํ์ ๋จ์ธ์ผ๋ก ์ธํด ์์ค๊ฐ ๋ณต์กํด์ง๊ณ  ์๋ค.

```ts
const confirmedTotal = $('.confirmed-total') as HTMLSpanElement;
const deathsTotal = $('.deaths') as HTMLParagraphElement;
const recoveredTotal = $('.recovered') as HTMLParagraphElement;
const lastUpdatedTime = $('.last-updated-time') as HTMLParagraphElement;
const rankList = $('.rank-list') as HTMLOListElement;
const deathsList = $('.deaths-list') as HTMLOListElement;
const recoveredList = $('.recovered-list') as HTMLOListElement;
```

DOM ์ ํธ ํจ์์ ํ์ ์ ์๋ฅผ ํตํด ์์ค๋ฅผ ๊น๋ํ๊ฒ ์์ฑํด๋ณด์.

<br>

```ts
function $<T extends HTMLElement>(selector: string) {
  return document.querySelector(selector);
}
```

`$` ์ ์ ๋ค๋ฆญ ํ์์ผ๋ก `<T extends HTMLElement>` ๋ฅผ ๋ฐ์ผ๋ฉด `HTMLElement` ์ ํธํ๋๋, ์ฆ `HTMLElement` ์ ํ์ ํ์๋ง ์ ๋ค๋ฆญ ํ์์ผ๋ก ์ ์ธํ  ์ ์๊ฒ ๋๋ค.


`HTMLElement` ํ์ ํ์ ์ด์ธ์ ํ์์ผ๋ก ์ ์ํ๋ฉด ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค.
```ts
// ๋ค์๊ณผ ๊ฐ์ด ์ฌ์ฉํ๋ฉด ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค.
const deathsTotal = $<string>('.deaths')
```

`$` ์์ ๋ฐ์ ์ ๋ค๋ฆญ ํ์์ ์ฌ์ฉํ๋ฉด ์๋์ ๊ฐ์ด ์ ์ํ  ์ ์๋ค.

```ts
function $<T extends HTMLElement>(selector: string) {
  const element = document.querySelector(selector);
  return element as T;
}
```

ํ์ ๋จ์ธ์ ์ฌ์ฉํ์ง ์๊ณ  ์ ๋ค๋ฆญ์ผ๋ก ์กฐ๊ธ ๋ ๊น๋ํ๊ฒ ์์ค๋ฅผ ์์ฑํ  ์ ์๊ฒ ๋๋ค.
```ts
const confirmedTotal = $<HTMLSpanElement>('.confirmed-total');
const deathsTotal = $<HTMLParagraphElement>('.deaths');
const recoveredTotal = $<HTMLParagraphElement>('.recovered');
const lastUpdatedTime = $<HTMLParagraphElement>('.last-updated-time');
const rankList = $<HTMLOListElement>('.rank-list');
const deathsList = $<HTMLOListElement>('.deaths-list');
const recoveredList = $<HTMLOListElement>('.recovered-list');
```

> โ๏ธ ์ฃผ์
> `$` ์ ์ธ์๋ก ๋ฃ๋ `selector` ๋ฌธ์์ด์ ์คํ๊ฐ ์๊ฑฐ๋ ์กด์ฌํ์ง ์๋ element์ ์ ๊ทผํ๋ ค๊ณ  ํ๋ฉด ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค. ๋ณธ ํ๋ก์ ํธ์์๋ js๋ก ํ์ดํ ๋ ์์ค๋ฅผ ts๋ก ๋ง์ด๊ทธ๋ ์ด์ ํ๋ ๊ฒ์ ๋ชฉ์ ์ผ๋ก ํ๊ณ  ์์ผ๋ฏ๋ก `element as T` ๋ก ์ค์ ํ์๋ค. ์ค๋ฌด์์๋ ์ด์ ๋ํ ๋์์ด ํ์ํ๋ค.


# ๐ซ Troubleshooting
## TypeScript์์ Promise๋ฅผ ์ฌ์ฉํ  ๋ ๋ฐ์ํ๋ ์ค๋ฅ

`app.ts` ์์ async๋ฅผ ์ฌ์ฉํ๋ `handleListClick` ํจ์์ hover๋ฅผ ํด๋ณด๋ฉด ๋ค์๊ณผ ๊ฐ์ ์ค๋ฅ ๋ฉ์ธ์ง๋ฅผ ํ์ธํ  ์ ์๋ค.

> An async function or method in ES5/ES3 requires the 'Promise' constructor.  Make sure you have a declaration for the 'Promise' constructor or include 'ES2015' in your '--lib' option.ts(2705)

`package.json` ์์ `"lib": ["ES2015"]` ์์ฑ์ ์ถ๊ฐํด์ฃผ๋ฉด ํด๊ฒฐ๋๋ค.

ํ๋ก์ ํธ์์ TypeScript๋ก DOM ์กฐ์์ ํ๋ ๋ถ๋ถ์ด ์์ผ๋ฏ๋ก, `"DOM", "DOM.Iterable"` ๋ ๋ฏธ๋ฆฌ ์ถ๊ฐํด๋๋ฉด ์ข๋ค.

```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc๋ก ๋ณํํ  js version
    "outDir": "./built",
    "moduleResolution": "Node",
+   "lib": ["ES2015", "DOM", "DOM.Iterable"]
  },
  "include": ["./src/**/*"]
}
```

## ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ import ์์ ๋ฐ์ํ๋ ์ค๋ฅ


> **โ๏ธ์ฃผ์**
> 
> ๊ฐ์ ์์ ์๋ chart.js๋ฅผ ์ค์นํ๋ฉด `types` ๋๋ ํ ๋ฆฌ๊ฐ ์๋๋ฐ ์ค์ต ์์ ์๋ ํฌํจ๋์ด ์์ด์ ๊ฐ์ ์ค๋ฅ๋ ๋ฐ์ํ์ง ์์๋ค. ํ์ง๋ง, ํ๋ก์ ํธ๋ฅผ ์งํํ๋ฉด์ ํด๋น ์ ํ์ ์ด์๊ฐ ๋ฐ์ํ  ์๋ ์์ผ๋ฏ๋ก, import ์์ ํ์ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค๊ณ  ๊ฐ์ ํ์ฌ README๋ฅผ ์์ฑํ์๋ค.


`npm i chart.js` ๋ช๋ น์ด๋ฅผ ์ด์ฉํด ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ค์น ํ, `app.ts` ์์ ์ ์์ ์ผ๋ก import๋ฅผ ํด์ฃผ์์ผ๋ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค.

(But, axios๋ ๋์ผํ๊ฒ import๋ฅผ ํด๋ ์ค๋ฅ๊ฐ ๋ฐ์ํ์ง ์๋๋ค.)

<img width="700" alt="chartjs-import-error" src="https://user-images.githubusercontent.com/31913666/169651298-eeddac69-ad4c-4d5c-bdb7-1657fd5b5e46.png">

์ด๋ `index.d.ts` ํ์ผ์ด ๋๋ฝ๋์ด ๋ฐ์ํ๋ ์ค๋ฅ์ด๋ค. TypeScript๋ ๋ชจ๋์ ํด์ํ  ๋ `index.d.ts` ํ์ผ์ ์ฐธ๊ณ ํ๊ธฐ ๋๋ฌธ์ด๋ค.

> **์ ์ด๋ฐ ๋ฐฉ์์ผ๋ก ๋์ด์๋๊ฐ?**
> 
> ๋ชจ๋ ์์ฑ ์์ ์๋ JavaScript๋ก ๋ง๋ค์ด์ก๋ค๊ฐ, TypeScript ์ํ๊ณ๊ฐ ์ปค์ง๋ฉด์ ์ด์ ๋์ํ๊ธฐ ์ํด `index.d.ts` ํ์ผ์ ์ถ๊ฐํ๊ฒ ๋์๊ธฐ ๋๋ฌธ์ด๋ค. **์ฆ, ์ธ๋ถ JavaScript ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ TypeScript๊ฐ ์ฌ์ฉํ  ์ ์๋๋ก ํ์์ ์ง์ ํด์ค ํ์ผ**์ด `index.d.ts` ์ด๋ค.

์ด๋ฅผ ํด๊ฒฐํ๋ ๋ฐฉ๋ฒ์๋ 2๊ฐ์ง๊ฐ ์๋ค.
- ํ์์ ์ ์ํด๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ค์น
- ๊ตฌํ์ฒด์ ํ์์ ์ ์ํ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ ์๋ค๋ฉด `index.d.ts` ๋ฅผ ์ง์  ์์ฑ

### [CASE #1] ํ์ ์ ์ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ค์น

์ค๋ฅ ๋ฉ์ธ์ง์ ์๋ด๋ [@types/chart.js](https://www.npmjs.com/package/@types/chart.js)๋ฅผ ๋ค์ด๊ฐ๋ณด๋ฉด chart.js์ ๊ตฌํ์ฒด์ ๋ํ ํ์์ด ์ ์๋์ด ์๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.

`npm i @types/chart.js` ๋ก ์ค์นํ๋ฉด `@types/chart.js` ๊ฐ ์ค์น๋๋ค.

<img width="272" alt="type-chartjs" src="https://user-images.githubusercontent.com/31913666/169656501-5a8c2242-8219-4aa3-802a-f2a289bb80d8.png">

<br>

import ๋ถ๋ถ์ ํ์ธํด๋ณด๋ฉด `from 'chart.js'` ๋ถ๋ถ์ ์ค๋ฅ๊ฐ ์ฌ๋ผ์ง ๊ฒ์ ํ์ธํ  ์ ์๋ค.
But, `import Chart` ์ ๋ค๋ฅธ ์ค๋ฅ๊ฐ ๋ฐ์ํ๊ณ  ์๋ค.

<img width="700" alt="import-chart-error" src="https://user-images.githubusercontent.com/31913666/169656590-226cab56-5dd7-410a-9d2c-a024dc2354ce.png">

<br>

ํด๋น ์ด์๋ import ๋ฐฉ์์ ๋ค์๊ณผ ๊ฐ์ด ๋ณ๊ฒฝํ๋ฉด ํด๊ฒฐ๋๋ค.

```ts
import * as Chart from 'chart.js';
```

> `import * as Chart` **๋ฅผ ์ฌ์ฉํด์ผ ํ๋ ์ด์ **
> 
> CommomJS๋ก ๋ง๋ค์ด์ง ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ES6 module codebase์์ import ํ๊ธฐ ์ํด์๋ `* as Chart` ์ ๊ฐ์ ๋ฐฉ์์ ์ฌ์ฉํด์ผ ํ๋ค.
> ๊ด๋ จ [stack overflow ๋งํฌ](https://stackoverflow.com/questions/56238356/understanding-esmoduleinterop-in-tsconfig-file) ์ฐธ๊ณ 

### [CASE #2] ํ์ ์ ์ธ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ ์ ๊ณต๋์ง ์๋ ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ฌ์ฉ
์ฌ์ฉํ๋ ค๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ ๋ํ ํ์ ์ ์ธ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ ์กด์ฌํ์ง ์๋๋ค๋ฉด ๋ค์๊ณผ ๊ฐ์ ๋ฐฉ๋ฒ์ผ๋ก ํด๊ฒฐํ  ์ ์๋ค.

#### 1) `typeRoots` ์ ๊ฒฝ๋ก ์ง์ 

`tsconfig.json` ์ `typeRoots` ์ ์ถ๊ฐํ๋ค. TypeScript๋ ํ์ ์ ์๋ฅผ ๊ฐ์ ธ์ค๊ธฐ ์ํด `./node_modules/@types` ๊ฒฝ๋ก ๋จผ์  ์ดํด๋ณธ๋ค. (`./node_modules/@types` ๊ฒฝ๋ก๊ฐ ๊ธฐ๋ณธ ๊ฐ)

์ฌ๊ธฐ์ ๋ด๊ฐ ์ง์  ์ง์ ํ  ํ์์ ์ ์ฅํ  ๋๋ ํ ๋ฆฌ์ธ `types` ๋ ์ถ๊ฐํด์ค๋ค.


```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc๋ก ๋ณํํ  js version
    "outDir": "./built",
    "moduleResolution": "Node",
    "lib": ["ES2015", "DOM", "DOM.Iterable"],
    "noImplicitAny": true,
+   "typeRoots": ["./node_modules/@types", "types"]
  },
  "include": ["./src/**/*"]
}
```

#### 2) `index.d.ts` ์์ฑ

๋ฃจํธ ๋๋ ํ ๋ฆฌ์ `types` ๋๋ ํ ๋ฆฌ๊ฐ ์๋ค๋ฉด ์์ฑํ๊ณ , ํ์์ `chart.js/index.d.ts` ํ์ผ์ ์์ฑํ๋ค.

**`index.d.ts` ํ์ผ์ TypeScript์ ํ์ ์ ์๋ง ํด๋์ ํ์ผ**์ด๋ค.

```ts
declare module 'chart.js' {
  // ...
  // interface ...
}
```

`app.ts` ์ import ๋ถ๋ถ์์ `chart.js` ์ ๊ฒฝ๋ก๋ฅผ ํ์ธํด๋ณด๋ฉด ์ง์  ์ ์ธํ module๋ก ์กํ๋ ๊ฒ์ ๋ณผ ์ ์๋ค. ์ด๋ `typeRoots` ์ `types` ๋ฅผ ์ถ๊ฐํด์ฃผ์๊ธฐ ๋๋ฌธ์ ์ธ์์ด ๊ฐ๋ฅํ ๊ฒ์ด๋ค.

<img width="345" alt="declare-moudle" src="https://user-images.githubusercontent.com/31913666/171395501-94d0cfeb-efc4-44b5-acce-fa0408b56fc7.png">


## Uncaught SyntaxError: Unexpected token 'export'
html์ด ์ดํดํ  ์ ์๋๋ก tsc๋ก ์ปดํ์ผ๋ `/built/app.js` ๋ก path๋ฅผ ๋ณ๊ฒฝํด์ฃผ์๋๋ ๋ค์๊ณผ ๊ฐ์ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค.

> Uncaught SyntaxError: Unexpected token 'export' (at app.js:261:1)

์ด๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด์๋ ๋ค์ 2๊ฐ์ง ์ฌํญ์ ์์ ํ๋ฉด ๋๋ค.
1. html์์ ES Module์ ์ฌ์ฉํ์ฌ script๋ฅผ ๋ถ๋ฌ์ค๊ธฐ ์ํด์๋ `type="module"` ์ ์ถ๊ฐํด์ฃผ์ด์ผ ํ๋ค.
  
```diff
<body>
- <script src="./built/app.js"></script>
+ <script type="module" src="./built/app.js"></script>
</body>
```

2. `tsconfig.json` ์ `"module": "ES2015"` ์์ฑ์ ์ถ๊ฐํ๋ค.
```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc๋ก ๋ณํํ  js version
    "outDir": "./built",
+   "module": "ES2015",
    "moduleResolution": "Node",
    "lib": ["ES2015", "DOM", "DOM.Iterable"],
    "noImplicitAny": true,
    "typeRoots": ["./node_modules/@types", "types"],
  },
  "include": ["./src/**/*"]
}
```

## No overload matches this call.

tsconfig์ `strict` ์ต์์ `true` ๋ก ์ค์ ํ๊ณ  ๋ฐ์ํ๋ ์๋ฌ๋ค์ ์์ ํ๋ ๊ณผ์ ์์ `initEvents()` ์์ ๋ค์๊ณผ ๊ฐ์ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค.

```ts
function initEvents() {
  rankList.addEventListener('click', handleListClick);
}
```

```bash
No overload matches this call.
  Overload 1 of 2, '(type: keyof ElementEventMap, listener: (this: Element, ev: Event) => any, options?: boolean | AddEventListenerOptions | undefined): void', gave the following error.
    Argument of type '"click"' is not assignable to parameter of type 'keyof ElementEventMap'.
  Overload 2 of 2, '(type: string, listener: EventListenerOrEventListenerObject, options?: boolean | AddEventListenerOptions | undefined): void', gave the following error.
    Argument of type '(event: MouseEvent) => Promise<void>' is not assignable to parameter of type 'EventListenerOrEventListenerObject'.
      Type '(event: MouseEvent) => Promise<void>' is not assignable to type 'EventListener'.
        Types of parameters 'event' and 'evt' are incompatible.
          Type 'Event' is missing the following properties from type 'MouseEvent': altKey, button, buttons, clientX, and 21 more.ts(2769)
```

<br>

`addEventListener` ์ ๋ ๋ฒ์งธ ์ธ์์ ๋ค์ด์์ผ ํ๋ ํ์๊ณผ `handleListClick` ์ ํ์์ด ์ผ์นํ์ง ์๊ธฐ ๋๋ฌธ์ ๋ฐ์ํ๋ ์ค๋ฅ์ด๋ค.

> tsconfig.json์์ `"strict": true` ์ต์์ ์ค์ ํจ์ผ๋ก์ `"strictFunctionTypes": true` ๊ฐ ์ ์ฉ๋์ด ๋ฐ์)

`event` ์ ํ์์ `MouseEvent` ์์ `Event` ๋ก ๋ณ๊ฒฝํด์ฃผ๋ฉด ์ค๋ฅ๊ฐ ํด๊ฒฐ๋๋ค.

```ts
async function handleListClick(event: Event) {
  // ์๋ต
}
```