# Obsidian Plugin設定

## 導入するplugin

### Zotero関連

Zotero Integration  
Zotlit

### ObsidianのUI関係

Minimal Theme Settings  
Style Settings

### Obsidian運用における中核的plugin

Dataview  
Pandoc Plugin 

### 表作成・編集関係

Advanced Tables  
Markdown Table Editor  
Table Generator

## 各pluginの設定

細かい解説は省略。設定画面をAIに投げて聞けば良い。  
注意点のみ、下記に記載。

### Pandoc Plugin

ターミナルを使用した、pandocのインストールが必要。

```bash pandoc --version```  
の結果、  
command not found  
となる場合は、  
```bash brew install pandoc```  
でインストールする。

他に、Extra pandoc arguments欄で、Zoteroのjsonファイルのパスが必要。   
まだ置いていない場合は、[前段階のマニュアル](1_Zotero_plugin設定.md) を参照してexport  

### Zotlit

templateファイル(後述)がグラフビュー(後述)に出てきてしまって邪魔なので、非表示設定をしておく。
Obsidianの設定 (Zotlitの設定ではない) > ファイルとリンク > 除外ファイル  
→ ZtTemplates/  
を選択しておく。

以降は、Zotlit内の設定。

Template > simple > Note filename を下記にしておく。   
<%= it.citationKey ?? it.citekey ?? it.DOI ?? it.title %>.md  
これは、論文ノートのmdファイル名を、citation keyにするための設定。 
Zoteroのバージョン次第だが、it.citationKey か it.citekey のどちらかを使用している。  
doiやタイトルは、上記が割り当てられていない等の不具合時に、代わりに使用される。

Connect > Zotero data directory において  
画像のようなエラーが出ていても、問題なく動く。  
![](../images/002.png)


