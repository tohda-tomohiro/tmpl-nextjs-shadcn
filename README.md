## 概要
create-next-app をベースにして、すぐに shadcn/ui が使えるようにしたテンプレートです。  
tailwindcss のサポート設定を追加しています。  
UIは画面に「Template」と表示されるだけのシンプルな構成です。

<img src="https://github.com/tohda-tomohiro/tmpl-nextjs-shadcn/assets/154492181/a850d927-0f87-4fc8-b194-87bb5a6d78a3" width="800"/>

## 使い方
bun を利用しています。
https://bun.sh/

```bash
# テンプレートからNext.jsプロジェクトを作成
bunx create-next-app -e https://github.com/tohda/template-nextjs-shadcn

# ローカルサーバー起動
bun run dev
```

`-e, --example [github-url]`：指定したURLのリポジトリをテンプレートにします。

[options](https://nextjs.org/docs/pages/api-reference/create-next-app#options)

## テンプレートの内容

```
bunx create-next-app@latest
```

<img src="https://github.com/tohda/template-nextjs-shadcn/assets/16369289/81b0fa3c-a40a-40e2-a560-04e710642c56" width="600">

### shadcn/ui を初期化済

```
bunx shadcn-ui@latest init
```

* style: Default
* color: Zinc
* CSS variables for colors: yes

### 拡張機能「Prettier - Code formatter」の設定
設定ファイル：.prettierrc

```json:
{
  "tabWidth": 2,
  "semi": true,
}
```

### ライブラリ「prettier-plugin-tailwindcss」の追加
Tailwind公式のPrettier用プラグイン  
classに渡された文字列からTailwindCSSクラスを含む属性を探して、推奨されるクラスの順序に従ってそれらを自動的に並べ替えられます。

設定ファイル：.prettierrc
```
{
  "plugins": [
    "prettier-plugin-svelte",
    "prettier-plugin-organize-imports",
    "prettier-plugin-tailwindcss" // 最後に読み込む
  ],
  "pluginSearchDirs": false
}
```

### ライブラリ「eslint-plugin-tailwindcss」の追加
classのコンフリクト、tailwindにサポートされていないクラスの使用、冗長な記述などを指摘してくれます。

設定ファイル：.eslintrc.json
```
{
  "extends": ["next/core-web-vitals", "plugin:tailwindcss/recommended"],
  "plugins": ["tailwindcss"]
}
```
## 推奨設定になっているVSCode拡張機能
設定ファイル： `.vscode/extensions.json`

### [shadcn/ui](https://marketplace.visualstudio.com/items?itemName=SuhelMakkad.shadcn-ui)
コマンドパレットからshadcn/uiコンポーネントの追加ができる。

### [easy-simple-react-snippets-lite](https://marketplace.visualstudio.com/items?itemName=nino.easy-simple-react-snippets-lite)
Reactの記述に便利なスニペット

### [File Utils](https://marketplace.visualstudio.com/items?itemName=sleistner.vscode-fileutils)
コマンドパレットからファイル操作ができる。

### [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- Tailwind CSSのClass名を自動補完
- マウスオーバー時のCSSプレビュー

デフォルトだとクラス名の自動補完の表示されるタイミングが遅かったり、クラス名を書き直したい時に補完されないことがあるため、以下の設定で常にクラス名候補を表示してくれるようになります。  

VSCodeの settings.json
```
"editor.quickSuggestions": {
  "strings": true
}
```

### [PostCSS Language Support](https://marketplace.visualstudio.com/items?itemName=csstools.postcss)
PostCSS の言語サポート  
@tailwind、@apply、@screenのカスタムCSSを使った際に発生するVSCodeのエラーが解決できます。

<img src="https://github.com/tohda/template-nextjs-shadcn/assets/16369289/dd2ace23-541c-443b-9655-cf767522faf8" width="400">
