# 三角函數視覺化教學 (Trigonometric Functions Visualization)

[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

一個以互動式 3D 動畫呈現三角函數（正弦、餘弦、正切）數學原理的網頁教學工具，使用 [Three.js](https://threejs.org/) 開發，適合學生、教師及任何對數學感興趣的人。

🔗 **線上展示**：<https://trigonometric.will.com.tw/>

---

## 目錄

- [專案簡介](#專案簡介)
- [功能特色](#功能特色)
- [操作說明](#操作說明)
- [數學原理](#數學原理)
  - [單位圓與角度](#單位圓與角度)
  - [正弦函數 sin(θ)](#正弦函數-sinθ)
  - [餘弦函數 cos(θ)](#餘弦函數-cosθ)
  - [正切函數 tan(θ)](#正切函數-tanθ)
  - [弧度與角度的轉換](#弧度與角度的轉換)
  - [畢氏定理與三角恆等式](#畢氏定理與三角恆等式)
- [技術架構](#技術架構)
- [如何在本地端執行](#如何在本地端執行)
- [參考資料](#參考資料)
- [授權聲明](#授權聲明)

---

## 專案簡介

本專案是一個純前端、免安裝的互動式三角函數視覺化教學頁面。透過旋轉的點在單位圓上移動，即時描繪出正弦波（sin）、餘弦波（cos）以及正切線（tan），幫助學習者直觀地理解這三種三角函數的幾何意義與週期性質。

傳統的三角函數教學往往依賴靜態圖表與公式，難以讓學生真正感受「角度變化」與「函數值」之間的動態關係。本工具透過即時動畫與互動拖曳，讓抽象的數學概念變得具體可感。

---

## 功能特色

- 🌀 **動態旋轉動畫**：一個黃色星星點沿單位圓旋轉，即時展示角度的變化。
- 📈 **三角函數波形**：正弦波（紅色）與餘弦波（藍色）從圓的右側即時延伸繪製。
- 📐 **直角三角形展示**：動態繪製課本上的對邊（紅色）、鄰邊（藍色）及斜邊（灰色），對應 sin、cos 的幾何定義。
- 🟢 **正切線視覺化**：綠色線段沿單位圓右側的垂直切線牆延伸，直觀展示 tan 值的幾何意義。
- 🔵 **弧長標示**：以紫色弧線凸顯目前角度對應的弧長（弧度）。
- 🏷️ **即時數據標籤**：畫面上動態顯示當前角度（θ）、斜邊長、水平分量（x）、垂直分量（y）及正切值。
- 🖱️ **互動拖曳**：可直接拖曳黃色星星點，手動控制旋轉角度。
- 🔍 **縮放功能**（桌機）：滑鼠滾輪可縮放畫面，方便觀察細節。
- ⏯️ **速度控制**：右上角提供「暫停」、「慢速」、「快速」三個按鈕，預設為慢速。
- 📱 **響應式設計**：自動適應桌機與手機版面配置。

---

## 操作說明

| 操作 | 效果 |
|------|------|
| 自動播放 | 頁面載入後，星星點預設以慢速沿圓自動旋轉 |
| 拖曳星星 | 滑鼠（或手指）按住黃色星星可手動拖曳，控制角度 |
| 滾輪縮放 | 桌機上可用滑鼠滾輪放大或縮小畫面 |
| 暫停 / 慢速 / 快速 | 點選右上角按鈕切換動畫速度 |

---

## 數學原理

### 單位圓與角度

**單位圓（Unit Circle）** 是以原點為圓心、半徑為 1 的圓（本動畫中半徑 `R = 10`，以利視覺呈現，數學意義相同）。

在標準座標系中，從正 x 軸出發，**逆時針**旋轉的角度為正角度。角度 θ 可以用**度（degree）**或**弧度（radian）**表示：

$$\theta_{\text{rad}} = \frac{\theta_{\text{deg}} \times \pi}{180}$$

單位圓上任意一點 P 的座標為：

$$P = (\cos\theta,\ \sin\theta)$$

這正是三角函數的幾何定義之根本。

---

### 正弦函數 sin(θ)

$$\sin(\theta) = \frac{\text{對邊（opposite）}}{\text{斜邊（hypotenuse）}} = \frac{y}{r}$$

在單位圓中（r = 1），sin(θ) 即等於點 P 的 **y 座標**。

- 值域：$[-1, 1]$
- 週期：$2\pi$（360°）
- 特殊值：

| θ（度） | θ（弧度） | sin(θ) |
|---------|-----------|--------|
| 0°      | 0         | 0      |
| 30°     | π/6       | 1/2    |
| 45°     | π/4       | √2/2   |
| 60°     | π/3       | √3/2   |
| 90°     | π/2       | 1      |
| 180°    | π         | 0      |
| 270°    | 3π/2      | −1     |
| 360°    | 2π        | 0      |

正弦函數是一條平滑的**S 型波浪曲線**，在動畫中以 **紅色** 曲線表示。

---

### 餘弦函數 cos(θ)

$$\cos(\theta) = \frac{\text{鄰邊（adjacent）}}{\text{斜邊（hypotenuse）}} = \frac{x}{r}$$

在單位圓中（r = 1），cos(θ) 即等於點 P 的 **x 座標**。

- 值域：$[-1, 1]$
- 週期：$2\pi$（360°）
- cos(θ) 與 sin(θ) 的相位差為 90°（π/2 弧度）：

$$\cos(\theta) = \sin\!\left(\theta + \frac{\pi}{2}\right)$$

餘弦函數在動畫中以 **藍色** 曲線表示。

---

### 正切函數 tan(θ)

$$\tan(\theta) = \frac{\text{對邊}}{\text{鄰邊}} = \frac{\sin(\theta)}{\cos(\theta)} = \frac{y}{x}$$

**幾何意義**：在單位圓中，從原點出發的射線與 $x = 1$ 的垂直切線牆（tangent line）相交，交點的 y 座標即為 tan(θ)。動畫中以 **綠色** 線段表示。

- 值域：$(-\infty, +\infty)$（實數全域）
- 週期：$\pi$（180°）
- 當 θ = 90° 或 270°（cos θ = 0）時，tan(θ) **無定義**（趨近正負無窮大）。

---

### 弧度與角度的轉換

弧度制是更自然的角度表示方式，因為它直接對應**弧長**：

$$\text{弧長} = r \times \theta_{\text{rad}}$$

在半徑為 r 的圓中，弧度 θ 對應的弧長為 rθ。動畫中以 **紫色弧線** 標示當前角度所對應的弧長。

轉換關係：

| 角度 | 弧度 |
|------|------|
| 180° | π    |
| 360° | 2π   |
| 1°   | π/180 ≈ 0.01745 |
| 1 rad | ≈ 57.296° |

---

### 畢氏定理與三角恆等式

基於畢氏定理（Pythagorean theorem），任何角度 θ 均滿足最重要的三角恆等式：

$$\sin^2(\theta) + \cos^2(\theta) = 1$$

這在幾何上意味著：單位圓上的點 $(\cos\theta, \sin\theta)$ 到原點的距離永遠等於 1。

其他常用恆等式：

$$\tan(\theta) = \frac{\sin(\theta)}{\cos(\theta)}$$

$$1 + \tan^2(\theta) = \sec^2(\theta)$$

$$\sin(2\theta) = 2\sin(\theta)\cos(\theta)$$

$$\cos(2\theta) = \cos^2(\theta) - \sin^2(\theta)$$

---

## 技術架構

| 技術 | 說明 |
|------|------|
| **HTML5 / CSS3** | 頁面結構與樣式，包含響應式佈局 |
| **JavaScript (ES6+)** | 動畫邏輯、互動事件處理 |
| **[Three.js r128](https://threejs.org/)** | 3D 渲染引擎，用於繪製所有幾何物件與波形曲線 |
| **OrthographicCamera** | 正交相機確保投影不失真，忠實呈現幾何關係 |
| **WebGL** | 瀏覽器原生 GPU 加速渲染 |

本專案為**純前端單頁應用**，無需任何後端伺服器，所有程式碼皆在 `index.html` 中。

---

## 如何在本地端執行

由於本專案為純靜態 HTML，只需一個本地 HTTP 伺服器即可：

**方法一：使用 Python**

```bash
# Python 3
python -m http.server 8080
# 然後在瀏覽器開啟 http://localhost:8080
```

**方法二：使用 Node.js (npx)**

```bash
npx serve .
```

**方法三：使用 VS Code**

安裝 [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) 擴充功能，右鍵點選 `index.html` → **Open with Live Server**。

> ⚠️ 直接以 `file://` 開啟可能因瀏覽器安全限制導致部分功能無法運作。

---

## 參考資料

以下為本專案數學內容的優質可靠參考來源：

### 教科書與學術資源

1. **Khan Academy - 三角函數**
   - 提供從基礎到進階的三角函數互動教程，包含大量視覺化練習。
   - 🔗 <https://www.khanacademy.org/math/trigonometry>

2. **3Blue1Brown - "Essence of trigonometry"**
   - Grant Sanderson 製作的高品質數學視覺化影片系列，直觀解釋三角函數的本質。
   - 🔗 <https://www.youtube.com/@3blue1brown>

3. **Paul's Online Math Notes - Trigonometry**
   - 由德克薩斯州 Lamar 大學 Paul Dawkins 教授維護，提供詳細的數學推導與範例。
   - 🔗 <https://tutorial.math.lamar.edu/Classes/CalcI/TrigFcns.aspx>

4. **Wolfram MathWorld - Trigonometric Functions**
   - Wolfram Research 維護的數學百科全書，提供嚴謹的數學定義與性質。
   - 🔗 <https://mathworld.wolfram.com/TrigonometricFunctions.html>

5. **Wikipedia - Trigonometric functions**
   - 涵蓋三角函數的歷史、定義、性質、恆等式及應用。
   - 🔗 <https://en.wikipedia.org/wiki/Trigonometric_functions>

6. **Wikipedia - Unit circle**
   - 詳細說明單位圓的定義及其與三角函數的關係。
   - 🔗 <https://en.wikipedia.org/wiki/Unit_circle>

### 工具與技術文件

7. **Three.js 官方文件**
   - 本專案使用的 3D 渲染函式庫文件。
   - 🔗 <https://threejs.org/docs/>

8. **MDN Web Docs - Math.sin() / Math.cos() / Math.tan()**
   - JavaScript 內建三角函數的 API 說明。
   - 🔗 <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sin>

---

## 授權聲明

本專案採用 [MIT 授權條款](LICENSE)。

```
MIT License

Copyright (c) 2025 Will 保哥

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

*本工具由 [Will 保哥](https://blog.miniasp.com/) 開發，歡迎自由使用、修改與分享。*
