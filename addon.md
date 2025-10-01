
---

# 3. Staged 與 Stageless 的技術差異（簡表）

| 面向     |           Staged | Stageless      |
| ------ | ---------------: | -------------- |
| 初始檔案大小 |                小 | 較大             |
| 網路行為   |   需要下載後續模組（可被監測） | 可能無需後續下載       |
| 彈性更新   |        高（可遠端換模組） | 低（得再次部署）       |
| 偵測難易度  | 靜態較難，動態與網路行為易被發現 | 靜態較容易被發現，網路痕跡少 |
| 可靠性    |       依賴外部 C2/資源 | 自包含、較穩定執行      |

---

# 4. 實務注意（攻擊者 vs 防護者觀點）

* 攻擊者偏好：如果要靈活更新或偷藏能力，常用 **staged**；要避免網路連線（如高敏環境）或一次性破壞，可能用 **stageless**。
* 防護面重點：監控初始下載器/投放程式、異常出站流量、DNS 查詢模式、TLS 與 HTTP 行為、記憶體中的可疑模組。特別要注意 beacon、fallback domains、DGA 循環等行為指標。

---

# 5. 偵測指標與防護建議（具體可執行）

* **端點防護（EDR）**：偵測可疑進程建立持久性、非授權的執行檔寫入、進程注入、子進程異常。
* **網路偵測**：監視異常外連（不尋常的域名、短期註冊域、頻繁的 POST/GET）、DNS TXT 和非常規 DNS 子域流量、使用 TLS 但不對應正常業務的主機。
* **記憶體取證**：檢查常駐記憶體模組、未落地的 shellcode 或 post-exploit 模組（尤其 stupefying stageless payloads）。
* **封鎖/隔離**：阻斷已知惡意域名/IP；限制出站端口與服務；應用白名單（application whitelisting）以阻止未知可執行檔。
* **威脅獵捕**：以 IOC（檔案雜湊、C2 domain、URL、行為模式）與 TTP（MITRE ATT&CK）來主動搜查。

---

# 6. 安全提醒（合規與道德）

我可以說明 payload 的高階概念、偵測跡象與如何保護系統，但不會提供會促成或協助製作惡意軟體的具體程式碼或步驟（例如如何產生 shellcode、如何實作 DGA、如何避開防禦等）。

---

如果你想要我把上面內容轉成投影片要點、講稿或一頁速查表（含偵測規則範例：如 EDR 規則範本或網路IDS 檢測思路的 pseudocode），我可以幫你整理成可直接使用的格式（會避免任何可被濫用的具體惡意實作細節）。要哪一種格式？

{
    ### 說明與分類（簡短）

* **KNOB 攻擊（Key Negotiation Of Bluetooth）**
  說明：攻擊者在配對時把雙方協商的金鑰長度降低（downgrade），使雙方使用非常短、弱的加密金鑰。
  MITM 屬性：可以用來實現或輔助 MITM —— 一旦金鑰很弱，攻擊者可以破解密鑰、解密或偽造通訊。
  緩解：更新韌體/作業系統（廠商已推補丁）、避免使用舊式配對流程、啟用 LE Secure Connections（若可用）。

* **BlueBorne**
  說明：一系列針對藍牙實作的漏洞利用（包括遠端代碼執行、資訊洩漏），能在不配對、不可見的情況下入侵設備。
  MITM 屬性：不一定本質上是 MITM；主要是遠端入侵/接管設備，但被入侵的設備可被用來監控/攔截通訊（等於實現 MITM 或竊聽）。
  緩解：關閉藍牙可見性或在不需要時關閉藍牙、安裝廠商安全更新、限制藍牙權限。

* **BtleJack**
  說明：針對 Bluetooth Low Energy（BLE）的工具/硬體組合，用於嗅探、注入、截斷及重放 BLE 封包。它利用 BLE 的弱點（例如沒有加密或使用預共享金鑰）來中間人攻擊。
  MITM 屬性：是典型的 MITM/嗅探/注入工具——能夠在 BLE 裝置間攔截並改寫封包。
  緩解：使用 LE Secure Connections（較強的配對/金鑰交換）、避免明文 BLE 通訊、更新設備韌體、在可能時使用應用層加密。
}

