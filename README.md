# CIE 1931 / 1976 色域分析與雙螢幕色彩對齊工具箱 (Color Gamut Studio)

本專案是一個全功能互動式色彩學研究與顯示器對齊工具箱。我們已將專案中功能分散的多個工具整合成一個現代化的單頁儀表板：**`ColorGamutStudio.html`**，同時保留了歷史版本的獨立 HTML 檔案供參考。

---

## 🚀 核心入口：[ColorGamutStudio.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/ColorGamutStudio.html)

**Color Gamut Studio (v2.0 Ultimate)** 是本專案的整合控制台，採用精美的深色模式設計，並透過多頁籤（Tab）結構整合了所有功能，具備以下三大特點：

*   **跨分頁資料協同 (Inter-Tab Synergy)**：
    *   **LED 傳送**：在 Tab 1 中，設定完紅綠藍 LED 變動波長範圍後，可一鍵將波長中位數三原色座標「傳送至雙螢幕配置」做為 Screen A 的基準點。
    *   **交集傳送**：在 Tab 2 中，互動式 Canvas 計算出的最佳交集色域（對齊目標），可一鍵「傳送至標準色域比對」，做為 Tab 1 比對圖表中的 Dotted Cyan 邊界，方便評估涵蓋比例。
*   **雙重色彩校正對齊引擎**：
    *   **標準 D65/定量白點對準**：輸入自定義白點與總亮度，反推相對亮度並計算 CSC 對照矩陣。
    *   **NovaStar 商業模式**：以顯示器原生白點（$R+G+B$ 滿載能量）為白平衡基準，保持亮度不被下壓，並套用 `Gamut Clip` 負數裁切與 `Sum-to-1` 歸一化，復刻商業硬體晶片色彩校正暫存器演算法。
*   **極致互動體驗**：
    *   **動態 Canvas 拖曳**：在色度圖上，可直接使用滑鼠或觸控拖曳 Screen A/B 的原色頂點，即時重算目標交集與 CSC 矩陣。
    *   **滑輪滾動調值**：所有數值輸入框均支援滑鼠滾輪上下滾動，滾輪滑動即可微調座標（步進 0.001）或亮度，無縫體驗。

---

## 📂 專案檔案結構

| 檔案名稱 | 說明 | 狀態 |
| :--- | :--- | :--- |
| **[ColorGamutStudio.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/ColorGamutStudio.html)** | **本專案主入口**。整併 LED 分析、Plotly 繪圖、互動拖曳 Canvas、D65/NovaStar 雙引擎與數學原理。 | 🌟 推薦使用 |
| **[CIE 1931 色域與波長範圍分析工具.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/CIE%201931%20%E8%89%B2%E5%9F%9F%E8%88%87%E6%B3%A2%E9%95%B7%E7%AF%84%E5%9C%8D%E5%88%86%E6%9E%90%E5%B7%A5%E5%85%B7.html)** | 獨立 LED 分析工具 (v1.7.1)。支援波長容差、黑體軌跡、MacAdam 橢圓、主波長分析及 PWM 求解。 | 歷史備份 |
| **[Dual Display Gamut Matcher 1.4.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/Dual%20Display%20Gamut%20Matcher%201.4.html)** | 獨立雙螢幕對齊工具 (v1.4)。支援 Canvas 頂點拖曳、目標白點反算、與原始發光矩陣展示。 | 歷史備份 |
| **[Dual Display Gamut Matcher.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/Dual%20Display%20Gamut%20Matcher.html)** | 獨立雙螢幕對齊工具 (v1.3)。支援 Canvas 拖曳、目標白點反算、無原始矩陣展示。 | 歷史備份 |
| **[Phase1_CoreEngine.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/Phase1_CoreEngine.html)** | 單一螢幕目標色域對齊與 $3 \times 3$ CSC 矩陣驗證器（極簡版）。 | 歷史備份 |
| **[Phase7_CommercialEngine.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/Phase7_CommercialEngine.html)** | 獨立 NovaStar 生產級對齊引擎。支援原生白點校正與負值裁剪歸一化（無 Canvas 拖曳）。 | 歷史備份 |
| **[LED 色温度リニア調整計算ツール_v3.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/LED%20%E8%89%B2%E6%B8%A9%E5%BA%A6%E3%83%AA%E3%83%8B%E3%82%A2%E8%AA%BF%E6%95%B4%E8%A8%88%E7%AE%97%E3%83%84%E3%83%BC%E3%83%AB_v3.html)** | 獨立 LED 色溫線性調整工具 (v3)。React 實作，支援中英日三語，能計算由基準色溫變換至目標色溫時，硬體端 R/G/B 通道的線性衰減比率。 | 獨立工具 |


---

## 🧮 核心色彩科學公式

### 1. xyY $\rightleftharpoons$ XYZ 座標轉換
色彩轉換計算皆在線性強度的 XYZ 絕對空間進行：
$$X = \frac{x \cdot Y}{y}$$
$$Y = Y$$
$$Z = \frac{(1 - x - y) \cdot Y}{y}$$

### 2. 白平衡反算 (White Point Balance)
解出合成目標白點三通道所需的發光亮度權重：
$$\begin{bmatrix} X_w \\ Y_w \\ Z_w \end{bmatrix} = 
\begin{bmatrix} 
x_r/y_r & x_g/y_g & x_b/y_b \\ 
1 & 1 & 1 \\ 
(1-x_r-y_r)/y_r & (1-x_g-y_g)/y_g & (1-x_b-y_b)/y_b 
\end{bmatrix} 
\begin{bmatrix} Y_R \\ Y_G \\ Y_B \end{bmatrix}$$

### 3. 校正矩陣生成 (Color Space Conversion)
$$CSC = M_{orig}^{-1} \times M_{tgt}$$

---

## 🛠 快速上手

1.  開啟 [ColorGamutStudio.html](file:///g:/%E6%88%91%E7%9A%84%E9%9B%B2%E7%AB%AF%E7%A1%AC%E7%A2%9F/%E5%80%8B%E4%BA%BA%E8%B3%87%E6%96%99%E5%A4%BE/%E5%AD%B8%E7%BF%92%E8%B3%87%E6%96%99/%E8%89%B2%E5%BD%A9%E5%AD%B8/ColorGamutTool/ColorGamutStudio.html)。
2.  在 **LED & 色域分析** 頁籤中，調整波長範圍、目標與實測白點，確認 PWM 混光比例與涵蓋率。若欲對齊，點擊右上角「傳送至螢幕對齊」。
3.  在 **雙螢幕色域對齊** 頁籤中，可直接用滑鼠拖拉右側畫布端點，下方即時顯示原始矩陣 $M_A/M_B$ 與最終寫入硬體的 CSC 校正矩陣。

*註：建議保持網際網路連線以順利加載 Tailwind、Plotly 與 KaTeX 公式渲染服務。*
