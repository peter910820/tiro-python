# Day 10 : 存放資料的收納庫-串列資料(下)

今天繼續來補足Python的其他存放資料的辦法:

# tuple

tuple跟list很相似，差別差在tuple為不可變動的串列，而且tuple並非用中括號，是用小括號。

```python
week = ("Monday","Tuesday","Wednesday")
print(week[1]) #輸出為Tuesday
```

對，就這麼簡單。只是要注意的是，tuple不能修改，而且定義時要用()，取出時用[]。

# dict

dict是一種比較複雜的形式，在dict中，會有所謂的key以及value，透過取出key就可以知道對應的value。建立字典要使用大括號{}來建立，如下

```python
dict = {}
```

這樣就建立一個空的字典叫做dict了，再來就是放key以及value進去。

```python
dict = {"date":"20200811", "time":"0904" ,"week":"Wednesday"}
```

形式為key:value，在key跟value之間用冒號隔開，每一組都用逗號隔開，。再來就可以取出key來取得value值了。

```python
dict = {"date":"20200811", "time":"0904" ,"week":"Wednesday"}
print(dict["date"]) #輸出為 20200811
```

刪除的話可以利用del的方式來刪除整個key。

```python
dict = {"date":"20200811", "time":"0904" ,"week":"Wednesday"}
del dict["date"]
print(dict) #可以看到輸出沒有date的值了
```

可以刪除當然可以新增，新增的方法如下:

```python
dict = {"date":"20200811", "time":"0904" ,"week":"Wednesday"}
dict["weather"] = "sun"
```

打入第二行程式碼後，就可以用print指令來看，就會發現dict被新增了一個key叫weather，裡面有個值叫sun。

dict當然也可以用len()去觀測他的長度。

```python
dict = {"date":"20200811", "time":"0904" ,"week":"Wednesday"}
print(len(dict)) #可以看到陣列長度為3
```

這篇有點少呢...明天直接就進入套件的環節吧(