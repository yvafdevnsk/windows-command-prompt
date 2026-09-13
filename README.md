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
