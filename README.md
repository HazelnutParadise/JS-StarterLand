# JS-StarterLand

<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="icon" href="https://src.hazelnut-paradise.com/HazelnutParadise-icon.ico">
    <title>JS新賓樂 (JS StarterLand): 為程式初學者設計的 JavaScript 教材 - 榛果繽紛樂</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/default.min.css">

    <style>
        /* 全站基本樣式 */
        body {
            margin: 0 auto;
            padding: 20px;
            max-width: 1200px;
            font-family: 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            background: #f5f5f5;
            scroll-behavior: smooth;
        }
        header, nav, main, footer {
            margin-bottom: 20px;
        }
        header h1 {
            font-size: xxx-large;
            text-align: center;
            color: #333;
        }
        header p {
            text-align: center;
            font-size: 1.1em;
            color: #555;
        }
        /* 導覽列 */
        nav {
            background: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            flex-wrap: wrap;
        }
        nav a {
            margin: 0 10px;
            text-decoration: none;
            color: #007acc;
            font-weight: bold;
        }
        nav a:hover {
            text-decoration: underline;
        }
        /* 各章節區塊 */
        .chapter {
            background: #fff;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .chapter h2 {
            margin-top: 0;
            color: #007acc;
        }
        .chapter code {
            font-size: 1.2em;
            background: #eef;
            padding: 2px 4px;
            border-radius: 3px;
        }
        pre code {
            font-size: 1.2em;
            background: #eef;
            padding: 10px;
            display: block;
            border-radius: 3px;
            overflow-x: auto;
        }
        /* 快捷按鈕 */
        .jump-btn {
            display: inline-block;
            margin-top: 10px;
            padding: 6px 12px;
            background-color: #007acc;
            color: #fff;
            border-radius: 3px;
            text-decoration: none;
            font-weight: bold;
        }
        .jump-btn:hover {
            background-color: #005fa3;
        }
        /* 線上編輯區 */
        .editor-section {
            background: #fff;
            padding: 20px;
            margin-top: 30px;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .editor-section label, .editor-section select {
            font-size: 1.1em;
        }
        #editor {
            width: 100%;
            height: 250px;
            border: 1px solid #ccc;
            margin-top: 10px;
        }
        .button-group {
            margin-top: 10px;
        }
        button {
            font-size: 1em;
            padding: 8px 16px;
            margin-right: 10px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            background: #007acc;
            color: #fff;
        }
        button:hover {
            background-color: #005fa3;
        }
        .test-result {
            margin-top: 20px;
            padding: 15px;
            background: #fafafa;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .passed {
            color: green;
        }
        .failed {
            color: red;
        }
        /* 回到頂端按鈕 */
        #toTopBtn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            padding: 10px 15px;
            background-color: #007acc;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            display: none;
            z-index: 1000;
        }
        #toTopBtn:hover {
            background-color: #005fa3;
        }
    </style>
    <script src="https://src.hazelnut-paradise.com/utils.js"></script>
    <script>getNavbar()</script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
    <script>hljs.highlightAll();</script>
    <!-- 載入 Ace Editor -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ace/1.37.2/ace.js"></script>
    <!-- （可自行載入 highlight.js 或其他前端語法高亮套件） -->
</head>
<body>
<div id="navbar-placeholder"></div>
<header>
    <h1>JS新賓樂 (JS StarterLand)</h1>
    <p>
        JavaScript 可用於網頁前端、伺服器、桌面應用、手機 App 及物聯網等多種領域。<br/>
        本教材為無程式基礎的初學者設計，幫助你從零開始建立程式設計能力！
    </p>
</header>
<nav>
    <!-- 新的章節順序 -->
    <a href="#ch0">第 0 章</a>
    <a href="#ch1">第 1 章</a>
    <a href="#ch2">第 2 章</a>
    <a href="#ch3">第 3 章</a>
    <a href="#ch4">第 4 章</a>
    <a href="#ch5">第 5 章</a>
    <a href="#ch6">第 6 章</a>
    <a href="#ch7">第 7 章</a>
    <a href="#ch8">第 8 章</a>
    <a href="#ch9">第 9 章</a>
    <a href="#ch10">第 10 章</a>
    <a href="#ch11">第 11 章</a>
    <a href="#ch12">第 12 章</a>
    <a href="#ch13">第 13 章</a>
    <a href="#ch14">第 14 章</a>
    <a href="#practice">練習區</a>
