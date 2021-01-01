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

### Seleniumのインストール
以下のコマンドを利用して、インストールする  

```
pip install selenium
```

pillowというライブラリもインストールするようだ  

```
pip install pillow
```

JupyterNotebook上でSeleniumを実行しようとするとエラーが発生する  


![image](https://user-images.githubusercontent.com/18514297/103432486-e042b800-4c22-11eb-921d-6e129408a881.png)

以下の通り、Firefox用のWebドライバであるgeckdriverが無いというメッセージが表示される  


`WebDriverException: Message: "geckodriver" executable needs to be in PATH.`

以下のコマンドでgeckodriverをインストールすることが可能  

```
brew install geckodriver
```

ドライバをインストール後に改めて、コードを実行してみると、自動的にFirefoxが起動する  

![image](https://user-images.githubusercontent.com/18514297/103433062-e8542500-4c2d-11eb-9133-c787e0614bf1.png)

Firefoxと同様にChromeもドライバをインストールする  
以下のコマンドでインストールすることが可能

```
brew install chromedriver
```

chromeが自動で起動することを確認する

![image](https://user-images.githubusercontent.com/18514297/103433121-b2fc0700-4c2e-11eb-9209-67364271164c.png)

pillowがインストールされていることを確認するのにJupyterNotebook上で以下のコマンドを実行する

```
from PIL import Image
```

![image](https://user-images.githubusercontent.com/18514297/103433134-ec347700-4c2e-11eb-8c1f-caa39abd13ab.png)

エラーが発生しなければOK