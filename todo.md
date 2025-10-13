(another 偵測方式、實務檢查指令與回應流程)

- 本章節重點
- 圖表
- MITRE ATT&CK 映射：把每種技術對應到 ATT&CK 技術 ID (例如 Persistence -> Registry Run Keys T1547.001, Scheduled Task T1053, Bootkits T1542.001 等)。
- 若面向管理層，增加 KPI/度量（如MTTR、檢測率、合規與風險矩陣）會更有說服力。
Log Injection

- 資通安全的原罪 - The Sins of CyberSecurity
- ch.0
    - 動機補上 電信商等
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
    - 關鍵基礎設施：指實體或虛擬資
產、系統或網路，其功能一旦停止
運作或效能降低，對國家安全、社
會公共利益、國民生活或經濟活
動有重大影響之虞，經主管機關
定期檢視並公告之領域。
    - 新聞優化 提取重點內容
    - 解釋基礎建設被害會怎樣 EX:電信被駭服務中斷 (標記案例抽取3個月內 )
    - 戰爭梳理重點 強調能做到什麼 為什麼資安即國安
    - 點出台灣可以借鏡的地方
    - 網路犯罪集團不但擴大惡意軟體的影響範圍，也同步發展不同型態的威脅手法。例如烏俄戰爭出現一種名為「資料破壞」（Wiper）的攻擊手法，導致國家級駭客組織持續針對高科技製造業、公共部門、電信業等重要的基礎設施進行攻擊
    - Collin 航太 歐洲機場遭網路攻擊 數百航班取消或延誤
- ch.2-0
    - 想在電力設施搞鬼？大陸製變流器驚見可疑通訊模組
    - 美警告：太陽能公路設施疑藏不明元件
    - 及美國聯邦眾議院議長訪台時，導致超商與車站電子看板物聯網設備遭駭並置換內容等，
    - In December 2024, four Chinese industry associations representing the Internet, automotive, semiconductor, and telecommunications sectors declared that U.S.-made chips are no longer secure, urging domestic firms to adopt locally produced alternatives. Chinese automakers, already facing supply chain vulnerabilities and rising geopolitical tensions, have responded by designing their own AI chips and embracing a “de-Americanization” strategy.
- ch.2-2
    - 國家apt事件改寫，敘事模式。中國進晶片合理，因為中國會這麼做，美國也會這麼做
    - 近期案件優化，改寫
- ch.3
    - 
1. **Asymmetry of effort** — An attacker needs one vulnerability and one successful exploit path. Defenders must secure *everything* (patches, configs, users, supply chain).
- ch.3-1
    - 作業系統無法控制在上運行的軟體對其造成破壞
- ch.3-1.b
    - 為了保護這份信任不被惡意利用，DNSSEC 協定作為根伺服器重要的安全防護機制。DNSSEC 設計一個關鍵的主簽署金鑰(KSK)。這個金鑰是整個數位世界的信任基礎，一旦失控、洩露或遺失，將導致全球網路信任體系全面崩潰。如果有惡意行為者控制根伺服器，那麼他就幾乎控制了全球網路。
- ch.3-1.c
    - 1244/15 純BT傳訊
- ch.3-1.d
    - [^6]: https://www.ithome.com.tw/news/169020
- ch.3-2.b
    - gmail回信自己 偽冒身分?
    - Exploit-Laden Banner Ads
    - n some
respects these ads look similar to pop ups, opening a new web browser in addition to the
browser the user already opened. But these so-called “malvertisement” ads pop open without
the underlying website authorizing any such thing; t
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
- ch.3-3.a
    - 生物認證會失靈
- ch.3-3.b
    - 📌 歷史上著名的案例：

DigiNotar（2011）被入侵：攻擊者簽發了上百張假的 Google、Yahoo 等憑證，造成伊朗等國家的用戶被監控。

Symantec CA 信任被撤銷（2017-2018）：因為它旗下子公司濫發憑證，Google 和 Mozilla 最終決定不再信任它簽發的憑證。
- ch.3-3.c
    - ### 防火牆邊界防禦 防火牆提供了邊界的防護，但是一旦放行，則完全不理會。
    - state, stateless firewall re-write
    - * 時間範圍（例如：上班時間允許、非上班時間封鎖）* 應用程式或用戶行為（在進階的下一代防火牆中）
    - Sin foucs on tranditional anti-virus (特徵辨識), less monitor and detection (偵測)
    - 217 測試十款商用網路入侵偵測產品 大部分都難敵刻意地規避 且1990年代的技巧都還管用
- ch.3-3.d
    - Another significant limitation of IDPs is that they only find what they are programmed to detect.
    - 治標不治本
通訊加密
- ch.3-4.a
    - beauty - ch.4 - the underground econnomy
- ch.3-4.b
    - 資安產品濫用
    - 沒有人/企業買得過國家
    - 社群
    - Google Mandiant || MS Security
- ch.4-0
    - 重寫 || FOCUS現在已有的
- ch.4-1
    - IOT領域 IEC62443[^10]
- ch.4-2
    - 微軟聯合美國、日本、歐洲執法機構，以及Cloudflare與ESET等資安業者，以摧毀感染逾39.4萬臺Windows電腦的Lumma惡意程式網路
    - 第一金融集團為展現守護資安決心，7月28日與法務部調查局簽署「國家資通安全聯防與情資分享合作備忘錄」(MOU)，
    - 1. **調整激勵機制**
   * 將產品／資安工程的關鍵績效指標（KPI）與實際的安全成果掛勾，而非僅追求功能開發速度。
   * 與供應商簽訂包含資安條款與服務水準協議（SLA）的合約，讓不安全的產品須承擔責任。
- ch.4-3
    - CISA GASA https://www.gasa.org/
    - {數位政府建設方面，林宜敬明言，數發部會持續推動數位憑證皮夾，相信數位憑證皮夾會是數位世界的基石，數位憑證皮夾的選擇性揭露功能，可保障民眾的隱私，未來數位憑證皮夾建立共同性，更可改善臺灣數位經濟的效益。「數發部最大的職責是創造適合AI、資安、資訊服務等產業成長茁壯的環境，讓資訊產業幫我解決問題的同時，可獲得豐厚利潤，也不會為社會帶來問題」}
    -{
在商業面，林宜敬認為，打詐是一場好人與壞人的戰爭，網路平臺業者擁有最多資源，在不涉及用戶的隱私之下，網路業者掌握涉詐帳號的資料，不應扮演旁觀者的角色，業者應該積極參與這場戰爭，邀請他們加入好人的一方，共同對抗網路詐騙，目前數發部已與Google、Meta、Line等網路業者合作，在事前防止詐騙發生，在事後協助警方偵辦。 }
    -{### 法律如何幫助

在死亡之前，在審判面前，迷途羔羊
帕拉斯對法庭這麼說：那時的我既愚蠢又傲慢，以為自己所向無敵。第二次見到他的時候，他告訴了我一句話，我永遠都不會忘記
}
    - 9月 犯罪逮捕例子