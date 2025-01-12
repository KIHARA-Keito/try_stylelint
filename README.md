# try_stylelint

## work log

1. 事前に github でリポジトリ作成する

2. github での指示通りに以下を実行

```
$ mkdir try_stylelint
$ cd try_stylelint
$ echo "# try_stylelint" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/KIHARA-Keito/try_stylelint.git
$ git push -u origin main
```

3. stylelint インストール・検証など

```
$ npm init --yes
$ npm install -D stylelint-config-standard
$ touch .stylelintrc.json
```

```.stylelintrc.json
{
  "extends": [
    "stylelint-config-standard"
  ],
  "rules": {
    "no-duplicate-selectors": true
  }
}
```

```./src/test.css
body {
  color: aqua;
}

body {
  text-align: left;
}
```

```
$ npx stylelint ./src
```

```.package.json
"scripts": {
  "csslint": "stylelint ./src",
  "csslintfix": "stylelint --fix ./src"
},
```

```
$ npm run csslint
```

4. sass のインストール

```
$ npm i sass
```

```.package.json
"scripts": {
  "sass": "sass ./src/*.scss out/out.css",
},
```

```
$ npm run sass
```

5. stylelint-config-standard-scss, stylelint-config-recess-order のインストール

```
$ npm i -D
```
