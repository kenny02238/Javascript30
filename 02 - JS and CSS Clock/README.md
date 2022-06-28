# day1 JavaScript Drum Kit

## 學習重點:

**1. Date 物件**

- 透過 new Date()可以得到一個當下時間的 Date 物件(可透過 cosole.dir 看物件方法)
- 可 Date.parse(時間)可指定一個時間,會得到一個根據格林威治標準時間開始累計到指定時間的毫秒數(milliseconds)  
  時間日期字串格式要符合 RFC2822 或 ISO 8601 date 標準，如果是無效的格式會返回 NaN
- Date 物件有許多方法可以使用
  - getMilliseconds() 取得是幾毫秒 (0-999)
  - getSeconds() 取得是幾秒 (0-59)
  - getMinutes() 取得是幾分 (0-59)
  - getHours() 取得是幾時 (0-23)
  - getDate() 取得是幾日 (1-31)
  - getMonth() 取得是幾月 (0-11)
  - getFullYear() 取得是幾年(yyyy)
  - getDay() 取得是星期幾 (0-6)
  - getTime() 取得從 1970-01-01 00:00:00 UTC 累計的毫秒數
  - 另外還有許多方法可提供處理時間問題
  - > [參考資料](https://www.fooish.com/)

**2. classList 使用方式**

- add 可以增加一個或是多個類名
- remove 可以刪除一個或是多個類名
- toggle(class, true|false)
  - 指定一個類名如有存在則移除該類名 並且返回 false 如果不存在則添加類名 並且返回 true
  - 第二個參數是可選參數,用來強制添加或是刪除類名 false 強制刪除 true 強制增加
- contains(class) 返回會是 Boolean 值,判斷該類名是否存在
- item(index) 返回相對應的類名,索引值從 0 開始 如果在範圍外則返回 null

**3. audio 的操作方法**

- play() 撥放音樂
- pause() 暫停撥放
- load() 重新加載
- canPlayType() 可以播放類型,檢查瀏覽器是否可以播放指定的媒體類型  
  其餘還有很多 properties(屬性)可提供 JS 操作,尚須多加練習

**4. querySelectorAll**

- 使用 querySelectorAll 得到的會是一個 NodeList 對象它不是陣列但是可以使用 foreach()方法  
  而且它是一個靜態的集合
