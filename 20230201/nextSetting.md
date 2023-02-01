next.js 플젝설치

```
yarn create next-app --typescript
```

eslint 설정을 위한 eslintrc 파일 자동으로 만들기

```
yarn create @eslint/config

```

typescript 파서 설정
//.eslintrc.json

```
{
  ...
  "parserOptions": [
    ...
    "project": ["tsconfig.json"]
  ],
  ...
}

nextjs 규칙 추가
//.eslintrc.json
{
  ...
  "extends": [
    ...
    "next/core-web-vitals"
  ],
  ...
}

기타 next와 충돌하는 룰 삭제
//.eslintrc.json
{
  ...
  "rules": [
    "react/react-in-jsx-scope": "off",
    "react/jsx-props-no-spreading": "off"
  ],
  ...
}

airbnb 규칙 설치
npx install-peerdeps --D eslint-config-airbnb eslint-config-airbnb-typescript



airbnb 규칙 추가
//.eslintrc.json
{
  ...
  "extends": [
    ...
    "airbnb",
    "airbnb/hooks",
    "airbnb-typescript"
  ],
  ...
}


``

prettier 설치
eslint-config-prettier: eslint와 prettier가 충돌하지 않도록 eslint의 일부 설정을 덮어써서 없애기
yarn add -D prettier eslint-config-prettier
prettier 규칙 추가
prettier가 eslint와 충돌하지 않도록 규칙을 추가 할 수 있다.
설치만 해도 되지만 아래같은 설정을 하면 prettier에 걸릴 때 lint 오류를 바로 보여준다.
//.eslintrc.json
{
  ...
  "extends": [
    ...
    "prettier"
  ],
  ...
}

prettier 설정
//.prettierrc.json
{
  "singleQuote": false,
  "semi": true,
  "useTabs": false,
  "printWidth": 80
}


vscode 설정
//.vscode/settings.json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
}


최종파일본

```

/.eslintrc.json
{
"env": {
"browser": true,
"es2021": true,
"node": true
},
"extends": [
"eslint:recommended",
"plugin:react/recommended",
"plugin:@typescript-eslint/recommended",
"next/core-web-vitals",
"airbnb",
"airbnb/hooks",
"airbnb-typescript",
"prettier"
],
"overrides": [],
"parser": "@typescript-eslint/parser",
"parserOptions": {
"ecmaVersion": "latest",
"sourceType": "module",
"project": ["tsconfig.json"]
},
"plugins": ["react", "@typescript-eslint"],
"rules": {
"react/react-in-jsx-scope": "off",
"react/jsx-props-no-spreading": "off"
}
}
//package.json
{
"name": "samplePage",
"version": "0.1.0",
"private": true,
"scripts": {
"dev": "next dev",
"build": "next build",
"start": "next start",
"lint": "next lint"
},
"dependencies": {
"eslint-config-prettier": "^8.5.0",
"next": "12.3.0",
"react": "18.2.0",
"react-dom": "18.2.0"
},
"devDependencies": {
"@types/node": "18.7.17",
"@types/react": "18.0.19",
"@types/react-dom": "18.0.6",
"@typescript-eslint/eslint-plugin": "^5.13.0",
"@typescript-eslint/parser": "^5.0.0",
"eslint": "^8.2.0",
"eslint-config-airbnb": "19.0.4",
"eslint-config-airbnb-typescript": "17.0.0",
"eslint-config-next": "12.3.0",
"eslint-plugin-import": "^2.25.3",
"eslint-plugin-jsx-a11y": "^6.5.1",
"eslint-plugin-react": "^7.28.0",
"eslint-plugin-react-hooks": "^4.3.0",
"prettier": "^2.7.1",
"typescript": "4.8.3"
}
}

```

```