</nav>
<main>
    <div id="chapters">
        <!-- 第 0 章：前言與環境設定 -->
        <div class="chapter" id="ch0">
            <h2>第 0 章：前言與環境設定</h2>
            <p>
                JavaScript 是一門應用極廣的語言，可用於網頁前端互動、伺服器程式、桌面與手機 App 甚至物聯網裝置的開發。
                在開始學習之前，建議你下載並安裝 <a target="_blank" href="https://code.visualstudio.com/"><strong>Visual Studio Code (VS Code)</strong></a> 作為主要編輯器，
                這是一款免費且功能豐富的工具。<br/>
                <br/>
                請至 <a target="_blank" href="https://nodejs.org/"><strong>nodejs.org</strong></a> 下載 Node.js，完成後在終端機中輸入 <code class="language-javascript">node -v</code> 確認安裝成功。
            </p>
            <p>
                撰寫以下程式檢查環境：
            </p>
            <pre><code class="language-javascript">console.log("Hello World!");</code></pre>
            <p>
                若終端機中正確顯示 "Hello World!"，則表示環境設置完成。
            </p>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，回傳字串 <code class="language-javascript">"Hello World!"</code>，
                並利用 <code class="language-javascript">console.log()</code> 輸出結果。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 1 章：變數與資料型態 -->
        <div class="chapter" id="ch1">
            <h2>第 1 章：變數與資料型態</h2>
            <p>
                變數就像儲物櫃，用於存放各種資料；資料型態則定義了資料的形式。JavaScript 提供三種變數宣告方式：
            </p>
            <ul>
                <li><code class="language-javascript">var</code>：傳統方式，但存在作用域提升（Hoisting）問題，容易造成錯誤，故不建議使用。</li>
                <li><code class="language-javascript">let</code>：區塊作用域變數，僅在所在區塊有效，能避免作用域混淆。</li>
                <li><code class="language-javascript">const</code>：區塊作用域常數，一經設定值便不可更改，適用於固定資料。</li>
            </ul>
            <p>
                常見資料型態包括：
            </p>
            <ul>
                <li><strong>Number</strong>：數字，如 <code class="language-javascript">42</code>、<code class="language-javascript">3.14</code>，可進行算術運算。</li>
                <li><strong>String</strong>：字串，如 <code class="language-javascript">"hello"</code>，表示文字資料。</li>
                <li><strong>Boolean</strong>：布林值，僅有 <code class="language-javascript">true</code> 與 <code class="language-javascript">false</code>，常用於條件判斷。</li>
                <li><strong>Null</strong>：明確設定的空值，表示「無」。</li>
                <li><strong>Undefined</strong>：變數宣告後未賦值時的預設值。</li>
                <li><strong>Object</strong>：複合型資料，用於存放多個屬性與方法。</li>
                <li><strong>Array</strong>：有序資料集合，本質上也是物件。</li>
                <li><strong>Symbol</strong>：ES6 新增，表示獨一無二的值。</li>
                <li><strong>BigInt</strong>：用來表示超過 Number 安全範圍的大整數。</li>
            </ul>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，在函式內使用 <code class="language-javascript">let</code> 宣告變數（100）與 <code class="language-javascript">const</code> 宣告常數（200），
                然後回傳字串 <code class="language-javascript">"let: 100, const: 200"</code>。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 2 章：基礎輸入與輸出 -->
        <div class="chapter" id="ch2">
            <h2>第 2 章：基礎輸入與輸出 (I/O)</h2>
            <p>
                輸入與輸出是程式與使用者間溝通的橋樑。使用 <code class="language-javascript">console.log()</code> 可將訊息印出到終端機，協助你追蹤程式運作與除錯。
            </p>
            <p>
                例如，計算 BMI 的公式為：<code class="language-javascript">BMI = weight / ((height/100)²)</code>。
                當身高以公分表示時，必須先除以 100 轉換成公尺，再進行計算。
            </p>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve(height, weight)</code>，根據上述公式計算 BMI 並回傳數值結果。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 3 章：運算子與流程控制 -->
        <div class="chapter" id="ch3">
            <h2>第 3 章：運算子與流程控制</h2>
            <p>
                運算子用於數學計算與邏輯比較，流程控制則決定程式根據條件如何執行。
                <strong>基本運算子</strong>：例如 <code class="language-javascript">+</code>、<code class="language-javascript">-</code>、<code class="language-javascript">*</code>、<code class="language-javascript">/</code>、<code class="language-javascript">%</code> 用於數學計算：
            </p>
            <pre><code class="language-javascript">console.log(10 + 5);    // 15
