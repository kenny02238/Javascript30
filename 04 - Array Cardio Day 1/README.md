# day04 - Array Cardio Day 1

## 學習重點:

**1. Array.prototype.filter()**

- filter()會建立一個經指定之函式運算後，由原陣列中通過該函式檢驗之元素所構成的新陣列
- 語法:

      var newArray = arr.filter(callback(element[, index[, array]])[, thisArg])

- element: 原陣列目前所迭代處理中的元素
- index(選擇性): 原陣列目前所迭代處理中的元素之索引
- array(選擇性): 呼叫 filter 方法的陣列
- thisArg(選擇性): 執行 callback 回呼函式的 this 值

  **2. Array.prototype.map()**

- map()方法會建立一個新的陣列<br> 其內容為原陣列的每一個元素經由回呼函式運算後所回傳的結果之集合
- 語法:

      let new_array = arr.map(function callback( currentValue[, index[, array]]) {
      // return element for new_array
      }[, thisArg])

- currentValue: 原陣列目前所迭代處理中的元素
- index(選擇性): 原陣列目前所迭代處理中的元素之索引
- array(選擇性): 呼叫 map 方法的陣列
- thisArg(選擇性): 選擇性的參數。執行 callback 回呼函式的 this 值

**3. Array.prototype.sort()**

- sort() 方法會原地（in place）對一個陣列的所有元素進行排序，並回傳此陣列。<br> 排序不一定是穩定的（stable）<br>預設的排序順序是根據字串的 **Unicode 編碼**位置（code points）而定
- 語法:

      arr.sort([compareFunction])

- compareFunction (選擇性):<br> 指定一個函式來定義排序順序。假如省略此參數<br> 陣列將根據各個元素轉為字串後的每一個字元之 Unicode 編碼位置值進行排序
- sort(a,b) if a-b>0 順序是 b a , if a-b<0 順序是 a b if a=b 順序不變

**4. Array.prototype.reduce()**

- reduce() 方法將一個累加器及陣列中每項元素（由左至右）傳入回呼函式，將陣列化為單一值。
- 語法:

      arr.reduce(callback[accumulator, currentValue, currentIndex, array], initialValue)

- accumulator:用來累積回傳值的累加器
- currentIndex(選擇性): 目前所迭代處理中的元素之索引
- array(選擇性): 呼叫 reduce() 方法的陣列
- initialValue(選擇性): 設定第一次呼叫的初始值，如果沒輸入則拿第一個元素當初始值<br> 會從第二個元素開始累加

**5. JavaScript String split() (字串切割)**

- split() 方法可以用來根據你指定的分隔符號，將字串切割成一個字串陣列
- 語法:

      str.split([separator[, limit]])

- separator: 用來指定分隔符號
- limit(選擇性): 表示最多返回幾個分隔字串
- split() 結果返回一個字串陣列
- 分隔符號也可以是一個正規表示式
- 如果用''空字符串當分割點,不是切割每個字符,也不是在每個 Unicode 字符<br> 而是在每個 UTF-16 代碼單元之間,會摧毀代理對

**6. search、indexOf、includes 搜尋字串方法**

- search(): 接受一個正則當作參數<br> 若查找到符合規則的字串，則回傳匹配字串第一個字的**索引值**，若查找不到，則回覆 **-1**
- indexOf(): 接受兩個參數，第一個參數為欲搜尋的字串，第二個參數為開始查找的位置，默認值為 0。<br> 若查找到符合的字串，則回傳匹配字串第一個字的**索引值**，若查找不到，則回覆 **-1** <br> 若第一個參數未傳入，則當作搜尋字串 undefined<br> 若第一個參數傳入為空字串，則會回傳 fromIndex 的值，但若給予的 fromIndex 值超過字串長度，則回覆字串長度。
- includes(): 接受兩個參數，第一個參數為欲搜尋的字串，第二個參數為開始查找的位置，默認值為 0。若查找到符合的字串，則**回傳 true**，若查找不到，則**回傳 false**
