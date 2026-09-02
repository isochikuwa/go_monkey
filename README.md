# go_monkey

『Go言語でつくるインタプリタ』（原題: *Writing An Interpreter In Go*, Thorsten Ball著）を読みながら実装した、Monkey言語のインタプリタです。

本編の内容に加えて、書籍のボーナスチャプター「The Lost Chapter」で扱われているマクロシステム（`quote`/`unquote`とマクロ展開）まで実装しています。

## 構成

字句解析→構文解析（Pratt parsing）→評価（木構造を辿るインタプリタ）という、書籍の設計に沿った構成です。

```
ast/        構文木の定義
token/      トークン定義
lexer/      字句解析
parser/     構文解析（Pratt parsing）
object/     実行時の値・環境の表現
evaluator/  評価器、組み込み関数、マクロ展開
repl/       REPL
```

## 実装している機能

- 変数束縛、整数・真偽値・文字列・配列・ハッシュ
- 関数（第一級関数、クロージャ）
- 組み込み関数（`len` `first` `last` `rest` `push` `puts`）
- マクロシステム（`quote`/`unquote`によるコード生成、マクロ展開）

## 実行方法

```bash
go run main.go   # REPLを起動
go test ./...    # 各パッケージのテストを実行
```
