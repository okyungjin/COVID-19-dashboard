# Table of Contents
- [Table of Contents](#table-of-contents)
- [About COVID-19-dashboard](#about-covid-19-dashboard)
- [Dev Notes](#dev-notes)
  - [JavaScript 프로젝트에 TypeScript 적용하기](#javascript-프로젝트에-typescript-적용하기)
    - [1) JSDoc으로 점진적인 타입 적용](#1-jsdoc으로-점진적인-타입-적용)
    - [2) TypeScript 환경 구성](#2-typescript-환경-구성)
# About COVID-19-dashboard
JavaScript로 제작된 **COVID-19 Dashboard**에 TypeScript를 점진적으로 적용해나가는 프로젝트입니다.

**관련 문서**

- [존스 홉킨스 코로나 현황](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6)
- [Postman API](https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#27454960-ea1c-4b91-a0b6-0468bb4e6712)
- [Type Vue without Typescript](https://blog.usejournal.com/type-vue-without-typescript-b2b49210f0b)

# Dev Notes
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
    "target": "ES5", // tsc로 변환할 js version
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


