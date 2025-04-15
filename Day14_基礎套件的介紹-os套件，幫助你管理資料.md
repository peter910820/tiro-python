# Day 14 : 基礎套件的介紹-os套件，幫助你管理資料

這邊就來介紹在python中非常重要的檔案管理套件，叫做os。它可以用來幫助你管理資料夾中的檔案，當然也可以做到一次更動檔名或資料的功能，非常的實用，使用前就先import吧，它是內建的所以不需要使用pip來做安裝，直接import就好。

```python
import os
```

再來就來創建一個資料夾吧，我們可以利用os.mkdir這個指令，mkdir是MakeDictionaries的意思，顧名思義就是創建一個資料夾。

```python
import os
os.mkdir('./test')
```

![](./image/Day14_01.png)

執行後就會發成功創建了一個test資料夾了。你已可以使用os.rmdir(RemoveDictionaries)來刪除指定資料夾。

```python
import os
os.rmdir('./test')
```

![](./image/Day14_02.png)

當然，因為是檔案管理套件，當然可以取得檔案的資料，就先從取得檔名開始講起，取得路徑下檔名非常的簡單，只要使用os.listdir就好了，例如我在剛剛的test資料夾中放了兩個檔案，a.txt跟b.txt，然後使用os.listdir:

```python
import os
list = os.listdir('./test')
print(list)
```

![](./image/Day14_03.png)

可以發現它就會將test資料夾下的所有檔案名稱以list(串列)的方式print出來，在很多檔案的狀況下就可以利用這種方法配合字串搜索來快速找到你想調整的檔案並對它進行變更。

在來就來嘗試取得檔案內的資料吧，在講這個之前必須先說明一下，開啟檔案的方式以及os中檔案讀寫的差異性。

開啟檔案有兩種方式，一種是使用os中的os.open，比較不直覺但功能較廣，另一種就是使用python的內建功能-open。open比較直覺並且好理解，故我這邊會用open來當範例。

open中可以放三個參數，分別是檔案路徑以及讀寫方式，還有編碼方式。我們先在a.txt裡面打入123456並把python程式碼改成這樣:

```python
import os
f = open( "./test/a.txt", 'r', encoding='utf-8')
print(f.read())
```

![](./image/Day14_04.png)

輸出結果可以看到，print出我們剛剛輸入的123456了，這邊程式碼非常好理解，首先open內的三個參數的第一項就是路徑，我們指向了a.txt這個檔案，第二個參數則是讀寫方式，大致可以分為三種:

r : 單純讀取這個檔案內的資料，不能做修改。

w : 更改這個檔案。

a : 再不引響檔案的狀況下，在檔案最後方追加資料。

第三個參數則是編碼方式，通常都會使用utf-8編碼。

然後將讀取得結果存到f變數中。

再來，我們可以使用read()函式將資料讀出來，f.read()就是從f中讀出資料的意思。

然後來講講w模式吧，它可以蓋過原本的資料，做覆寫的動作，將剛剛的程式碼改成這樣:

```python
import os
f = open( "./test/a.txt", 'w', encoding='utf-8')
f.write("abcdef")
f.close()
x = open("./test/a.txt", 'r', encoding='utf-8')
print(x.read())
```

這邊有兩點要注意，首先是w權限的使用，它無法使用read函式，所以必須使用r再open一次;第二點是任何檔案開完後必須利用close將它關閉，不然可能會有bug的產生。

![](./image/Day14_05.png)

結果你就會看到123456被更改成abcdef了，如果想在後面增加輸入的話，我們就需要用到a權限。

```python
import os
f = open( "./test/a.txt", 'a', encoding='utf-8')
f.write("abcdef")
f.close()
x = open("./test/a.txt", 'r', encoding='utf-8')
print(x.read())
```

![](./image/Day14_06.png)

蠻簡單的吧!

明天會繼續談論OS，並且會把自身用os解決問題的例子拿出來分享。