# Webスクレイピング入門
## Seleniumのインストールと準備
### JupyterNotebookのインストール

例のごとく、以下のコマンドを実行   
環境は自分のMacBookで実施  
まずはvenv環境を構築 

```
python3 -m venv venv
```

```
. venv/bin/activate
```

次にJupiterNotebookをインストール  
まずはpipのアップデート  

```
pip install --upgrade pip
```

```
pip install notebook
```

ちなみにめっちゃいっぱいパッケージ入る^^;  
インストールが完了したら、下のコマンドでnotebookを起動してみる  

```
jupyter notebook
```

notebookの母体になるサーバが起動して、自動でブラウザが起動  
かなり、簡単にインストール&起動ができた！

![image](https://user-images.githubusercontent.com/18514297/103413430-d6866980-4bbc-11eb-809c-77cc79816bb7.png)
