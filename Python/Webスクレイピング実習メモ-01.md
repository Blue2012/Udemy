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

