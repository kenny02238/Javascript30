# day05 - Flex Panel Gallery

## 解題流程:

**1. 針對 css 調整 flex 和一些變動效果**<br>
**2. 利用 querySelectorAll 取出所有 .panel**<br>
**3. 利用 forEach()對每個 panel 監聽 click 和 transitionend 事件<br>並用 handleClick 方法和 handleTransitionend 方法處理**<br>
**4. 在 Click 事件利用 toggle 加上 open 的 classname**<br>
**5. 在 transitionend 事件利用 toggle 加上/刪除 open-active 的 classname**<br>

## 學習重點:

**1. Css Flex**

- flex-wrap: 可以設定 flex 要不要換行

  - nowrap(預設值) 不換行
  - wrap 換行
  - wrap-reverse 換行且順序反轉

- flex-direction: 設定主軸和輔軸方向

  - row(預設值) 主軸從左至右 輔軸從上至下
  - row-reverse 與 row 方向相同,但內部元件順序反轉
  - column 主軸從上至下 輔軸從左至右
  - column-reverse 與 column 方向相同,但內部元件順序反轉

- flex-flow: 可用來設置 flex-direction 和 flex-warp (順序沒分 中間空格即可)

- justify-content: 可以用來設置主軸對齊方式

  - flex-start(預設值) 從起點開始排
  - flex-end 從終點開始排
  - center 排在中間
  - space-between 兩邊貼主軸起點和終點,其餘平均排
  - space-around 平均分配元素,但距離起點和終點間隔較小
  - space-evenly 平均分配元素

- align-item: 可以用來設置輔軸對齊方

  - stretch(預設值) 將輔軸所有元素填滿(寬 or 高)不能設置 height,否則失效
  - flex-start 從起點開始排
  - flex-end 從終點開始排
  - center 排在中間(對齊方式是對齊字體中間)
  - baseline 排在中間(對齊字體下方)

- align-content: 控制輔軸每一行的距離(需有多行才有用)

  - stretch(預設值) 將每一行的大小拉長以填滿剩餘空間
  - flex-start 每一行從輔軸起點開始排
  - flex-end 每一行從輔軸終點開始排
  - center 每一行從正中間開始排
  - space-around 平均分配行的間距,但距離起點和終點間隔較小
  - space-evenly 平均分配行的間距
  - space-between 平均分配行的間距,但兩測貼輔軸起點和終點

- align-self 效果跟 align-item 一樣,但是用來改變 flex 裡的單一元素

- order: 預設值為 0,可通過設定預設值大小來對改變元素排列的順序(可設置負數)

- flex: 為 (flex-grow、flex-shrink、flex-basis)的縮寫

  - flex-grow(預設值為 0) 可依照設定值分配剩餘空間
  - flex-shrink(預設值為 1) 當空間不夠時,可依照設定值比例縮小
  - flex-basis(預設值為 auto) 優先級比 width 高,可設置元素基本寬度

- flex 縮寫的方式

  - 若只有一個值且沒有單位 會被視為 flex-grow (flex:1)
  - 若只有一個值且有單位 會被視為 flex-basis (flex:30px)
  - 若設置為 initial(flex:initial) 與 flex: 0 1 auto 相等
  - 若設置為 auto(flex:auto) 與 flex: 1 1 auto 相等
  - 若設置為 none(flex:none) 與 flex: 0 0 auto 相等
  - 若設置兩個值,第一個必須沒有單位,被視為 flex-grow<br>第二個值若無單位則視為 flex-shrink<br>第二個值若有單位則視為 flex-basis
  - 若設定為三個值,則依序為 flex-grow,flex-shrink,flex-basis

  **2. classList 和 className**

- element.classList 取到的會是 DOMTokenList(類似陣列但不是)有許多方法可用<br>以下列出目前常用的方法

  - add() 可增加 className
  - remove() 可刪除 className
  - toggle() 如 className 存在則刪除,如不存在則增加上去

- element.className 取到的會是字串類型的 className 並用空白隔開

**3. click 時的 event.target 和 this 差別**

- 測試過程中有發現一個小差異,在事件監聽.panel 的 click 事件下<br>如果是改變 e.target 的 classname 時,點到.panel 裡的 p 元素,e.target 就會為 p 元素不為整個.panel 元素<br>但是如果使用 this 去改變 classname 則不論點選哪邊都會指向.panel 元素 (不得使用 arrow function 否則 this 指向 window)

**4. transitionend 時的 event**

- 由於 transitionend 會得到許多改變後的事件,如不加以判斷再處理又剛好是偶數事件的話<br>由於 toggle 的特性會剛好消除掉想要增加或刪除的 calssname
