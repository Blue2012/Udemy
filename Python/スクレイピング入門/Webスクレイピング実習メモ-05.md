# Webスクレイピング入門
## ランキングサイトからまとめて情報収集

Webページの情報取得を行うには、HTMLのDOMを理解しておくことが重要そうだ   

![image](https://user-images.githubusercontent.com/18514297/103480693-0fbb1580-4e19-11eb-8fa5-2387d503d331.png)

今回、取得しようとしている対象データは全てh2タグ内に収まっている   
h2タグ内の要素を全て取得できれば、解決になりそうだが、もっと、精緻に取得する対象の値を絞る場合、もう少し細かめにタグを指定する必要がある   

![image](https://user-images.githubusercontent.com/18514297/103480844-27df6480-4e1a-11eb-8374-d74f5fa7da61.png)

今回の要素、「u_areaListRankingBox」の中にすっぽりと収まっているので、こちらの要素を抽出する   

以下のようなコードを用意する   

```python
elem_rankingBox = browser.find_element_by_class_name('u_areaListRankingBox')
```

これで、以下の通り、u_areaListRankingBoxの要素内に含まれている全ての要素は取得できる    

![image](https://user-images.githubusercontent.com/18514297/103480905-b05e0500-4e1a-11eb-9f75-64075b75b599.png)

この取得してきた要素にさらに条件をつけて、取得するデータの情報を絞ることができる   
取得してきた変数にさらに1階層掘り下げて、「find_element_by_class_name」で条件を絞る   

```python
elem_title = elem_rankingBox.find_element_by_class_name('u_title')
```

![image](https://user-images.githubusercontent.com/18514297/103481013-66c1ea00-4e1b-11eb-89b9-ebeb53801e60.png)

__<u>コツとしては大きい枠から初めて、徐々に絞っていくのが良いとのこと</u>__

また、今回取得してきたデータには先頭に余計なデータが含まれているため、そちらを除外する   
まずはスプリット関数を使用する   

```python
title = elem_title.text
title.split('\n')[1]
```

上記、Seleniumで抽出したデータに対して、不要な情報をPython標準の関数を利用して除外した   
split関数は()内で指定した文字をキーワードにして、データを分割し、リストに格納するという機能を持つ   

![image](https://user-images.githubusercontent.com/18514297/103481201-b8b73f80-4e1c-11eb-82e1-421ce54b0bd8.png)

なので、配列の2番目にアクセスすると以下の通り、データを抽出できる   

```python
title.split('\n')[1]
```

![image](https://user-images.githubusercontent.com/18514297/103481304-704c5180-4e1d-11eb-875f-46eea84848c7.png)

これで余分なデータも除外する形で必要なデータを取得できるようになった   

### 別解

以下はu_titleというクラスの中に存在するh2タグの情報を持ってこいと司令している

```python
elem_title = elem_rankingBox.find_element_by_class_name('u_title').find_element_by_tag_name('h2')
```

![image](https://user-images.githubusercontent.com/18514297/103481404-29ab2700-4e1e-11eb-827e-18af53ba5afd.png)
