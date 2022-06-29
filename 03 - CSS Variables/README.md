# day1 JavaScript Drum Kit

## 解題流程:

**1. 利用 querySelectorAll 取出所有 input**<br>
**2. 利用 forEach()對每個 input 監聽 change 和 mousemove 事件<br>並用 handleChange 方法處理**<br>
**3. 利用 querySelector 取出:root 樣式 並用 style.setProperty 改變其樣式值**<br>

## 學習重點:

**1. input dataset**

- input 標籤支持 HTML 全局屬性,全局屬性中有 data-*, *可以自定義數據
- dataset 透過 JS 可以綁定 data-\*並取出其中的值

      <input id="blur" type="range" name="blur" data-sizing="px">//html
      input.dataset.sizing //JS 取出data-sizing的值(px)

**2. JS 設置 CSS 樣式**

- 直接設置 style 屬性<br>如果屬性中有 background-color 這種的話可以用[]或是駝峰式寫法(camel case)

      element.style.height = '100px';

- 使用 setAttribute

      element.setAttribute('height', '100px');

- 使用 setProperty(value,priority 為可選值 priority 可設置!important 優先級)

      style.setProperty(propertyName, value, priority);

- 使用 classList 新增移除 class name 更動 css 樣式

      e.target.classList.remove('styleName');

- 設置 cssText

      element.className = 'styleName';

- 使用 addRule、insertRule

        document.styleSheets[0].addRule('.box', 'height: 100px');
        document.styleSheets[0].insertRule('.box {height: 100px}', 0);
