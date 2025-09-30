Nice — that snippet is good, and I can expand/clarify it so it’s accurate and useful in a doc. Below I’ll (1) briefly explain each item in Chinese, (2) say whether it’s a MITM-style attack, and (3) give concise mitigations and a polished bilingual bullet you can drop into your notes.

---



---

### 建議的加入文件的中英雙語條目（可直接貼上）

* **KNOB 攻擊（Bluetooth 的金鑰協商攻擊）**：攻擊者在配對時強制降低協商出的金鑰長度，導致弱加密或可被破解的金鑰，進而可能解密或偽造通訊（可用作 MITM）。建議：更新韌體、避免使用舊式配對、啟用 LE Secure Connections。
* **BlueBorne**：一組針對藍牙實作的遠端漏洞，可在不配對/不顯示的情況下入侵設備；攻擊者可取得裝置控制權或竊取資料，入侵後亦可用以監控或攔截通訊。建議：安裝廠商補丁、關閉不必要的藍牙功能、限制藍牙權限。
* **BtleJack（BLE 注入/嗅探工具）**：用於嗅探、攔截及注入 BLE 封包，能實現典型的 MITM/重放攻擊。建議：使用 LE Secure Connections、在應用層加密敏感資料、更新韌體並避免明文通訊。

---

要我把這三條改成更短的 summary、或加上 CVE 範例、或做成幻燈片格式（一頁/三頁），告訴我要哪種格式 — 不過我會直接給你結果，不用你等我去查！
