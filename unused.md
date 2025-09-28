ch2.0{
    ### 電腦連不上網 不等於沒有受到C2控制
    連網?一般想到的是可以瀏覽網頁，通外網，但沒有內網  Adhoc
    內外往常指 IEEE
    還有其他 通訊手段協定

    ### 以為警察會處理
    光處理事情就更多了 還資安 也沒那個資源 
}

ch2-1{

    若人們對這些風險缺乏認知，將會在毫無防備的情況下，不斷將脆弱的裝置連接到網路，會讓駭客擁有很大的攻擊面積，進而讓整個社會暴露在極高的資安風險之中。

    這些風險對不同角色造成的影響也不盡相同：

    * **對一般民眾而言**，物聯網裝置與人臉辨識等技術的大量結合，使得日常生活中的監控風險大幅上升。
    * **對軟體、硬體及網路等供應商而言**，若提供的產品存在安全漏洞，不僅自身受害，更可能連帶危及整個供應鏈。
    * **對於保管敏感資訊的單位**——如銀行、政府、軍方等，一旦遭到入侵，可能導致大量機密資料外洩。

}

ch2-2{
    - 荷蘭警告Citrix NetScaler出現重大漏洞攻擊行動，當地企業組織已傳出受害[^6]
    - 法國企業組織遭中國駭客UNC5174鎖定，透過Ivanti CSA設備零時差漏洞入侵[^11]
    - 瑞士政府周一指出，受非營利機構Radix受勒索軟體攻擊事件波及，致使數個瑞士政府機構辦公室資料外洩[^4]。
    - Dell傳出遭駭客組織World Leaks勒索，該公司坦承測試平臺遭駭[^1]
    - 6月26日，勒索軟體Dire Wolf鎖定臺灣、美國、泰國而來，科技與製造產業是主要標的[^2]
    - 今年1月、5月兩度遭到勒索軟體攻擊的矽光子及光電封測大廠聯鈞光電[^3]。    
    美國國家安全局(NSA)與英國政府通訊總部(GCHQ)遭窺探
    實驗室 中國產品發訊號
}



ch3.0{
    > **「稱職修車工的首要條件，不應是擅長往油箱裡倒糖。」**
    > —— 反映出資安防守與破壞之間，技能上的不對等。
}

ch3-1.a{
    **真實案例**：Eric Allman 的 `sendmail` 曾無意留下除錯用後門，後被臭名昭著的 **Morris 蠕蟲** 利用，成為網際網路史上首例大規模攻擊事件。
}
ch3-1.b{
    **蠕蟲**
    1988 Morris 蠕蟲
    紅色警戒 red code 造成約26億美元以上的財物損失 A116
    尼姆達 nimda A117

    快速蠕蟲感染網際網所有弱點的電腦只需要幾分鐘，甚至幾秒鐘
    Slammer
    Blaster
    Welchia
    Sobig
    Sasser 讓香港醫院當機，美國達美航空取消四十趟班機，感染澳洲鐵路網使數以千計的火車乘客動彈不得
    ### 3.
    TODO:
    1994 賈伯斯被問是否可能出現使用零時差弱點 快速傳播 帶有毀滅性酬載的蠕蟲?
    把臉埋進雙手 一棟不動一聲不響 "不 他們需要網路 不會砸自己吃飯的郭"
    可以窺見 沒發生不是技術問題 是沒有動機
    推估一小隊有技術的人就可以辦到[^1]

    ### 6. 協定的便利與風險
    許多協定**創立基於便利性，因此也缺乏安全性**。像是DNS讓使用者無需記住難以辨識的數字 IP 位址，大幅提升了網路的可用性與便利性，然而這樣的設計同時也為攻擊者創造了可乘之機。或是FTP 協定缺乏加密機制，使用者認證流程也不夠嚴謹，導致攻擊者或已入侵的帳號有機會上傳惡意檔案至伺服器。

    ### 網頁連覽器
    broswer電腦上的軟體，沒辦法在電腦控制下，能攻擊到電腦
    恣意讀取電腦上的各種檔案，跑各種指令，修改或刪除資料，插入惡意程式各種功能監聽。
    Session hijacking 

    ### 網路監禁問題
}
ch3-1.c{
    bluesnarfing 藍芽竊聽
    ## 網際網路的延伸
    **安全議題**：數據網路容易遭遇SIM卡複製、中間人攻擊及SS7漏洞，5G帶來大量物聯網裝置與網路切片的新挑戰，需嚴密防護以防資安入侵。
    **安全議題**：衛星通訊面臨訊號干擾、資料攔截及地面站網路攻擊等威脅，衛星連結也易遭冒充或未授權存取，需加強資安防護。    
}
ch3-1.d{
    烏克蘭電廠20年未更新，駭客入侵電廠的控制設備，只消幾秒鐘就能切斷電力供應
    駭客經常竄改韌體內容在裏頭植入惡意功能，試圖長期不被發現活動蹤跡，就算重裝作業系統或更換硬碟也能繼續存活。
另外竄改某些韌體(BIOS或UEFI)的組態變數，已讓駭客停用某些硬體支援的安全控制，例如安全啟動(secure boot)
}
ch3-2.a{
### Linux應對
ASLRR 位址空間配置隨機 Address Space Layout Randomization 之前一般都是位在記憶體空間頂部 ASLR隱藏堆疊
ASLR很快失效 駭客找到堆疊位址的方法
推出ESP 可執行空間保護 Executeable Space Protection 會將推疊所在的記憶體為指標是為不可執行 就算破解ASLR找到植入代碼 ESP也會拒絕執行
ESP 失效 Return Oriented Programming返回導向程式設計 不再將惡意軟體植入堆疊 而是尋找堆疊外可以協助完成任位的代碼片段
ROP中 每個片段結尾的指令 都是返回到堆疊 每個片段的記憶體位只放在堆疊上 串接再一起執行惡意程式 
片段跳轉到堆疊 堆疊跳轉到片段 控制程式流    

SQL注入 相對容易預防 卻還是很常見
}
ch3-2.c{
    ### **5. Impacts: What Are the Consequences?**

    The consequences of MITM attacks can be severe for both individuals and organizations:

    * **Data Theft**:

    * Sensitive personal or financial information (e.g., usernames, passwords, credit card details) can be stolen and used for malicious purposes such as identity theft, fraud, or account takeovers.

    * **Loss of Data Integrity**:

    * Attackers may alter the communication in transit. For example, a bank transfer could be modified to redirect funds to the attacker’s account, or malicious code could be inserted into otherwise legitimate files.

    * **Impersonation**:

    * The attacker can impersonate either of the communicating parties. This can lead to unauthorized access to systems, malicious transactions, or spreading misinformation.

    * **Undermining Trust**:

    * MITM attacks erode trust in online communications. If users begin to suspect that their communication is being intercepted, they may avoid using certain services or sharing sensitive information, which can hurt businesses and disrupt online services.
    
    * **Silent traffic redirection**: Victims may unknowingly connect through the attacker’s gateway or use malicious DNS servers, enabling phishing, session hijacking, or malware injection.

    * **Reputational Damage**:

    * If an organization is compromised by a MITM attack, the resulting data breach or financial loss can severely damage its reputation, especially if customers' sensitive information is involved.
}

ch3-2.b{
    欠缺資安溢式的使用
    PEBCAK
}
ch3-2.c{
    緩解
    CDN contents delivery network
    同一內容的快取分散在網路上
}