console.log(10 % 3);    // 1</code></pre>
            <p>
                <strong>比較運算子</strong>：
                - <code class="language-javascript">=</code> 用於賦值；
                - <code class="language-javascript">==</code> 在比較時會自動轉換型別（例如 5 == "5" 為 true）；
                - <code class="language-javascript">===</code> 嚴格比較，只有型別和值都相同才回傳 true（例如 5 === "5" 為 false）。
            </p>
            <p>
                <strong>流程控制語法</strong>：
                使用 <code class="language-javascript">if...else</code> 根據條件決定執行區塊：
            </p>
            <pre><code class="language-javascript">if (score >= 60) {
  console.log("及格");
} else {
  console.log("不及格");
}</code></pre>
            <p>
                使用 <code class="language-javascript">switch</code> 進行多分支選擇，並搭配 <code class="language-javascript">break</code> 防止落空執行：
            </p>
            <pre><code class="language-javascript">switch (fruit) {
  case "apple":
    console.log("蘋果");
    break; // 若無 break，則會繼續執行下一個 case
  case "banana":
    console.log("香蕉");
    break;
  default:
    console.log("未知水果");
}</code></pre>
            <p>
                <strong>迴圈語法</strong>：
                使用 <code class="language-javascript">for</code> 或 <code class="language-javascript">while</code> 重複執行程式；
                <code class="language-javascript">continue</code> 可跳過本次迴圈的剩餘程式，<code class="language-javascript">break</code> 可中斷整個迴圈：
            </p>
            <pre><code class="language-javascript">// 使用 continue：當 i === 2 時跳過
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i);  // 輸出 0, 1, 3, 4
}

// 使用 break：當 i === 3 時中斷迴圈
for (let i = 0; i < 5; i++) {
  if (i === 3) break;
  console.log(i);  // 輸出 0, 1, 2
}</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve(score)</code>，根據分數回傳等級：
                分數 ≥ 90 為 "A"，80–89 為 "B"，70–79 為 "C"，60–69 為 "D"，其他回傳 "不及格"。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 4 章：函式與箭頭函式 -->
        <div class="chapter" id="ch4">
            <h2>第 4 章：函式與箭頭函式</h2>
            <p>
                函式可封裝重複的邏輯，並透過參數接收外部輸入，最後回傳結果。這使得函式成為程式設計中的基本組件。
                除了傳統函式外，ES6 提供的箭頭函式語法更簡潔，且 this 綁定固定。
                下例示範傳統函式如何使用參數與回傳值：
            </p>
            <pre><code class="language-javascript">function add(a, b) {
  // a 與 b 為傳入參數，計算並回傳其和
  return a + b;
}
console.log(add(3, 4)); // 輸出 7</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve(x)</code>，回傳 x 的平方，請使用多行箭頭函式語法。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 5 章：遞迴與進階函式應用 -->
        <div class="chapter" id="ch5">
            <h2>第 5 章：遞迴與進階函式應用</h2>
            <p>
                遞迴是函式呼叫自身的一種技巧，常用於解決可以分解成相同問題的小問題。例如計算階乘：
                n! = n × (n-1)!，當 n 為 0 時定義 0! = 1。這種方法使問題得以逐步簡化。
            </p>
            <pre><code class="language-javascript">function factorial(n) {
  if (n === 0) return 1;  // 終止條件
  return n * factorial(n - 1);  // 遞迴呼叫
}
console.log(factorial(5)); // 輸出 120</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve(n)</code>，利用遞迴計算並回傳 n 的階乘（n!）。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 6 章：陣列 -->
        <div class="chapter" id="ch6">
            <h2>第 6 章：陣列 (Array)</h2>
            <p>
                陣列是一組有序資料的集合，就像購物清單。你可以使用數字索引存取陣列中的資料，並利用內建方法操作陣列。
                常用方法包括：<code class="language-javascript">push()</code>、<code class="language-javascript">pop()</code>、<code class="language-javascript">shift()</code>、<code class="language-javascript">unshift()</code>、<code class="language-javascript">slice()</code>、<code class="language-javascript">splice()</code>、<code class="language-javascript">indexOf()</code>、<code class="language-javascript">map()</code>、<code class="language-javascript">filter()</code> 與 <code class="language-javascript">reduce()</code> 等。
            </p>
            <p>
                <strong>範例：</strong>
            </p>
            <pre><code class="language-javascript">let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // "apple"