{
  macOS 項目：除了 LaunchAgents/LaunchDaemons，也可補「Login Items、launchctl、cron、sticky plist 權限操控」。

Linux 項目：補充 systemd 之外可列 cron、/etc/rc.local、init scripts、以及 LD_PRELOAD、shared-object injection 等技術。

Windows 項目：除了 Registry Run keys、Startup、Scheduled Tasks，還可補 Services（服務）、WMI persistence、Image File Execution Options (IFEO)、DLL search order hijacking 等常見手段。

「授權與帳號持久化」→ 建議補「Kerberos ticket/Golden Ticket、STOLEN credentials、SSH authorized_keys、credential dumping 並植入憑證」等常見手法說明。


# 偵測（可加入的技術或指標）

* **Cross-view 比對**：使用 user-land 工具列出的進程/驅動/模組 與從 kernel 或直接記憶體取得的清單做交叉比對（若出現不一致，疑似 rootkit）。
* **完整性檢查**：對核心/關鍵二進位（kernel modules、system binaries、bootloader、EFI variables）採用檔案雜湊與簽章驗證。
* **記憶體取證**：採用 Volatility、Rekall 等工具檢查 kernel hooks、inline hooks、unlinked processes、偽造的 system call table。
* **網路異常行為**：長期穩定的外連、異常端口/協議、加密隧道、使用 LOLBins 進行資料外傳的行為模式。
* **日誌完整性與遠端備份**：啟用不可變日誌（WORM）或把日誌推到遠端/不可變儲存以避免本機刪除。
* **啟動流程檢測**：監控 boot sequence、EFI 變數、MBR/GPT 變更與 BIOS/UEFI 更新事件。


---

# 防護建議（可實作的 controls）

* **啟用與強化 Secure Boot / Measured Boot / TPM**：阻止未簽名或異常韌體/bootloader。
* **強制驅動簽名與 Driver Verifier**：減少惡意驅動載入機會。
* **最小權限原則**：限制管理帳號使用、強化特權分離，並偵測新建立的本地管理帳號或權限變更。
* **Endpoint Detection & Response（EDR）/HIDS**：部署能做記憶體/行為分析的 EDR，能監控注入、進程異常、API hooking 等。
* **啟用 Windows Defender ATP / Application Control（AppLocker、Windows Defender Application Control）**：阻止未白名單應用。
* **日誌與遠端蒐集**：集中日誌到遠端 SIEM 並保存（不可由被攻擊端輕易刪除）。
* **韌體供應鏈管理**：確保韌體來自官方簽名來源並實施版本控管與簽章驗證。
* **定期完整性掃描與補丁管理**：包括核對 kernel modules、驅動、系統二進位雜湊。
* **阻斷 LOLBins 濫用**：針對高風險系統命令（PowerShell、certutil、bitsadmin）做行為層次監控、腳本規則或白名單。
* **建立刪除/恢復策略**：當發現 rootkit 時，應有明確流程（隔離、記憶體採證、離線映像、重灌 + 驗證或者韌體重刷）。

---

# 偵測工具與檢查清單（實務）

* Windows：Sysinternals（Autoruns、Process Explorer、Sigcheck）、OSQuery 查詢、Windows Defender/EDR logs、Autoruns 的 registry/startup 檢查。
* Linux：`chkrootkit`, `rkhunter`, `lsmod`, `dmesg`、systemd-analyze、AIDE/Tripwire 完整性檢查。
* macOS：`launchctl list`、`kextstat`、`spctl`、plist 權限檢查、以及 EDR for macOS。
* 記憶體鑑識：Volatility、Rekall（尋找 inline hooks、SSDT hooks、unlinked objects）。
* 韌體檢查：廠商提供的 BIOS/UEFI 校驗工具或比對韌體映像雜湊。

---

# 範例：把一兩個簡短檢查指令放進文件（可直接使用）

* Windows — 列出 service 中未簽名驅動：

```powershell
Get-WmiObject Win32_SystemDriver | Where-Object { -not (Get-AuthenticodeSignature $_.PathName).Status -eq 'Valid' } | Select Name, PathName
```

* Linux — 檢查 systemd 單元是否有非預期自動啟動：

```bash
systemctl list-unit-files --state=enabled --no-legend
```

* 通用 — 記憶體不一致（cross-view）示意：比對 `ps` 與從 raw memory 恢復出的 process list（需要取證工具）。

---


# 偵測指標（IOC / TTP）— 可直接放在 SOC playbook

* 網路層

  * 固定或隨機化但週期性的外連（長期持續且行為一致），尤其向少量少見域名或 IP。
  * DGA 風格的域名（高熵、快速輪換）；Fast‑flux DNS 記錄。
  * DNS 查詢中的長 base32/base64 子域（DNS exfiltration）。
  * 非標準協定或自訂封包格式、異常 TLS 指紋（JA3/JA3S 差異）。
* 主機層

  * 新建立的 service、排程任務、IFEO／Startup registry 的變更。
  * 未簽章或新近被寫入的驅動、可疑 kernel module。
  * PowerShell/Windows cmdline 含大量編碼（Base64）或使用 certutil/downloadstring 等 LOLBins。
  * 進程注入（CreateRemoteThread、NtWriteVirtualMemory 等 API 使用痕跡）、未匹配的模組映射。
* 記憶體/取證

  * 未在正常 process list 出現卻在 raw memory 中存在的執行緒/模組（cross‑view 不一致）。
  * 網路連線記錄與進程來源不一致（例如 explorer.exe 發起外連）。
* 其他

  * 大量刪除或改寫 event logs、刪除 shadow copies、關閉備份服務等行為。

# 範例查詢 / 規則（直接可用）

## OSQuery（找出最近被建立且可疑的 Windows Scheduled Tasks）

```sql
SELECT name, path, description, last_run_time
FROM scheduled_tasks
WHERE path LIKE '%AppData%' OR path LIKE '%Temp%' OR path LIKE '%Users%';
```

## PowerShell：列出可疑使用 Base64 的命令（Windows 事件或 PowerShell 轉儲）

```powershell
Get-WinEvent -FilterHashtable @{LogName='Microsoft-Windows-PowerShell/Operational'; StartTime=(Get-Date).AddDays(-7)} |
Where-Object { $_.Message -match 'EncodedCommand' } |
Select TimeCreated, Message
```

## Zeek (Bro) — 偵測 DNS 子域高熵（簡化）

```zeek
# 假設使用 community script for dns_entropy
@load policy/dns/dns-utils
event dns_request(c: connection, msg: dns_msg) {
  if ( dns_high_entropy(msg$qname) ) {
    NOTICE([$note=Notice::DNS_HighEntropy, $msg=fmt("High entropy qname %s", msg$qname), $peer=c$id$resp_h]);
  }
}
```

## Suricata / IDS — 偵測常見 Cobalt Strike HTTP Beacon (示例 pattern, 須調整)

```
alert http any any -> any any (msg:"Possible Cobalt Strike HTTP Beacon"; content:"/submit.php"; http_uri; content:"User-Agent: Mozilla/5.0"; sid:1000001; rev:1; classtype:trojan-activity;)
```

（備註：實際規則需依版本與環境調整，並搭配 TLS 解密 / SNI 檢查）

## Sigma（偵測持續 Beacon 行為，示意）

```yaml
title: Periodic Beaconing via HTTP
detection:
  selection:
    EventID: 3
    Image: '*\powershell.exe'
    CommandLine|contains: 'Invoke-WebRequest'
  condition: selection
level: high
```

# 偵測方法補充（技術面）

* 行為式檢測比單純簽名更重要：監控「週期性外連」、「進程與網路行為不一致」、「script engine 使用行為」。
* 使用 JA3/JA3S、TLS Server Name、SNI、Certificate Subject/Issuer 做 TLS 流量指紋與群組化分析。
* 用 temporal analytics（時間序列）找出「穩定但低頻率」的連線（beacon）。
* Cross‑view 檢測：`ps` vs raw memory、`lsmod` vs kernel module list，任何差異可疑。
* 沙箱/偵測環境：beacon 常會含 jitter、隨機 delay、fallback domain；把這些模式列入檢測特徵。

# 防護建議（可操作）

* 嚴格 egress 控制：只允許必要的外部服務，阻斷可疑端口／協定。
* DNS 監控與封鎖：啟用 DNS Filtering、阻斷高風險 domain 與 DGA。
* TLS 檢查／中繼：在合規範圍內做 TLS 檢視或使用 TLS 指紋化技術（注意隱私與合規）。
* 對高風險 LOLBins 實施限制或白名單（尤其在高敏感主機上）。
* 部署 EDR 並開啟記憶體保護/行為偵測（針對注入、API hooking、shellcode execution）。
* 縮小管理面暴露面：最小權限、分段網路、跳板機管理、MFA。
* 儲存/分析日誌到不可變或遠端位置（避免攻擊者刪除本機日誌）。


# SOC / IR 建議（運營層面）

* 建立基於優先度的事件分級（如：未簽章驅動載入 = P0；定期 beacon 到新域名 = P1）。
* 當偵測到 beacon/持久化行為：先隔離→記憶體採證→導出網路抓包→分析 C2 domain/IP → 查找 lateral movement indicators→再進行修復（重灌/韌體重刷視情況）。
* 定期演練：tabletop 演練 C2 偵測與隔離流程。

---


### 偵測指標（IOC / TTP）

* 內網主機之間出現大量或非典型的 SMB 會話（長時間持續或在非工作時間）
* 突然出現許多來自不常見主機的檔案共享讀/寫行為，尤其寫入執行檔或腳本到管理分享（C$, ADMIN$）或特定共用資料夾
* 命名管線（named pipe）連線異常或新創建不明 pipe 名稱（IPC activity）
* 可疑使用 PsExec、wmiexec、smbclient 或類似工具的行為紀錄（遠端執行痕跡）
* SMBv1 流量或來自過時系統的大量 SMB 請求（可疑 exploit 掃描）
* 透過 SMB 傳輸的加密/編碼小型資料塊（可能為 beacon payload）
* 憑證使用模式改變：相同憑證在多台主機短時間內失敗/成功登入（可能為憑證重放/relay）

### 偵測 / 調查範例指令

（可直接放入 SOC playbook）

* Windows — 列出目前 SMB 連線／會話

```powershell
Get-SmbSession | Select ClientComputerName, ClientUserName, NumOpens, SessionId, ClientIP
```

* Windows — 列出開啟中的 SMB 檔案

```powershell
Get-SmbOpenFile | Select ClientComputerName, ClientUserName, Path, FileId
```

* Windows — 列出分享設定

```powershell
Get-SmbShare | Select Name, Path, Description, ConcurrentUserLimit
```

* Linux (Samba) — 檢視 samba log（常見路徑）

```bash
tail -n 200 /var/log/samba/log.*
```

* Network/IDS — 使用 Zeek/Suricata 的 SMB 模組，檢查大量 SMB Write/CREATE 操作或 unusual Named Pipe sequences（依環境啟用 SMB analyzer 並追蹤 smb_files, smb_cmds）

### 防護與減緩建議（可操作）

* **封鎖邊界與 egress 控制**：在網路邊界阻擋 SMB（TCP 445/139）對外流量；內部僅允許必要的 SMB 流量。
* **停用 SMBv1**：移除過時的 SMBv1 協定以避免已知散播漏洞被利用。
* **強制 SMB 簽章與加強驗證**：啟用 SMB signing（防止中間人/relay）並強制使用 NTLMv2 或 Kerberos，限制匿名登入。
* **限制管理分享與最小權限**：對 C$, ADMIN$ 等管理分享採嚴格控制；限制需大量權限的帳號使用與來源。
* **分段與微分段（micro‑segmentation）**：把內網切分，限制工作站直接訪問伺服器或高權限資源，減少橫向擴散面。
* **監控與日誌化**：收集 SMB 相關日誌（主機端與 NAS/SAN/檔案伺服器）到集中 SIEM，並建立檢測規則（大量寫入、非典型時間、跨多台主機同一帳號行為）。
* **防止憑證濫用**：使用 LAPS、限制本地管理員帳號複用、定期更換/輪替憑證；部署 MFA 於管理存取。（減少憑證被用於 SMB 橫向的風險）
* **EDR 規則**：在 EDR 中加入針對 PsExec、smbclient、remote service create、named pipe usage、suspicious SMB file writes 的檢測/阻斷規則。
* **資產及補丁管理**：立即修補可被利用的 SMB 漏洞，移除或隔離高風險之老舊系統。
* **內網蜜罐/誘餌共享**：部署假的 SMB 共享或命名管線來偵測內部探索與 lateral movement。

}