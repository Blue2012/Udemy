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

```python
elems_th[0].text
```