fruits.push("date");    // 陣列變為 ["apple", "banana", "cherry", "date"]
console.log(fruits.indexOf("cherry")); // 2</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，建立陣列 <code class="language-javascript">["apple", "banana", "cherry"]</code> 並回傳第一個元素。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 7 章：物件與 JSON -->
        <div class="chapter" id="ch7">
            <h2>第 7 章：物件與 JSON</h2>
            <p>
                物件用於儲存多個相關資料，就像身份證記錄姓名、年齡與地址。你可以存取、修改物件的屬性，並定義方法來操作資料。
                JSON（JavaScript Object Notation）是一種輕量級的資料交換格式，可將物件轉換成字串，方便儲存與傳輸。
            </p>
            <p>
                <strong>範例：</strong>
            </p>
            <pre><code class="language-javascript">let student = {
  name: "John",
  age: 30,
  greet: function() { return "Hello, " + this.name; }
};
console.log(student.name);            // "John"
console.log(JSON.stringify(student)); // 將物件轉換成 JSON 字串</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，建立物件 {name: "John", age: 30} 並回傳其 JSON 字串。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 8 章：字串操作 -->
        <div class="chapter" id="ch8">
            <h2>第 8 章：字串操作</h2>
            <p>
                字串用於表示文字資料，JavaScript 提供多種方法來操作字串，讓你可以檢查、轉換、分割或替換文字。
                常用方法包括：<code class="language-javascript">length</code>、<code class="language-javascript">toUpperCase()</code>、<code class="language-javascript">toLowerCase()</code>、<code class="language-javascript">slice()</code>、<code class="language-javascript">split()</code>、<code class="language-javascript">join()</code>、<code class="language-javascript">indexOf()</code>、<code class="language-javascript">includes()</code> 與 <code class="language-javascript">replace()</code>。
            </p>
            <p>
                <strong>範例：</strong>
            </p>
            <pre><code class="language-javascript">let str = "hello world";
console.log(str.length);          // 11
console.log(str.toUpperCase());   // "HELLO WORLD"
console.log(str.slice(0, 5));     // "hello"
console.log(str.split(" "));      // ["hello", "world"]</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，將字串 "hello world" 轉換為全大寫後回傳。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 9 章：錯誤處理與除錯 -->
        <div class="chapter" id="ch9">
            <h2>第 9 章：錯誤處理與除錯</h2>
            <p>
                錯誤處理能夠避免程式因錯誤而崩潰，並幫助你快速找到問題所在。你可以使用 <code class="language-javascript">try...catch</code> 捕捉錯誤，
                並利用 <code class="language-javascript">throw</code> 主動拋出錯誤來中斷不合理的執行流程。<br/>
                <strong>為何要用 break：</strong> 在 switch 陳述式中，若不使用 break，當某個 case 條件滿足後，程式會繼續執行後續所有 case，
                這稱為「落空執行」，通常會導致意外結果，因此必須使用 break 來中斷。
            </p>
            <p>
                <strong>範例一：主動拋出錯誤</strong>
            </p>
            <pre><code class="language-javascript">function checkAge(age) {
  if (age < 18) {
    throw new Error("未滿 18 歲");
  }
  return "符合資格";
}</code></pre>
            <p>
                <strong>範例二：捕捉錯誤並判斷</strong>
            </p>
            <pre><code class="language-javascript">try {
  checkAge(16);
} catch (error) {
  console.log(error.name);    // "Error"
  console.log(error.message); // "未滿 18 歲"
}</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，故意拋出一個錯誤，並用 try...catch 捕捉後回傳錯誤訊息 "意外錯誤"。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 10 章：進一步的流程控制與錯誤捕捉補充 -->
        <div class="chapter" id="ch10">
            <h2>第 10 章：進一步的流程控制與錯誤捕捉補充</h2>
            <p>
                除了基本的流程控制與錯誤處理外，本章進一步說明：
                - 為何在 switch 陳述式中必須使用 break（避免落空執行）。<br/>
                - 如何在錯誤處理中根據 <code class="language-javascript">error.name</code> 來判斷錯誤類型，進而做出不同處理。
            </p>
            <pre><code class="language-javascript">switch (day) {
  case 1:
    console.log("星期一");
    break;  // 防止落空執行
  case 2:
    console.log("星期二");
    break;
  default:
    console.log("其他");
}

