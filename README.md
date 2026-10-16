# 📈 InvestSim Pro - 金融投資模擬與智慧學習平台

> **臺中市立臺中工業高級中等學校 資訊科專題實作成果**  
> 🔗 **Live Demo：** [https://quiet-babka-195e95.netlify.app/](https://quiet-babka-195e95.netlify.app/)

![Tech Stack](https://img.shields.io/badge/Frontend-HTML5%20%7C%20TailwindCSS%20%7C%20JS(ES6)-blue)
![API](https://img.shields.io/badge/API-Binance%20WebSocket%20%7C%20Gemini%20LLM-emerald)
![License](https://img.shields.io/badge/License-MIT-orange)

## 📌 專案簡介
隨著數位理財普及，初學者常因缺乏真實市場經驗與風險意識而蒙受損失。**InvestSim Pro** 是一套專為金融素養教育設計的無風險擬真交易與學習平台，結合 **WebSocket 即時行情**、**量化風險引擎 (Quant Engine)** 與 **生成式 AI (Google Gemini LLM)**，提供具備體驗式學習理論（Experiential Learning）的數位教育工具。

---

## 🚀 核心技術亮點

1. **WebSocket 秒級行情串流 (Real-time Market Streaming)**
   - 拋棄傳統 REST API 輪詢（Polling），直連 **Binance WebSocket Server (`wss://`)**，實現毫秒級價格跳動與數據監控。
2. **量化風險分析引擎 (Quant Risk Engine)**
   - 自主開發演算法即時計算 **夏普指數 (Sharpe Ratio)** 與 **最大回撤 (Max Drawdown, MDD)**，將機構級風險指標引入教育平台。
3. **生成式 AI 智慧理財診斷 (Gemini LLM Integration)**
   - 打包使用者之資產配置、ROI、MDD 與 Sharpe Ratio 數據為結構化 JSON，透過 API 送交 **Google Gemini 1.5 Flash** 進行個人化風險診斷。
4. **遊戲化學習與資料狀態持久化 (Gamification & Fault Tolerance)**
   - 整合金融知識測驗、排行榜與交易履歷；採用 `localStorage` 搭配自研 Sanitizer 狀態修復機制，防止資料結構衝突。

---

## 🏗️ 系統架構圖 (System Architecture)

```mermaid
graph TD
    A[使用者介面 Frontend UI] -->|1. 訂閱秒級行情| B(Binance WebSocket Server)
    A -->|2. 打包持股與量化數據 JSON| C(Google Gemini LLM API)
    A -->|3. 本機資料狀態備份/修復| D[(LocalStorage & Sanitizer)]
    
    B -->|即時價格/漲跌幅推播| A
    C -->|個人化診斷報告| A
