# Webスクレイピング入門
## CSV形式でのデータ出力

pandasのライブラリを利用してデータを出力する   
まずはpandasのライブラリをインストール   

```python
pip install pandas
```

インストールが終わったら、以下の通り、ライブラリをインポート   
空のデータフレームを定義する   

```python
# 空のDataFrame(Excelの行列のようなもの)を定義
df = pd.DataFrame()
```

空のフレームを定義したら、その中に値を入れる   

```python
# thに格納されていた項目
df['項目'] = Columunkeys
# tdに格納されていた項目
df['値'] = Valuekeys
```

このように値を入れてやると以下のようにExcelのような2次元の配列表が出来上がる   

![image](https://user-images.githubusercontent.com/18514297/103449195-1b5aef00-4ce8-11eb-8fd5-b586e91f6a60.png)

出来上がった表をCSVファイルとして出力するためには、以下のように指定すれば良い

```python
df.to_csv(ファイル名)
```

上記のままでは画面左側に表示されている番号(インデックス番号)も出力されてしまうため、これらを除外するために以下のように指定する   

```python
df.to_csv(ファイル名,index=False)
```

するとカレントディレクトリにCSVファイルが出力されている   

![image](https://user-images.githubusercontent.com/18514297/103449291-78a37000-4ce9-11eb-8ecc-8d8fb16c1d4c.png)

ファイルを開いてみると以下のようにCSVファイルにデータが格納されていることが確認できる   

![image](https://user-images.githubusercontent.com/18514297/103449335-1c8d1b80-4cea-11eb-9d7f-9728099ff312.png)
