# day1 JavaScript Drum Kit

## 解題流程:

**1. 將 window 事件'keyup'監聽並用 handleclick 方法處理**<br>
**2. 利用 keyCode 判斷按鍵,並在相對應按鍵撥放音效和加上 playing 效果**<br>
**3. 用 if 判斷式處理沒有按在特定按鍵的鍵盤事件**<br>
**4. 利用 audio.currentTime 設置音效每次從 0 秒開始撥放**<br>
**5. 利用 querySelectorAll 找到每一個.key 監聽是否動畫撥放完畢(transitionend)**<br>
**6. 如撥放完畢移除 playing 效果**<br>

## 學習重點:

**1. addEventListener 事件**

- 過程中有發現到 keypress 是必須在按完鍵盤且螢幕有輸出的情況下才使用,否則會取不到值
- 可監聽事件很多這次只使用到 keydown,keyup,keypress,transitionend  
  其餘還有很多 dom event 可監聽,須多加練習

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
