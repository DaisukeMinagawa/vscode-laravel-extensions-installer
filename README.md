# Visual Studio Codeのよくあるお勧めLaravelの拡張機能の一括インストールシェル
  
## VScodeのインポート ＆ エクスポートの方法まとめ
https://qiita.com/mainy/items/3072e68e704eae1421c1
  
## 利用方法
上記リンクの「VSCode Exstension のインポート」を実行するだけ。

> `vscode-extensions.txt`から Extension を一気にインストールします。
> 既にインストール済みの Extension は無視されます。

```
Get-Content vscode-extensions.txt | ForEach-Object { code --install-extension $_ }
```
  
> （参考）
> 上記のコマンドがわからない方は、下記の書き方だとわかりやすいかもしれません。

```
$extensions_list_file = "vscode-extensions.txt"
foreach ($extension in Get-Content $extensions_list_file) {
    code --install-extension $extension
}
```
  
Mac とか Linux とかだとこうなります。
```
cat vscode-extensions.txt | while read line; do code --install-extension $line; done
```

このシェルスクリプトはUbuntuとmacOSの両方に対応していますが、スクリプトは、VSCodeがシステムにインストールされており、
codeコマンドがパスに設定されていることを前提としています。 
macOSでは、VSCodeを公式サイトからダウンロードしてインストールした場合、codeコマンドがパスに設定されていない可能性があります。
その場合は、以下の手順でパスを設定してください。
1. VSCodeを開きます。
2. コマンドパレット（Cmd+Shift+P）を開きます。
3. "Shell Command: Install 'code' command in PATH" と入力し選択します。
4. ターミナルを再起動して、変更を反映させます


　　
# Bulk Installation Shell for Commonly Recommended Laravel Extensions in Visual Studio Code

## Summary of VSCode Import & Export Methods
https://qiita.com/mainy/items/3072e68e704eae1421c1

## How to Use
Simply execute the "VSCode Extension Import" from the link above.
> This will install all Extensions from `vscode-extensions.txt` at once.
> Already installed Extensions will be ignored.
```powershell
Get-Content vscode-extensions.txt | ForEach-Object { code --install-extension $_ }
```

> (Reference)
> If you're unfamiliar with the above command, the following format might be easier to understand:
```powershell
$extensions_list_file = "vscode-extensions.txt"
foreach ($extension in Get-Content $extensions_list_file) {
    code --install-extension $extension
}
```

For Mac or Linux, use this command:
```bash
cat vscode-extensions.txt | while read line; do code --install-extension $line; done
```

This shell script is compatible with both Ubuntu and macOS. However, the script assumes that VSCode is installed on the system and the code command is set in the PATH.
On macOS, if you downloaded and installed VSCode from the official website, the code command might not be set in the PATH. In that case, please follow these steps to set the PATH:

1. Open VSCode.
2. Open the Command Palette (Cmd+Shift+P).
3. Type "Shell Command: Install 'code' command in PATH" and select it.
4, Restart the terminal to reflect the changes.
