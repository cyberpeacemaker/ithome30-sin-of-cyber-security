(another 偵測方式、實務檢查指令與回應流程)

- MITRE ATT&CK 映射：把每種技術對應到 ATT&CK 技術 ID (例如 Persistence -> Registry Run Keys T1547.001, Scheduled Task T1053, Bootkits T1542.001 等)。
- 本章節重點
- 更多簡單比喻?

- ch.1 
    - cia+4
- ch.1-1 
    - 駭客以可以駭入這些智慧裝置並竊聽[link](https://www.cnet.com/tech/mobile/these-kids-smartwatches-have-security-problems-as-simple-as-1-2-3/)
    - 駭客入侵Ring監視器，嚇壞家中小孩 [link](https://www.ithome.com.tw/news/134826)
    - Insecam 
- ch.1-2
    - 2018 北韓 lazarus group攻擊紐約聯邦儲備銀行 偷取8100萬美元
    - 北韓駭客組織Lazarus發動史上最大加密貨幣盜竊案，導致Bybit交易所損失14.6億美元
- ch.1-3
    - 新聞優化 提取重點內容
    - 解釋基礎建設被害會怎樣 EX:電信被駭服務中斷 (標記案例抽取3個月內 )
    - 戰爭梳理重點 強調能做到什麼 為什麼資安即國安
    - 點出台灣可以借鏡的地方
    - 網路犯罪集團不但擴大惡意軟體的影響範圍，也同步發展不同型態的威脅手法。例如烏俄戰爭出現一種名為「資料破壞」（Wiper）的攻擊手法，導致國家級駭客組織持續針對高科技製造業、公共部門、電信業等重要的基礎設施進行攻擊
    - Collin 航太 歐洲機場遭網路攻擊 數百航班取消或延誤
- ch.2-0
    - 想在電力設施搞鬼？大陸製變流器驚見可疑通訊模組
    - 美警告：太陽能公路設施疑藏不明元件
- ch.2-2
    - 國家apt事件改寫，敘事模式。中國進晶片合理，因為中國會這麼做，美國也會這麼做
    - 近期案件優化，改寫
- ch.3-1
    - 作業系統無法控制在上運行的軟體對其造成破壞
- ch.3-1.c
    - 1244/15 純BT傳訊
- ch.3-1.d
    - [^6]: https://www.ithome.com.tw/news/169020
- ch.3-2.b
    - gmail回信自己 偽冒身分?
- ch.3-2.c
    - real example || B292 New york times
    - 原罪編號
- ch.3-2.d
    - BEACON 抖動（Jitter）：在時間上做小幅變化以避免以簽名為基礎的偵測
    - * 🕷️ **Mirai**: Famous IoT botnet that took down major websites (Netflix, Twitter) via DNS provider Dyn in 2016.
    - * 🦠 **Emotet**: Started as banking malware, evolved into a modular botnet for spam and malware distribution.
    - * 👾 **Zeus/Zbot**: Banking trojan with MITB features, often used in botnets.
    - * ⚠️ **QakBot**: Multifunction botnet used for ransomware delivery before its takedown in 2023.
## Persistence mechanisms

* Registry Run keys (Windows), systemd timers/services (Linux), cron jobs, startup folders, firmware-level persistence for advanced threats.


As shown below, the attacker chooses to run a post-exploit persistence module, which involves a Visual Basic Script (VBScript) placed in the Windows Temp folder of the logged-on user, UoPfNwo.vbs. The attacker then installs a Windows registry entry to enable the script to autorun after the machine boots up.
* Beacon / C2 callback → T1071 (Application Layer Protocol)、T1095 (Non‑Application Layer Protocol)、T1105 (Ingress Tool Transfer)
* Downloader → T1105 (Ingress Tool Transfer)、T1218 (Signed Binary Proxy Execution)
* Dropper/Installer → T1543 (Create or Modify System Process)、T1547 (Boot or Logon Autostart Execution)
* Staged vs Stageless → T1105 (staged fetch)、T1059 (command and scripting interpreter) 等（可逐條對應）

- ch.3-2.e
    - 變種 AI 規則檔案，Rules File Backdoor將AI的「規則檔案」變成攻擊媒介，而有可能使得受到危害的軟體影響終端使用者
    - Docker Hub[^6] Github[^7] [^9] NPM[^8] 輸入法[^10] VScode Extension[^12] Go模組[^15] 案例分類，介紹，重點擷取
    - **保管重要資訊的人** 佛羅里達 警官 accurint 社會安全保險號碼 出生日期 居家住址 駕照號碼 || 網路供應商 T mobile 員工告訴一切 附加解說
- ch.3-3.b
    - 📌 歷史上著名的案例：

DigiNotar（2011）被入侵：攻擊者簽發了上百張假的 Google、Yahoo 等憑證，造成伊朗等國家的用戶被監控。

Symantec CA 信任被撤銷（2017-2018）：因為它旗下子公司濫發憑證，Google 和 Mozilla 最終決定不再信任它簽發的憑證。
    