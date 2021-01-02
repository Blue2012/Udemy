# Webスクレイピング入門
## 単体テキストデータの抽出

以下のようにプロパティを指定することで、項目の中に定義されているデータを抽出することが可能   

```python
elem = browser.find_element_by_id('name')
elem.text
```

## 複数テキストデータの一括

以下のようにプロパティを複数形で指定することで同じ要素を持っている値を一つの変数に格納される   
複数の値はリストの形式で格納されるため、番号を指定することで単体のデータにアクセスすることが可能になる   

```python
elems_th = browser.find_elements_by_tag_name('th')
```

上記はHTMLタグの中で「th」という要素を持つ値を一括で取得する   
取得した値は以下のように指定することで、アクセス可能になる    

![image](https://user-images.githubusercontent.com/18514297/103448815-23b02b80-4ce2-11eb-8b2f-ba6bee6ef2c1.png)

以下のような形で配列番号を指定する   

```python
elems_th[0].text
```

これをfor文を利用して、一括で取得しようとすると以下になる    

```python
# 配列の初期化
keys = []
# 対象要素の取得
elems_th = browser.find_elements_by_tag_name('th')
# 1つ1つの要素を取得し、1つの変数に追加する
for elems_th in elems_th:
    key = elems_th.text
    keys.append(key)
```

上記は項目の取得、続いて、各項目に格納されている値を取得する   
項目は「th」という要素に格納されていた   
値は「td」という要素に格納されている    

なので、先程のコードを応用して以下のようなコードを実装する

```python
# 配列の初期化
keys = []
# 対象要素の取得
elems_td = browser.find_elements_by_tag_name('td')
# 1つ1つの要素を取得し、1つの変数に追加する
for elems_td in elems_td:
    key = elems_td.text
    keys.append(key)
```

これでページに表示されている各項目名とそれに紐づく値を取得することができた