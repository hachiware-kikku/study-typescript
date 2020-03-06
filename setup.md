# typescript のセットアップ

- nodeプロジェクトの初期化

```
npm init
```

- typescriptのセットアップ

```
npm install --save-dev typescript
```

- typescriptの設定ファイル作成

```
.\node_modules\.bin\tsc --init
```

- [tsconfig.json]の編集
    - [outDir](./tsconfig.json#L15)
      - ビルドしたJavaScriptの出力先ディレクトリ
    - [rootDir](./tsconfig.json#L16)
      - コンパイル対象のルートディレクトリ

