# Windowsのコマンドプロンプトの使用方法

## 指定したフォルダのディレクトリとファイルの名前の一覧を名前の昇順でソートする

実行するコマンド
```
dir /b [フォルダのパス] | sort
```

以下にコマンドの実行結果を示す。  
対象のフォルダはエクスプローラーで表示するとディレクトリ、ファイルの順番で表示される。
```
branches [ディレクトリ]
hooks [ディレクトリ]
logs [ディレクトリ]
objects [ディレクトリ]
refs [ディレクトリ]
COMMIT_EDITMSG
config
HEAD
index
```

コマンドの実行結果は名前の昇順でソートされ、ディレクトリとファイルが混ざって表示される。
```
branches [ディレクトリ]
COMMIT_EDITMSG
config
HEAD
hooks [ディレクトリ]
index
logs [ディレクトリ]
objects [ディレクトリ]
refs [ディレクトリ]
```

## 指定したフォルダのディレクトリとファイルの一覧を名前の昇順でソートする

実行するコマンド
```
dir [フォルダのパス] /o:gn
```

[Microsoftのサイトにあるdirコマンドの説明](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/dir)  
/o:g => ディレクトリを最初に表示する。  
/o:n => 名前でソートする。  
  
以下にコマンドの実行結果を示す。  
対象のフォルダはエクスプローラーで表示するとディレクトリ、ファイルの順番で表示される。
```
branches [ディレクトリ]
hooks [ディレクトリ]
logs [ディレクトリ]
objects [ディレクトリ]
refs [ディレクトリ]
COMMIT_EDITMSG
config
HEAD
index
```

コマンドの実行結果は名前の昇順でソートされ、最初にディレクトリが表示され次にファイルが表示される。
```
2024/01/08  14:17    <DIR>          ..
2024/01/08  14:17    <DIR>          branches
2024/01/08  14:17    <DIR>          hooks
2024/01/08  14:19    <DIR>          logs
2024/01/08  14:19    <DIR>          objects
2024/01/08  14:17    <DIR>          refs
2024/01/08  14:19                14 COMMIT_EDITMSG
2024/01/08  14:19               378 config
2024/01/08  14:19                24 HEAD
2024/01/08  14:19                32 index
```

## 指定したフォルダのディレクトリとファイルの一覧を名前の昇順でソートし、名前だけを表示する

実行するコマンド
```
dir [フォルダのパス] /b /o:gn
```

以下にコマンドの実行結果を示す。  
対象のフォルダはエクスプローラーで表示するとディレクトリ、ファイルの順番で表示される。
```
branches [ディレクトリ]
hooks [ディレクトリ]
logs [ディレクトリ]
objects [ディレクトリ]
refs [ディレクトリ]
COMMIT_EDITMSG
config
HEAD
index
```

コマンドの実行結果は名前の昇順でソートされ、最初にディレクトリが表示され次にファイルが表示される。名前だけが表示されるのでエクスプローラーでの表示と同じになる。
```
branches
hooks
logs
objects
refs
COMMIT_EDITMSG
config
HEAD
index
```

## 環境変数 Path の内容を表示する

実行するコマンド
```
echo %Path%
```

[Microsoftのサイトにあるpathコマンドの説明](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/path)

## 環境変数 Path の内容に指定した検索語が完全一致で含まれるかを確認する

実行するコマンド
```
echo %Path% | findstr /c:"apple peach grape"
```

コマンドの実行結果は、「apple peach grape」という連続した文字列が含まれる場合のみ環境変数 Path の内容が表示される。「/c」オプションで検索語を指定した場合は空白は検索語の区切りにはならない。  
  
[Microsoftのサイトにあるfindstrコマンドの説明](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/findstr)  
/c => Uses the specified text as a literal search string.

## 環境変数 Path の内容に指定した検索語の何れかが含まれるかを確認する

実行するコマンド
```
echo %Path% | findstr "apple peach grape"
```

コマンドの実行結果は、「apple」または「peach」または「grape」の何れかの文字列が含まれる場合のみ環境変数 Path の内容が表示される。空白が検索語の区切りになる。  
  
[Microsoftのサイトにあるfindstrコマンドの説明](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/findstr)  
Use spaces to separate multiple search strings unless the argument is prefixed with /c.

## カレントディレクトリまたは環境変数 Path の場所を探して、指定したファイルが存在する場所を表示する

実行するコマンド
```
where [ファイル名]
```

[Microsoftのサイトにあるwhereコマンドの説明](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/where)  
By default, where searches the current directory and the paths that are specified in the PATH environment variable.  

以下にコマンドの実行結果を示す。  
ファイル名として「notepad」を指定してコマンドを実行する。
```
where notepad
```

コマンドの実行結果は環境変数 Path の場所から複数の場所が表示された。
```
C:\Windows\System32\notepad.exe
C:\Windows\notepad.exe
C:\Users\<UserName>\AppData\Local\Microsoft\WindowsApps\notepad.exe
```
