# Webスクレイピング入門
## 業務効率化の第一歩
### Seleniumを利用した自動ログイン

まずはSeleniumを利用する際のデフォルト  
以下の定義を1行目に記載する  

```python
from selenium import webdriver
```

どのブラウザを利用するのかは以下の1行を追加して指定する  
今回はChromeを利用するため、以下のように記載する

```python
browser = webdriver.Chrome()
```

以下のように記載すると指定したURLに対して、Getメソッドを利用して  
Webページにアクセスすることができる

```python
browser.get('https://scraping-for-beginner.herokuapp.com/login_page')
```

![image](https://user-images.githubusercontent.com/18514297/103433198-674a5d00-4c30-11eb-8f3f-89d4177028e2.png)

以下を指定することでブラウザを閉じることが可能  

```python
browser.quit()
```

JupyterNotebookに以下のように2行を記載して一括で実行すると、  
ブラウザが起動して、ログインページにアクセスする

```python
browser = webdriver.Chrome()
browser.get('https://scraping-for-beginner.herokuapp.com/login_page')
```

もう一度、さらに実行するとブラウザが起動する  
その場合、複数のブラウザが起動することになるが、この後、Seleniumで記載するコードでは、Seleniumでは1つのブラウザしか制御できないため、<u> __先に起動したブラウザ__ </u> のみを起動することしかできない  

HTMLのinputというフォームはWebアプリにユーザーが入力した値を引き渡す機能を持っている  
このフォーム内のIDという項目に入力された値が格納されている  

今回は自動ログインを実現するため、usernameのidを持っているものを指定する  
chromeの検証モードで確認したidの値を指定する  

要素の指定は以下の通り実施する   

```python
elem_username = browser.find_element_by_id('username')
```

個人的な理解イメージだが、webdriverというライブラリのなかに「find_element_by_id」というメソッドがあり、id名の中から「username」の値を探してくるというもののようだ。

![image](https://user-images.githubusercontent.com/18514297/103439816-976f1b80-4c83-11eb-9901-a7cf16e27451.png)
