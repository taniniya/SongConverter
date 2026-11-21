# SongConverter

太鼓の達人シミュレータ向け TJA ツール集（SongSorter / DanGenerator / DanConvertor）のカスタム版です。

English: [README_EN.md](README_EN.md)

## これは何？

bluetaiko 氏の SongConvertor をベースにしたカスタム版です。本家リポジトリが削除されたため、フォークを元に UI の改良を加えてこのリポジトリで公開しています。

## ダウンロード

[Releases](https://github.com/taniniya/SongConverter/releases) から `SongConverter-v1.1.0.exe` をダウンロードしてください。.NET ランタイム同梱の単一ファイルなので、Windows でそのまま実行できます（インストール不要）。

## 機能

### SongSorter
esegit でコピーした TJA を、本家と同じ並び順に整理します。

### DanGenerator
太鼓 Wiki の段位ページから、段位名と条件を使って TaikøNauts 等で使える段位ファイルを生成します。

### DanConvertor
OpenTaiko 等の TJA 段位を、TaikøNauts 等で使える形式の段位ファイルに変換します。

## 使い方

### SongSorter
1. AddSongs タブで、曲をダウンロードする親フォルダを選択して「曲追加実行」ボタンを押します。（git がインストールされていない場合は https://git-scm.com/ からインストールしてください）
2. SongSorter タブでコピー元の Songs フォルダと、コピー先の Songs フォルダを選択します。
3. 「並び替え開始」ボタンを押します。

### DanGenerator
1. 太鼓 Wiki の段位ページの URL を入力します。（例: https://wikiwiki.jp/taiko-fumen/%E6%AE%B5%E4%BD%8D%E9%81%93%E5%A0%B4 ）
2. 出力先フォルダを決めます。
3. Songs フォルダを選択します。
4. 「段位生成」ボタンを押します。

### DanConvertor
1. 変換する TJA ファイルを選択します。
2. 出力先フォルダを決めます。
3. Songs フォルダを選択します。（省略可）
4. 「変換実行」ボタンを押します。

※ 難易度の指定は TJA の仕組み上難しかったため、難易度は "danSongs" の "difficulty" を変更して指定してください（0: かんたん, 1: ふつう, 2: むずかしい, 3: おに, 4: おに裏）。
デフォルトでは、シミュフォルダを選択しない限り段位の TJA を分割するため、難易度の指定は不要です。

## カスタム版の変更点（v1.1.0）

- **進行状況パネルの大型化**: ログの上に大きなパネルを常時表示。現在の処理が太字で大きく出て、%・処理件数（処理済み/全体）・経過時間を表示。処理が終わった後も最終状態が残ります
- **SongSorter の進捗表示を配線**: コア側にあった進捗コールバックが本体で使われていなかったので、プログレスバーに反映されるようにしました。譜面リスト更新もカテゴリ単位で進捗が出ます
- **ダークテーマ**: 全体をダークグレー基調にし、実行ボタンは太鼓レッドに。タブは選択中が分かるよう赤ライン表示、ログはターミナル風（黒背景＋緑文字）になりました
- **アイコン変更**: 太鼓＋バチ＋音符のデザインに変更
- **アップデート確認先の変更**: 削除された本家リポジトリではなく、このリポジトリ（taniniya/SongConverter）を見るようにしました

## ビルド方法

.NET 10 SDK が必要です。

```
dotnet publish SongConverter.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:EnableWindowsTargeting=true
```

## クレジット / ライセンス

- 原作: bluetaiko 氏（SongConvertor）
- ライセンス: MIT License（[LICENSE](LICENSE) を参照）
