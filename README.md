# Shoppe_Crawler_Project
## 目的
- 從蝦皮網站上抓取特定商品的資訊，包含了圖片、品名、價格等等，將其整理成html以及xlsx格式後，透過通訊軟體telegram，於每日固定時間"自動"將整理好的檔案傳送出來。

## 使用到的套件及工具
### 套件       
- selenium
- time
- webdriver
- beautifulsoup
- pandas
- requests
### 工具
- vscode
- github
- git
- telegram 

## 簡易流程
1. 透過selenium的方式開啟webdriver，並直接連接到"目標"的蝦皮網頁
2. 對目標的蝦皮網頁進行操作，包含了頁面往下及往右往左滾動
3. 滾動完畢後將上述資料使用request下載下來並用beautifulsoup去進行解析
4. 將beautifulsoup解析過後的程式碼再更進一步地進行分析，依照品名、價格等進行排序
5. 將上述排序完後的資料，整理成html檔以及xlsl檔進行存檔
6. 於固定時間透過github將上述的檔案透過telegram傳送給自己

## 流程中碰到的問題
(1)為何要透過selenium開啟而不用正常的chrome開啟?

    ==> 因為直接透過chrome開啟的蝦皮中含有很多cookie或者head或者argument才能將"完整的"資料下載下來，因此透過selenium可以避免上述的問題產生
(2) 為何要對打開後的蝦皮網頁左右移動?

    ==>因為蝦皮網頁一頁通常會有60個資料，但是需讓資料有"實際"呈現在網頁上，才能抓到資料，所以需要往下滾動才能讓這些資料出來。
(2+6) 為何還要往左或往右滾動?

    ==> 因為我們是透過github於"固定時間"自動幫我們跑程式碼，但是github的執行上需要我們將蝦皮頁面以headless的方式進行跑動，而在headless的狀態下，我們須將網頁往下並往右最後再往左的方式，才能讓60筆完整的資料被抓取下來。
(6) 為何最後是使用telegram進行傳送?

    ==> 我們原本是希望透過LINE的方式將資訊傳送給自己，但是LINE目前在技術上只能串送圖片、文字或者url，目前我們無法解決傳送檔案的問題，因此最後才使用telegram。