try {
  throw new Error("自訂錯誤");
} catch (e) {
  if (e.name === "Error") {
    console.log("自訂錯誤");
  } else {
    console.log("其他錯誤");
  }
}</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，故意拋出一個自訂錯誤（例如 "自訂錯誤"），
                在 catch 區塊中判斷錯誤名稱，若為 "Error" 則回傳 "自訂錯誤"，否則回傳 "其他錯誤"。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 11 章：非同步與 async/await -->
        <div class="chapter" id="ch11">
            <h2>第 11 章：非同步與 async/await</h2>
            <p>
                當程式需要等待長時間操作（例如網路請求或檔案讀取）時，非同步技術可以讓程式在等待時繼續執行其他任務。
                Promise 表示一個尚未完成但未來會有結果的操作；而 async/await 語法使非同步程式碼看起來像同步程式碼，
                其中 <code class="language-javascript">await</code> 可等待 Promise 解決後再執行下一行程式碼。
            </p>
            <p>
                <strong>範例：</strong>
            </p>
            <pre><code class="language-javascript">async function fetchData() {
  try {
    let response = await fetch("https://api.example.com/data");
    let data = await response.json();
    return data;
  } catch (err) {
    console.error("錯誤：", err);
  }
}</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫 async 函式 <code class="language-javascript">solve()</code>，模擬非同步操作（無需實際請求），直接回傳字串 "done"。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 12 章：非同步進階與錯誤捕捉補充 -->
        <div class="chapter" id="ch12">
            <h2>第 12 章：非同步進階與錯誤捕捉補充</h2>
            <p>
                除了基本的 async/await，本章進一步說明如何在非同步操作中捕捉錯誤，並處理多個非同步操作的錯誤情境。
                當使用 <code class="language-javascript">await</code> 等待 Promise 時，如果該 Promise 被拒絕，錯誤會傳至 catch 區塊。
                你可以根據錯誤類型進行不同處理。
            </p>
            <p>
                <strong>範例：</strong> 模擬兩個非同步操作，其中一個故意拋出錯誤：
            </p>
            <pre><code class="language-javascript">async function processData() {
  try {
    let a = await Promise.resolve(10);
    let b = await Promise.reject(new Error("非同步錯誤"));
    return a + b;
  } catch (err) {
    return "錯誤捕捉：" + err.message;
  }
}
processData().then(console.log); // 輸出 "錯誤捕捉：非同步錯誤"
</code></pre>
            <p>
                <strong>練習題：</strong> 撰寫 async 函式 <code class="language-javascript">solve()</code>，模擬兩個非同步操作，其中第一個回傳 5，第二個故意拋出錯誤，
                使用 try...catch 捕捉後回傳錯誤訊息 "捕捉到錯誤"。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 13 章：綜合應用與專案實作 -->
        <div class="chapter" id="ch13">
            <h2>第 13 章：綜合應用與專案實作</h2>
            <p>
                當你掌握了前面所有知識後，便具備了獨立撰寫小程式的能力。此時你可以將變數、流程控制、函式、陣列、物件、字串、
                錯誤處理與非同步技術結合起來，製作一個完整應用，例如簡易計算機、記事管理系統或猜數字遊戲。
                這就像廚師利用各種食材製作一頓豐盛大餐，需要合理安排程式邏輯與資料流程。
            </p>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，回傳字串 "project completed"，模擬專案完成的成果。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>

        <!-- 第 14 章：其他必備知識與延伸資源 -->
        <div class="chapter" id="ch14">
            <h2>第 14 章：其他必備知識與延伸資源</h2>
            <p>
                這份教材可能是你的第一個接觸的程式教材，但絕對不會是最後一份！<br/>
                除了上述內容外，還有一些進階概念對撰寫健全、可維護的程式非常重要，例如：
            </p>
            <ul>
                <li>
                    <strong>作用域與閉包：</strong> 了解變數的存取範圍以及函式如何捕捉外部變數，有助於保護資料與建立私有變數。
                </li>
                <li>
                    <strong>Hoisting（提升）：</strong> 變數與函式宣告會被提升至作用域頂部，但初始化不會，可能導致未賦值錯誤。
                </li>
                <li>
                    <strong>原型與繼承：</strong> 物件透過原型鏈共享屬性與方法，這是 JavaScript 繼承機制的基礎。
                </li>
                <li>
                    <strong>模組化：</strong> 使用 ES6 模組（import/export）將程式拆分成獨立單元，提高程式結構與重用性。
                </li>
                <li>
                    <strong>事件處理：</strong> 在瀏覽器中如何捕捉並處理使用者互動（如點擊、輸入等），是前端開發的重要基礎。
                </li>
            </ul>
            <p>
                此外，持續參考以下延伸學習資源，能幫助你更深入瞭解 JavaScript：
            </p>
            <p>
                <strong>延伸學習資源：</strong><br/>
                <a href="https://developer.mozilla.org/zh-TW/" target="_blank">MDN Web Docs</a>｜
                <a href="https://stackoverflow.com/" target="_blank">Stack Overflow</a>｜
                <a href="https://www.freecodecamp.org/" target="_blank">FreeCodeCamp</a>
            </p>
            <ul>
                <li>
                    <strong>自學網頁の嬰兒教材：JavaScript（一）—— 幫衣服工廠做個好用表單</strong>：
                    <a target="_blank" href="https://codelove.tw/@howtomakeaturn/course/l3j5xk">https://codelove.tw/@howtomakeaturn/course/l3j5xk</a>
                </li>
                <li>
                    <strong>(影片)【javascript】3小時初學者教學</strong>：
                    <a target="_blank" href="https://www.youtube.com/watch?v=yZwlW5INhgk">https://www.youtube.com/watch?v=yZwlW5INhgk</a>
                </li>
            </ul>
            <p>
                <strong>練習題：</strong> 撰寫函式 <code class="language-javascript">solve()</code>，回傳一個 JSON 字串，
                表示包含 "MDN"、"Stack Overflow" 與 "FreeCodeCamp" 三個推薦資源的陣列。
            </p>
            <p><a href="#practice" class="jump-btn">前往練習區</a></p>
        </div>
    </div>
