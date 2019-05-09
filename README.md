# corpus_processor

## 專案目的
這個專案主要是方便於處理語言田野調查課程所採集的檔案。這學期我們請了汶水泰雅語的族語老師，並將每個禮拜採集的語料整理成一個`.docx`檔。

## 語料檔範例
```
1.
ma-tas=sami         su     tigami     ni     Payan    babay   i    Laway
AF-write=1PL.NOM    ACC    letter     BEN    Payan    for     NOM  Laway
主焦-寫=1PL.主格     受格    信         受益格   Payan    給      主格  Laway

#e I write the letter to Laway with Payan.  
#c 我跟Payan一起寫信給Laway。   
#n 比較 ki Payan 和 ni Payan: ki Payan的意思為「和 Payan」，ni Payan的意思為「 Payan的信」。

2.
si-pa-quwas=mu           i      yaya
CF-VBL-song=1SG.GEN      NOM    mother
參焦-動化-歌=1SG.屬格      名詞    媽媽
 
#e I sing for mom.
#c 我唱歌給媽媽聽。
#n i 可以省略。
```

## 語料檔格式
```
[編號].
[族語轉寫]
[英文Glossing]
[中文Glossing]
[空行]
#e [英文翻譯]
#c [中文翻譯]
#n [註釋]
[空行]
```

## `.ipynb`檔使用方式
### Step 1
先將專案clone至自己的電腦中
```
$ git clone https://github.com/puerdon/corpus_processor.git
```

### Step 2
啟動電腦中的`jupyter`伺服器（前提是電腦裡已事先安裝`jupyter`）
```
$ jupyter notebook
```

### Step 3
進瀏覽器中的`jupyter`中開啟路徑底下的`corpus_processor.ipynb`

### Step 4
開一個新的cell，呼叫`search`函數，`search`函數接收兩個參數，第一個參數(字串)為語料`.docx`檔所在路徑，第二個參數為欲搜尋的字串，可以使用regex。

```python
# 假設我的語料都在 /user/Don/corpus
# 假設我想搜尋所有標有LOC或NOM的語料
# 我就可以呼叫下列函數:
search("/user/Don/corpus", "(NOM|LOC)")

# 當然我也可以直接搜尋某個中文字串
search("/user/Don/corpus", "給")
```
