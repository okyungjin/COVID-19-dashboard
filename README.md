# 🏷 Table of Contents
- [🏷 Table of Contents](#-table-of-contents)
- [🙌 About COVID-19-dashboard](#-about-covid-19-dashboard)
- [📕 Dev Notes](#-dev-notes)
  - [JavaScript 프로젝트에 TypeScript 적용하기](#javascript-프로젝트에-typescript-적용하기)
    - [1) JSDoc으로 점진적인 타입 적용](#1-jsdoc으로-점진적인-타입-적용)
    - [2) TypeScript 환경 구성](#2-typescript-환경-구성)
    - [3) 명시적인 any 선언하기](#3-명시적인-any-선언하기)
    - [4) 프로젝트 환경 구성](#4-프로젝트-환경-구성)
    - [5) 외부 라이브러리 모듈화](#5-외부-라이브러리-모듈화)
  - [Arrow Function](#arrow-function)
  - [DOM 함수 타입 오류 해결하기](#dom-함수-타입-오류-해결하기)
  - [devDependencies에 추가한 라이브러리](#devdependencies에-추가한-라이브러리)
    - [Babel](#babel)
    - [ESLint](#eslint)
    - [Prettier](#prettier)
- [🔫 Troubleshooting](#-troubleshooting)
  - [TypeScript에서 Promise를 사용할 때 발생하는 오류](#typescript에서-promise를-사용할-때-발생하는-오류)
  - [외부 라이브러리 import 시에 발생하는 오류](#외부-라이브러리-import-시에-발생하는-오류)
    - [[CASE #1] 타입 정의 라이브러리 설치](#case-1-타입-정의-라이브러리-설치)
    - [[CASE #2] 타입 선언 라이브러리가 제공되지 않는 외부 라이브러리 사용](#case-2-타입-선언-라이브러리가-제공되지-않는-외부-라이브러리-사용)
      - [1) `typeRoots` 에 경로 지정](#1-typeroots-에-경로-지정)
      - [2) `index.d.ts` 생성](#2-indexdts-생성)
# 🙌 About COVID-19-dashboard
JavaScript로 제작된 **COVID-19 Dashboard**에 TypeScript를 점진적으로 적용해나가는 프로젝트입니다.

**관련 문서**

- [존스 홉킨스 코로나 현황](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6)
- [Postman API](https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#27454960-ea1c-4b91-a0b6-0468bb4e6712)
- [Type Vue without Typescript](https://blog.usejournal.com/type-vue-without-typescript-b2b49210f0b)

# 📕 Dev Notes
## JavaScript 프로젝트에 TypeScript 적용하기
JSDoc을 사용하여 점진적인 타입 시스템을 도입하는 방법이 있지만, 사용법이 불편하여 비용이 많이 든다.
### 1) JSDoc으로 점진적인 타입 적용
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

### 2) TypeScript 환경 구성
**2-1. init npm & TypeScript 라이브러리 설치**

```bash
npm init -y
npm i -D typescript
```

**2-2. TypeScript 설정 파일 생성 및 기본값 추가**

`tsconfig.json` 추가
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

- `"allowJs": true` 프로젝트에 js 파일 사용 가능하도록 설정
- `"target": "ES5"` tsc로 변환할 js의 버전을 ES5로 설정
- `"outDir": "./built"` 결과물이 담길 디렉토리를 `./built` 로 지정
- `"moduleResolution": "Node"` Promise base로 구현할 수 있도록 Node 기반으로 설정
- `"include": ["./src/*]` 해당 프로젝트에 어떤 파일들을 tsc로 변환할 것인지 설정, `src` 디렉토리 이하의 모든 폴더의 파일(`./**/*`을 대상으로 하겠다.

**2-3. JavaScript 파일을 TypeScript로 변환**
`app.js` 를 `app.ts` 로 변환

**2-4. `tsc` 명령어로 TypeScript 변환 수행**

`package.json` 에 `build` script 추가
```diff
"scripts": {
   "test": "echo \"Error: no test specified\" && exit 1",
+  "build": "tsc" 
},
```
### 3) 명시적인 any 선언하기
`tsconfig.json` 의 `noImplicitAny` 속성을 `true` 로 설정한다.
가능하면 구체적으로 타입을 정의한다.

```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc로 변환할 js version
    "outDir": "./built",
    "moduleResolution": "Node",
    "lib": ["ES2015", "DOM", "DOM.Iterable"],
+   "noImplicitAny": true
  },
  "include": ["./src/**/*"]
}
```
### 4) 프로젝트 환경 구성
- Babel, ESLint, Prettier 환경 설정

### 5) 외부 라이브러리 모듈화


## Arrow Function

**Arrow Function in JavaScript**

```js
// ES5 - 함수 선언문
function sum(a, b) {
  return a + b;
}

// ES5 - 함수 표현식
var sum = function(a, b) {
  return a + b;
}

// ES6+ - 함수 표현식 (화살표 함수)
var sum = (a, b) => {
  return a + b;
};

var sum = (a, b) => a + b;
```

<br>

**Arrow Function in TypeScript**

```ts
// 화살표 함수 + TypeScript
var sum = (a: number, b: number): number => {
  return a + b;
};

var sum = (a: number, b: number): number => a + b;
```

## DOM 함수 타입 오류 해결하기
DOM 함수의 반환 값에 `innerHTML` 을 접근하니 다음과 같은 오류가 발생했다.

> any
> Property 'innerText' does not exist on type 'Element'.ts(2339)

<img width="700" alt="innerHTML does not exist" src="https://user-images.githubusercontent.com/31913666/169526577-6c011964-9cdb-46fc-bd40-d0036e02ab9a.png">

해당 이슈가 발생하는 원인은 TypeScript가 `document.querySelector()` 의 반환값을 `Element` 타입으로 추론했기 때문이다.

```ts
function $(selector: string) {
  return document.querySelector(selector);
}
```

VSCode를 이용하여 `Element` 의 인터페이스로 이동해보면 `innerHTML` 속성이 없는 것을 확인할 수 있다. 즉, `Element` 타입에서 없는 속성에 접근하려니 오류가 발생하는 것이다.

`deathsTotal` 변수의 querySelector 인자인  `.deaths` 를 index.html에서 찾아보면 `<p>` 태그인 것을 확인할 수 있다.

```html
<p class="total deaths">0</p>
```

따라서 오류를 해결하기 위해서는 TypeScript에게 타입 단언으로 타입 명시를 해주어야 한다.

`HTMLParagraphElement` 타입으로 단언해주면 오류가 사라진다.

```ts
// p tag
const deathsTotal = $('.deaths') as HTMLParagraphElement;

// 참고로 span tag는 다음과 같이 명시해준다.
const confirmedTotal = $('.confirmed-total') as HTMLSpanElement;
```
## devDependencies에 추가한 라이브러리
### Babel

```json
"@babel/core": "^7.18.0",
"@babel/preset-env": "^7.18.0",
"@babel/preset-typescript": "^7.17.12",
```
최신 JavaScript 문법을 브라우저에서 호환 가능한 하위 버전으로 변경해주는 **JavaScript 컴파일러**이다. JavaScript 소스를 JavaScript로 변환해준다는 의미에서 `transcompiler` 라고도 한다.
(컴파일, 트랜스파일, 트랜스컴파일 용어가 혼용되어 사용됨)

`@babel/preset-env` 라이브러리에 `preset` 이라는 용어가 보이는데, 이는 **plugin의 집합**을 말한다.

### ESLint

```json
"@typescript-eslint/eslint-plugin": "^5.25.0",
"@typescript-eslint/parser": "^5.25.0",
"eslint": "^8.15.0",
"eslint-plugin-prettier": "^4.0.0",
```

JavaScript 소스를 작성할 때 오류가 날 것 같은 구문들에 대한 힌트를 주는 보조 도구이며, 문법 힌트 외에도 포맷팅의 기능도 있다.

`.eslintrc.js` 파일에 옵션을 수정하여 ESLint 설정을 커스텀할 수 있다.

> **TSLint를 사용하지 않고 ESLint를 사용하는 이유**
> 
> ESLint가 TSLint 보다 성능이 좋아서, TypeScript를 만든 회사인 Microsoft가 TSLint를 deprecate하고 ESLint에 contribute하는 방향으로 진행하겠다고 밝혔다. 따라서 ESLint에 TypeScript에 대한 설정을 추가하는 방식으로 사용된다.


### Prettier

```json
"prettier": "^2.6.2",
```

Prettier를 코드 포맷팅 규칙을 커스텀할 수 있다.
팀 단위로 코딩 컨벤션을 정의하여 적용하는 경우가 많고, 컨벤션 유무에 따라 가독성에 큰 차이가 있으니 가급적 사용하는 것을 추천한다.

Prettier의 설정이 `.eslintrc.js` 파일의 `rules` 에 위치하고 있는데, 이는 `eslint-plugin-prettier` 가 설치되어 있기 때문이다. ESLint 설정 파일에서 Prettier 옵션을 인식할 수 있도록 도와주는 라이브러리이다.

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

# 🔫 Troubleshooting
## TypeScript에서 Promise를 사용할 때 발생하는 오류

`app.ts` 에서 async를 사용하는 `handleListClick` 함수에 hover를 해보면 다음과 같은 오류 메세지를 확인할 수 있다.

> An async function or method in ES5/ES3 requires the 'Promise' constructor.  Make sure you have a declaration for the 'Promise' constructor or include 'ES2015' in your '--lib' option.ts(2705)

`package.json` 에서 `"lib": ["ES2015"]` 속성을 추가해주면 해결된다.

프로젝트에서 TypeScript로 DOM 조작을 하는 부분이 있으므로, `"DOM", "DOM.Iterable"` 도 미리 추가해두면 좋다.

```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc로 변환할 js version
    "outDir": "./built",
    "moduleResolution": "Node",
+   "lib": ["ES2015", "DOM", "DOM.Iterable"]
  },
  "include": ["./src/**/*"]
}
```

## 외부 라이브러리 import 시에 발생하는 오류


> **❗️주의**
> 
> 강의 시점에는 chart.js를 설치하면 `types` 디렉토리가 없는데 실습 시점에는 포함되어 있어서 같은 오류는 발생하지 않았다. 하지만, 프로젝트를 진행하면서 해당 유형의 이슈가 발생할 수도 있으므로, import 시에 타입 오류가 발생한다고 가정하여 README를 작성하였다.


`npm i chart.js` 명령어를 이용해 라이브러리를 설치 후, `app.ts` 에서 정상적으로 import를 해주었으나 오류가 발생한다.

(But, axios는 동일하게 import를 해도 오류가 발생하지 않는다.)

<img width="700" alt="chartjs-import-error" src="https://user-images.githubusercontent.com/31913666/169651298-eeddac69-ad4c-4d5c-bdb7-1657fd5b5e46.png">

이는 `index.d.ts` 파일이 누락되어 발생하는 오류이다. TypeScript는 모듈을 해석할 때 `index.d.ts` 파일을 참고하기 때문이다.

> **왜 이런 방식으로 되어있는가?**
> 
> 모듈 생성 시점에는 JavaScript로 만들어졌다가, TypeScript 생태계가 커지면서 이에 대응하기 위해 `index.d.ts` 파일을 추가하게 되었기 때문이다. **즉, 외부 JavaScript 라이브러리를 TypeScript가 사용할 수 있도록 타입을 지정해준 파일**이 `index.d.ts` 이다.

이를 해결하는 방법에는 2가지가 있다.
- 타입을 정의해둔 라이브러리를 설치
- 구현체의 타입을 정의한 라이브러리가 없다면 `index.d.ts` 를 직접 작성

### [CASE #1] 타입 정의 라이브러리 설치

오류 메세지에 안내된 [@types/chart.js](https://www.npmjs.com/package/@types/chart.js)를 들어가보면 chart.js의 구현체에 대한 타입이 정의되어 있는 것을 확인할 수 있다.

`npm i @types/chart.js` 로 설치하면 `@types/chart.js` 가 설치된다.

<img width="272" alt="type-chartjs" src="https://user-images.githubusercontent.com/31913666/169656501-5a8c2242-8219-4aa3-802a-f2a289bb80d8.png">

<br>

import 부분을 확인해보면 `from 'chart.js'` 부분의 오류가 사라진 것을 확인할 수 있다.
But, `import Chart` 에 다른 오류가 발생하고 있다.

<img width="700" alt="import-chart-error" src="https://user-images.githubusercontent.com/31913666/169656590-226cab56-5dd7-410a-9d2c-a024dc2354ce.png">

<br>

해당 이슈는 import 방식을 다음과 같이 변경하면 해결된다.

```ts
import * as Chart from 'chart.js';
```

> `import * as Chart` **를 사용해야 하는 이유**
> 
> CommomJS로 만들어진 라이브러리를 ES6 module codebase에서 import 하기 위해서는 `* as Chart` 와 같ㅇ은 방식을 사용해야 한다.
> 관련 [stack overflow 링크](https://stackoverflow.com/questions/56238356/understanding-esmoduleinterop-in-tsconfig-file) 참고

### [CASE #2] 타입 선언 라이브러리가 제공되지 않는 외부 라이브러리 사용
사용하려는 라이브러리에 대한 타입 선언 라이브러리가 존재하지 않는다면 다음과 같은 방법으로 해결할 수 있다.

#### 1) `typeRoots` 에 경로 지정

`tsconfig.json` 에 `typeRoots` 을 추가한다. TypeScript는 타입 정의를 가져오기 위해 `./node_modules/@types` 경로 먼저 살펴본다. (`./node_modules/@types` 경로가 기본 값)

여기에 내가 직접 지정할 타입을 저장할 디렉토리인 `types` 도 추가해준다.


```diff
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5", // tsc로 변환할 js version
    "outDir": "./built",
    "moduleResolution": "Node",
    "lib": ["ES2015", "DOM", "DOM.Iterable"],
    "noImplicitAny": true,
+   "typeRoots": ["./node_modules/@types", "types"]
  },
  "include": ["./src/**/*"]
}
```

#### 2) `index.d.ts` 생성

루트 디렉토리에 `types` 디렉토리가 없다면 생성하고, 하위에 `chart.js/index.d.ts` 파일을 생성한다.

**`index.d.ts` 파일은 TypeScript의 타입 정의만 해놓은 파일**이다.