</main>
<!-- 線上練習系統 -->
<section id="practice" class="editor-section">
    <h2>線上練習系統</h2>
    <label for="exerciseSelect">選擇練習題：</label>
    <select id="exerciseSelect"></select>
    <br/><br/>
    <div id="exerciseDesc" style="margin-bottom:1em; color:#333;"></div>
    <!-- Ace Editor 編輯器容器 -->
    <div id="editor"></div>
    <div class="button-group">
        <button id="runTestBtn">送出批改</button>
        <button id="showAnswerBtn">看答案</button>
    </div>
    <div id="testResult" class="test-result"></div>
</section>
<!-- 回到頂端按鈕 -->
<button id="toTopBtn" onclick="scrollToTop()">回到頂端</button>
<footer>
    <p style="text-align:center; color:#666;">© 2025 HazelnutParadise. All rights reserved.</p>
</footer>
<script>
    // 回到頂端按鈕功能：平滑滾回頁首
    function scrollToTop() {
        window.scrollTo({top: 0, behavior: 'smooth'});
    }
    window.addEventListener("scroll", function() {
        const btn = document.getElementById("toTopBtn");
        if (window.scrollY > 200) {
            btn.style.display = "block";
        } else {
            btn.style.display = "none";
        }
    });

    // 練習題資料：與章節對應（0~14）
    const exercises = [
        {
            id: "ch0_prep",
            title: "第 0 章練習：環境檢查",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，回傳字串 <code>"Hello World!"</code> 以確認開發環境正常。
        `,
            template: `function solve() {
  // 請撰寫程式，回傳 "Hello World!"
}`,
            answer: `function solve() {
  // 回傳字串 "Hello World!"
  return "Hello World!";
}`,
            testCases: [
                {
                    name: "回傳 'Hello World!'",
                    input: [],
                    expected: "Hello World!"
                }
            ]
        },
        {
            id: "ch1_vars",
            title: "第 1 章練習：變數與資料型態",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，在函式中宣告一個 let 變數（值為 100）與一個 const 常數（值為 200），
          然後回傳字串 <code>"let: 100, const: 200"</code>。
        `,
            template: `function solve() {
  // 請宣告一個 let 變數和一個 const 常數，並回傳指定字串
}`,
            answer: `function solve() {
  let a = 100;
  const b = 200;
  return "let: " + a + ", const: " + b;
}`,
            testCases: [
                {
                    name: "回傳 'let: 100, const: 200'",
                    input: [],
                    expected: "let: 100, const: 200"
                }
            ]
        },
        {
            id: "ch2_bmi",
            title: "第 2 章練習：BMI 計算",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve(height, weight)</code>，根據公式 <code>BMI = weight / ((height/100)²)</code> 計算 BMI 並回傳數值結果。
        `,
            template: `function solve(height, weight) {
  // 請在此撰寫計算 BMI 的程式
}`,
            answer: `function solve(height, weight) {
  const meter = height / 100;
  return weight / (meter * meter);
}`,
            testCases: [
                {
                    name: "170, 65 => 約22.49",
                    input: [170, 65],
                    expected: 22.49
                },
                {
                    name: "180, 70 => 約21.60",
                    input: [180, 70],
                    expected: 21.60
                }
            ]
        },
        {
            id: "ch3_grade",
            title: "第 3 章練習：分數等級判斷",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve(score)</code>，根據分數回傳等級：分數 ≥ 90 回傳 "A"，80–89 回傳 "B"，70–79 回傳 "C"，60–69 回傳 "D"，其他回傳 "不及格"。
        `,
            template: `function solve(score) {
  // 請在此撰寫分數等級判斷邏輯
}`,
            answer: `function solve(score) {
  if (score >= 90) return "A";
  else if (score >= 80) return "B";
  else if (score >= 70) return "C";
  else if (score >= 60) return "D";
  else return "不及格";
}`,
            testCases: [
                {
                    name: "score=95 => 'A'",
                    input: [95],
                    expected: "A"
                },
                {
                    name: "score=70 => 'C'",
                    input: [70],
                    expected: "C"
                },
                {
                    name: "score=50 => '不及格'",
                    input: [50],
                    expected: "不及格"
                }
            ]
        },
        {
            id: "ch4_square",
            title: "第 4 章練習：函式與箭頭函式",
            description: `
          <strong>題目：</strong><br/>
          撰寫箭頭函式 <code>solve(x)</code>，計算並回傳 x 的平方，請使用多行箭頭函式語法。
        `,
            template: `const solve = (x) => {
  // 請在此撰寫程式
}`,
            answer: `const solve = (x) => {
  const result = x * x;
  return result;
};`,
            testCases: [
                {
                    name: "x=5 => 25",
                    input: [5],
                    expected: 25
                }
            ]
        },
        {
            id: "ch5_factorial",
            title: "第 5 章練習：遞迴與階乘",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve(n)</code>，利用遞迴計算並回傳 n 的階乘（n!）。
        `,
            template: `function solve(n) {
  // 請在此撰寫遞迴計算階乘的程式
}`,
            answer: `function solve(n) {
  if (n === 0) return 1;
  return n * solve(n - 1);
}`,
            testCases: [
                {
                    name: "n=5 => 120",
                    input: [5],
                    expected: 120
                }
            ]
        },
        {
            id: "ch6_array",
            title: "第 6 章練習：陣列操作",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，建立陣列 <code>["apple", "banana", "cherry"]</code> 並回傳第一個元素。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  const arr = ["apple", "banana", "cherry"];
  return arr[0];
}`,
            testCases: [
                {
                    name: "回傳 'apple'",
                    input: [],
                    expected: "apple"
                }
            ]
        },
        {
            id: "ch7_object",
            title: "第 7 章練習：物件與 JSON",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，建立物件 {name: "John", age: 30} 並回傳其 JSON 字串。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  const obj = {name: "John", age: 30};
  return JSON.stringify(obj);
}`,
            testCases: [
                {
                    name: "回傳 JSON 字串",
                    input: [],
                    expected: '{"name":"John","age":30}'
                }
            ]
        },
        {
            id: "ch8_string",
            title: "第 8 章練習：字串操作",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，將字串 "hello world" 轉換為全大寫後回傳。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  return "hello world".toUpperCase();
}`,
            testCases: [
                {
                    name: "回傳 'HELLO WORLD'",
                    input: [],
                    expected: "HELLO WORLD"
                }
            ]
        },
        {
            id: "ch9_error",
            title: "第 9 章練習：錯誤處理",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，故意拋出一個錯誤，並用 try...catch 捕捉後回傳錯誤訊息 "意外錯誤"。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  try {
    throw new Error("意外錯誤");
  } catch(e) {
    return e.message;
  }
}`,
            testCases: [
                {
                    name: "回傳 '意外錯誤'",
                    input: [],
                    expected: "意外錯誤"
                }
            ]
        },
        {
            id: "ch10_error_advance",
            title: "第 10 章練習：進一步的流程控制與錯誤捕捉補充",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，故意拋出一個自訂錯誤（例如 "自訂錯誤"），
          在 catch 區塊中判斷錯誤名稱，若為 "Error" 則回傳 "自訂錯誤"，否則回傳 "其他錯誤"。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  try {
    // 主動拋出自訂錯誤
    throw new Error("自訂錯誤");
  } catch(e) {
    if (e.name === "Error") {
      return "自訂錯誤";
    } else {
      return "其他錯誤";
    }
  }
}`,
            testCases: [
                {
                    name: "回傳 '自訂錯誤'",
                    input: [],
                    expected: "自訂錯誤"
                }
            ]
        },
        {
            id: "ch11_async",
            title: "第 11 章練習：非同步與 async/await",
            description: `
          <strong>題目：</strong><br/>
          撰寫 async 函式 <code>solve()</code>，使用 async/await 模擬非同步操作，直接回傳字串 "done"。
        `,
            template: `async function solve() {
  // 請在此撰寫程式
}`,
            answer: `async function solve() {
  return "done";
}`,
            testCases: [
                {
                    name: "回傳 'done'",
                    input: [],
                    expected: "done"
                }
            ]
        },
        {
            id: "ch12_async_advance",
            title: "第 12 章練習：非同步進階與錯誤捕捉補充",
            description: `
          <strong>題目：</strong><br/>
          撰寫 async 函式 <code>solve()</code>，模擬兩個非同步操作：第一個操作回傳 5，第二個操作故意拋出錯誤，
          使用 try...catch 捕捉後回傳錯誤訊息 "捕捉到錯誤"。
        `,
            template: `async function solve() {
  // 請在此撰寫程式
}`,
            answer: `async function solve() {
  try {
    let a = await Promise.resolve(5);
    let b = await Promise.reject(new Error("非同步錯誤"));
    return a + b;
  } catch (e) {
    return "捕捉到錯誤";
  }
}`,
            testCases: [
                {
                    name: "回傳 '捕捉到錯誤'",
                    input: [],
                    expected: "捕捉到錯誤"
                }
            ]
        },
        {
            id: "ch13_project",
            title: "第 13 章練習：綜合應用與專案實作",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，回傳字串 "project completed"，模擬專案完成的成果。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  return "project completed";
}`,
            testCases: [
                {
                    name: "回傳 'project completed'",
                    input: [],
                    expected: "project completed"
                }
            ]
        },
        {
            id: "ch14_resources",
            title: "第 14 章練習：其他必備知識與延伸資源",
            description: `
          <strong>題目：</strong><br/>
          撰寫函式 <code>solve()</code>，回傳一個 JSON 字串，表示包含 "MDN"、"Stack Overflow" 與 "FreeCodeCamp" 三個推薦資源的陣列。
        `,
            template: `function solve() {
  // 請在此撰寫程式
}`,
            answer: `function solve() {
  return JSON.stringify(["MDN", "Stack Overflow", "FreeCodeCamp"]);
}`,
            testCases: [
                {
                    name: "回傳資源陣列的 JSON 字串",
                    input: [],
                    expected: '["MDN","Stack Overflow","FreeCodeCamp"]'
                }
            ]
        }
    ];

    // 初始化下拉選單
    const exerciseSelect = document.getElementById("exerciseSelect");
    const exerciseDesc = document.getElementById("exerciseDesc");
    const testResult = document.getElementById("testResult");

    exercises.forEach(ex => {
        const option = document.createElement("option");
        option.value = ex.id;
        option.textContent = ex.title;
        exerciseSelect.appendChild(option);
    });

    // 預設載入第一個練習題
    let currentExercise = exercises[0];
    exerciseDesc.innerHTML = currentExercise.description;

    // 初始化 Ace Editor
    const aceEditor = ace.edit("editor");
    aceEditor.setTheme("ace/theme/monokai");
    aceEditor.session.setMode("ace/mode/javascript");
    aceEditor.setFontSize(14);
    aceEditor.setValue(currentExercise.template, -1);

    // 當下拉選單改變時更新題目內容
    exerciseSelect.addEventListener("change", () => {
        const selectedId = exerciseSelect.value;
        currentExercise = exercises.find(ex => ex.id === selectedId);
        exerciseDesc.innerHTML = currentExercise.description;
        aceEditor.setValue(currentExercise.template, -1);
        testResult.innerHTML = "";
    });

    // 點擊「送出批改」按鈕時執行測試
    document.getElementById("runTestBtn").addEventListener("click", async () => {
        const userCode = aceEditor.getValue();
        const results = await runTests(currentExercise.testCases, userCode);
        renderTestResults(results);
    });

    // 「看答案」按鈕：詢問確認後顯示正確答案
    document.getElementById("showAnswerBtn").addEventListener("click", () => {
        if (confirm("確定要顯示答案？這將覆蓋你目前的程式碼。")) {
            aceEditor.setValue(currentExercise.answer, -1);
        }
    });

    // 執行測試函式：用 eval() 執行使用者程式，再根據測試案例比對結果
    async function runTests(testCases, userCode) {
        const results = [];
        let solveFn;
        try {
            eval(userCode);  // 假設使用者在程式碼中定義了 solve 函式
            solveFn = solve;
        } catch (err) {
            return [{
                name: "程式碼錯誤",
                passed: false,
                error: err.message
            }];
        }
        for (let tc of testCases) {
            let passed = false;
            let error = null;
            let actual;
            try {
                let result = solveFn(...tc.input);
                // 若回傳值為 Promise，需 await
                if (result instanceof Promise) {
                    actual = await result;
                } else {
                    actual = result;
                }
                passed = compareResult(actual, tc.expected);
            } catch (err) {
                error = err.message;
            }
            results.push({
                name: tc.name,
                passed,
                expected: tc.expected,
                actual,
                error
            });
        }
        return results;
    }

    // 比對結果，若為數字則允許微小誤差
    function compareResult(a, b) {
        if (typeof a === "number" && typeof b === "number") {
            return Math.abs(a - b) < 0.01;
        }
        return JSON.stringify(a) === JSON.stringify(b);
    }

    // 顯示測試結果
    function renderTestResults(results) {
        if (!results || results.length === 0) {
            testResult.innerHTML = "<p>沒有測試結果</p>";
            return;
        }
        let passCount = 0;
        let html = "";
        results.forEach(r => {
            if (r.passed) passCount++;
            if (r.error) {
                html += `<div class="failed"><strong>${r.name}</strong>：執行錯誤<br/>錯誤訊息：${r.error}</div>`;
            } else if (r.passed) {
                html += `<div class="passed"><strong>${r.name}</strong>：通過</div>`;
            } else {
                html += `<div class="failed"><strong>${r.name}</strong>：失敗<br/>預期：${JSON.stringify(r.expected)}<br/>實際：${JSON.stringify(r.actual)}</div>`;
            }
        });
        html = `<p>總測試：${results.length}，通過：${passCount}，失敗：${results.length - passCount}</p>` + html;
        testResult.innerHTML = html;
    }
</script>
</body>
</html>
