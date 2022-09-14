from [YT](https://www.youtube.com/playlist?list=PLYSZyzpwBEWTBdbfStjqJSGaulqcHoNkT) tutorial by Bruno Antunes

### Setup next app

npx create-next-app . --ts

create src folder. move pages

### Setup ts-jest

npm install --save-dev jest typescript ts-jest @types/jest jest-environment-jsdom

npx ts-jest config:init

add "test":"jest" in `package.json`

### Setup react-testing-library

npm install --save-dev @testing-library/react @testing-library/user-event @testing-library/dom @testing-library/jest-dom

create `tsconfig.json`

update `jest.config.ts`:

create `jest.setup.ts` inside src

### set up eslint

npx eslint --init

npm install --save-dev eslint-plugin-testing-library eslint-plugin-jest

update the `.eslintrc.js` by adding "next" and "next/core-web-vitals" and update plugins

update lint in package.json to be next lint --dir src

npm i eslint-plugin-jest

### lint stage and prettier

npx mrm@2 lint-staged - this will set up lint-staged with husky
npm i -D lint-staged prettier

change `.husky/pre-commit` to

```
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

exec >/dev/tty 2>&1

npm run lint-staged
```

update `package.json` script
update `package.json` lint stage to

```
  "lint-staged": {
    "*.(tsx|ts)": "eslint --cache --fix",
    "*": "prettier --write --ignore-unknown"
  }
```

### Git Continuous Integration

[follow this link](https://youtu.be/7uKVFD_VMT8?list=PLYSZyzpwBEWTBdbfStjqJSGaulqcHoNkT&t=1701)
remove the 14 node version in the action script
