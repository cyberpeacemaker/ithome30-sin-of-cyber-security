Sure! Here's your text translated into Traditional Chinese, with the technical terms kept in English for the first time:

---

## 電腦發展過程的關鍵奠基石

這裡介紹幾個構成當代電腦雛形的重要節點。

### 獨立電腦 (1940年代)

第一台真正的電子電腦 **ENIAC (Electronic Numerical Integrator and Computer)** 是在1940年代開發的，並且標誌著計算歷史中的一個關鍵時刻。它是一台龐大、房間大小的機器，能夠每秒進行數千次的運算。

當時，使用者必須將程式打孔在實體卡片上，並將整批卡片交給系統操作員處理——這是一個緩慢且非互動式的體驗。想改變程序需透過對物理硬體重新接線的方式

---

### 存儲程式概念 (1945年)

在1945年，**John von Neumann** 在他的報告《First Draft of a Report on the EDVAC》中提出了 **存儲程式概念（stored-program concept）**。這一模型成為了現代計算的基礎。

核心概念：

* **程序指令 (program instructions)** 和 **數據 (data)** 都存儲在同一記憶體中。
* **CPU** 以抓取數據的方式抓取指令。
* 電腦可以通過將新程式碼載入記憶體來 **重編程 (reprogrammed)**，不再像ENIAC需要重新接線。

這一創新大大提高了靈活性，並為互動式計算鋪平了道路。

---

### 分時系統(1961年)

**分時系統 (Compatible Time-Sharing SystemS)** 是在1961年由麻省理工學院（MIT）開發的，它是第一批允許 **多使用者 (multiple users)** 同時訪問單一電腦的操作系統之一，通過將 **CPU** 時間分配給不同的使用者來實現——這個概念被稱為 **時間共享（time-sharing）**。

這一變革取代了緩慢的批次處理，使得 **互動計算 (interactive computing)** 成為可能，改善了系統資源的利用和使用者體驗，讓使用者能夠透過終端(terminals)跟電腦互動。

---

## 資訊安全的發展嘗試

隨著電腦的發展，安全性的意義也開始浮出，這裡介紹早期學者的對資安的一些研究嘗試。

### Bell–LaPadula 模型與基本安全定理 (1970年代)

由 **David Elliott Bell** 和 **Leonard J. LaPadula** 為美國國防部開發的 **Bell–LaPadula model** 是一種專注於 **機密性 (confidentiality)** 的正式 **訪問控制模型 (access control model)**。

#### 核心概念：

* **主體 (Subjects)**：使用者、進程
* **對象 (Objects)**：檔案、資料庫
* **安全等級 (Security levels)**：未分類、機密、秘密、絕密

#### 主要規則：

* **簡單安全性屬性 (Simple Security Property)** （無法向上讀取）：使用者無法讀取其許可等級以上的數據。
* **\*屬性 (Star Security Property)**（無法向下寫入）：使用者無法寫入數據到較低許可等級的地方。

#### 🔒 基本安全定理：

> **如果一個系統在安全狀態下啟動，並且所有過程中的轉換都遵守安全規則，那麼該系統將保持安全。**

### 形式驗證

在1983年，美國國防部的**橘皮書**TCSEC（**Trusted Computer System Evaluation Criteria**，信任電腦系統評估標準）中，正式介紹了**形式驗證**（**Formal Verification**）。

**形式驗證**是一種數學方法，用於證明系統是否按照其規範進行運作，特別是在軍事、醫療和航空航天等關鍵應用領域中，對系統的安全性和可靠性進行驗證。

### 形式驗證的運作方式：

形式驗證通常包括以下幾個關鍵步驟：

1. **規範定義**：定義系統所需的屬性（例如，存取控制政策、避免信息洩漏等）。
2. **建模**：建立系統的正式模型（通常使用形式邏輯或有限狀態機等方法）。
3. **證明**：利用數學證明技術，如模型檢查（Model Checking）或定理證明（Theorem Proving），來驗證系統是否滿足其規範。
4. **驗證**：確保模型的行為與系統的實際運行一致。

---

Let me know if you'd like any adjustments or further details!
