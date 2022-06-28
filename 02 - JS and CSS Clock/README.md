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

**2. setTimeout 使用方式**

- 語法:setTimeout(fun,延遲毫秒);
- 只會執行一次,如果需要持續執行需在 fun 內再次呼叫 setTimeout
- 如要停止需要 clearTimeout(setTimeout 的變數名稱)

        function foo(){
            console.log('bar');
            setTimeout(foo,1000);
        }
        const foobar = setTimeout(foo,1000);
        clearTimeout(foobar);//停止時輸入

**3. setInterval 使用方法**

- 語法:setInterval(function,毫秒);
- 所指定的毫秒為每隔多久就執行一次
- 無法保證執行間隔,如果前一次的函數執行時間較長,則回調有可能意外被執行
- 如要停止需要 clearInterval(setInterval 的變數名稱)

        function foo(){
            console.log('bar');
        }
        const foobar = setInterval(foo,1000);
        clearInterval(foobar);//停止時輸入

**4. requestAnimationFrame 使用方法**

- 語法: requestAnimationFrame(function);
- 可與瀏覽器和硬體同步(例如螢幕更新頻率),當螢幕準備好接受下一個畫面更新時回調
- 如果使用者沒在使用頁面時會停止呼叫,節省系統資源
- 只會執行一次,如果需要持續執行需在 fun 內再次呼叫 requestAnimationFrame
- 如要停止需要 cancelAnimationFrame(requestAnimationFrame 的變數名稱)

        function foo(){
            console.log('bar');
            requestAnimationFrame(foo);
        }
        const foobar = requestAnimationFrame(foo);
        cancelAnimationFrame(foobar);//停止時輸入

