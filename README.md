# Gaussian Scan（配布用）

スキャン測定データ（位置・強度）から、微分・直接FWHM・Gaussianフィットでビーム幅などを評価する Windows 用アプリです。
このリポジトリは**実行ファイルの配布専用**です（ソースコードは含みません）。

## ダウンロード

[Releases](https://github.com/RyomaKataoka/GaussianScan-release/releases/latest) から `GaussianScan.exe` をダウンロードしてください。
`SHA256.txt` はファイルが壊れていないかの確認用です。

## 動作環境

- Windows 10 / 11（64ビット）
- インストール不要。Python や追加ライブラリ、インターネット接続も不要です。

## 使い方（はじめて起動するとき）

1. `GaussianScan.exe` を任意のフォルダ（例：`C:\Tools\GaussianScan`）に置きます。
2. ダウンロードしたファイルを右クリック →「プロパティ」→「許可する」にチェックを入れると、警告が出にくくなります。
3. ダブルクリックで起動します。署名のない実行ファイルのため、初回は「Windows によって PC が保護されました」と表示されることがあります。「詳細情報」→「実行」を選んでください。
4. 起動時に一時フォルダへ展開するため、数秒～数十秒かかることがあります。

ハッシュ値の確認（任意）：PowerShell で次を実行し、`SHA256.txt` の値と一致することを確かめます。

```
Get-FileHash .\GaussianScan.exe -Algorithm SHA256
```

操作方法は [使い方.txt](使い方.txt) を参照してください。
`sample/` の `pos.txt` と `xas.txt`（横軸1列目・縦軸4列目）で動作を試せます（合成データ）。

## 注意

- 元のデータファイルは変更しません。レジストリ・PATH・既存の Python も変更しません。
- 新しい版で保存したセッションファイル（`.gscan`）は、古い版では開けません。

## ライセンス

EXE には Python・Tcl/Tk・NumPy・SciPy・Matplotlib などが含まれます。
一覧は [licenses/THIRD_PARTY_NOTICES.txt](licenses/THIRD_PARTY_NOTICES.txt)、全文は `licenses/` にあります。
EXE を再配布するときは `licenses/` フォルダも一緒に配布してください。
