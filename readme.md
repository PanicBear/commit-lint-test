## Git 커밋 메시지 lint 설정 방법

- @commitlint/cli, @commitlint/config-conventional 설치
  ```bash
  npm install @commitlint/{cli,config-conventional} --save-dev
  ```
- .commitlintrc.json 파일 생성
  ```bash
  {
    "extends": ["@commitlint/config-conventional"]
  }
  ```
- commitlint.config.js 파일 생성
  ```bash
  module.exports = {
    extends: ['@commitlint/config-conventional'],
  };
  ```
- husky 설치 및 git hook 활성화
  ```bash
  npm install husky --save-dev
  npx husky install
  ```
- commit-msg hook 추가
  ```bash
  npx husky add .husky/commit-msg 'npx commitlint --edit $1'
  ```
