# 【08】資安的原罪 ch.2-2 從「腳本小子」到國家級 APT


# From scriptkid to advace persist threat

now wer know the deviece that can be hackerd. but who is hacking?

## who is hacking?

**Script Kiddo (or Script Kiddie)**
A script kiddo is an inexperienced or unskilled person who uses existing computer scripts or tools created by others to hack or exploit systems, without truly understanding how they work. They're often looked down upon in the cybersecurity world.
由於市面上大量的現成工具，目前想成為駭客不需要技術或經驗，只需要犯法的勇氣就可以了。
EX: Metaspolit框架，弱點掃描，弱點利用

**💰 Profit-Oriented Hacker Groups:**
現在許多民間營利項的駭客組織規模及能力發展壯大
These are cybercriminal organizations that focus on **making money** rather than political or ideological goals. They often run like businesses, with teams, customer support, and even affiliate programs.

**APT (Advanced Persistent Threat):**
An APT is a sophisticated and stealthy cyber attack, usually carried out by skilled hackers (often state-sponsored) over a long period. The goal is to gain unauthorized access to a network and remain undetected to steal data or cause damage.
要技術有技術，有方法有方法，最恐怖的是有充足的資源。一般民眾組織不可投入全部資源在資安
零時差弱點的開發 網路釣魚大規模法展與運行 基礎建設製造 滲透出來資料的後續處理 都需資源透入
駭客工具會很勤勞而且周詳的更新
他們創作工具的意圖是要避免遭到偵測 即在被偵測到時緩減被確認出身分的速度

合理的假設是APT已經喘入 任務是在組織內部找他們並嘗試排除他們
被逼上，修補程式的安裝、防毒軟體與入侵偵測系統的使用、甚至是空氣隔離的導入，都很難期待產生出什麼成效

---





美國國安局從2012 弱點買家 向法國公司VUPEN訂閱"零時差服務"
2016 聯邦調查局已超過130萬美元 購買iphne零時差弱點利用程式

微軟打算限縮部分中國MAPP成員存取內容，原因是中國政府傳出參與SharePoint零時差漏洞攻擊[^7]



由於進階持續性威脅（APT）的入侵手法與國家級駭客發動的惡意行為，相較網路犯罪分子的威脅，其攻擊速度更快、更具針對性，且影響範圍更廣，因此不論是對台灣或全球各大企業，APT攻擊與國家級駭客組織的規模發展與活躍程度，都將成為未來攻擊趨勢的重點關注方向。

針對各種重要機構設施滲透，其中包含電信業者，這將使的下游客戶被攻擊

## 國家例子

法國企業組織遭中國駭客UNC5174鎖定，透過Ivanti CSA設備零時差漏洞入侵[^11]

---
中國駭客組織鎖定電信業者從事大規模網路間諜活動，藉此針對特定的政治人物進行情報收集，這樣的事故又以去年9月爆發的Salt Typhoon駭客攻擊行動受到高度關注，不僅傳出AT&T、Verizon、Lumen等多家大型業者受害，相關攻擊亦得到美國政府的證實，後續更傳出這些駭客也對其他國家電信業者下手的情況；另有資安業者揭露專門攻擊南亞、非洲電信業者的駭客組織Liminal Panda，如今又有資安業者揭露相關事故的最新調查結果。中國駭客組織行徑囂張，長年從事網路攻擊的情況，過往相關警告幾乎是美國發出，也有不少是由五眼聯盟發出，但最近日本也發布相關的公告，該國警方本週針對特定中國駭客組織的攻擊行動發布警告，突顯此項威脅範圍正在逐漸擴大。他們特別提及這些駭客已對於當地發動三波大規模攻擊，主要的目的就是為了國家安全及先進技術的機密資料，並公布駭客的作案手法，供當地企業組織防範相關攻擊。
Google揭露中國駭客UNC3886利用零時差漏洞CVE-2023-34048的攻擊行動，駭客從2021年開始用於對VMware虛擬化平臺vCenter下手，並在癱瘓VMware服務後的數分鐘內，部署後門程式。後續有其他駭客跟進，利用這項漏洞從事網路間諜活動[^22]

### 中國
從醉金的新聞可以看到，中國正在打舉入侵他國重要設施，包含金融業、大學[^23]、政府機關[^18]，IT產業[^24]、電信服務業[^16] [^13] [^20] [^25]等[^19]，甚至美國核武機構[^14]
7月23日，3組中國駭客使用SharePoint零時差漏洞從事攻擊[^12]
微軟打算限縮部分中國MAPP成員存取內容，原因是中國政府傳出參與SharePoint零時差漏洞攻擊[^28]
---

**美國**
早在1960 階梯計畫 Echelon Program 五眼聯盟 five eyes group用各種基地台、電信分路氣、電纜竊聽器來 攔截衛星、電話、微波通訊。 南北美洲、北大西洋與歐洲、亞洲全都在美國國安局掌握下
2020 華盛頓郵報 Crypto AG生產軍事外加的加密基季 從1970就跟美國中情局秘密合作在機器中嵌入後門
2013 美國國安局在海關埋伏 等Cisco思科的路由器一出現 就打開盒子把原本的晶片換成藏有後門的版本輸往國外

美國國安局 曾入侵德國總理梅克爾的手機 歐巴馬親自向梅克爾道歉
美國關安 肌肉muscular, 無界線民 doundless informant, 終極機密總譜 Xkeyscore

影子 shadow brokers 駭入 方程式組織 equation group 取得眾多弱點利用程式ENTERNALBLUE, ETERNALROMANCE, EXPLODINGCAN
其中ETERNALBLUE後來被用來創造WannaCry勒索 Notpetya
方程式組織 幾乎確定隸屬於NSA TAO 國家安全局內部的特定入侵行動辦公室 office of tailored access operations

2013 菱鏡計畫 PRISM 美國正在入侵全美前九大網路公司，從中央服務氣直接存與影音聊天紀錄、照片、墊子郵件、文件、連線紀錄 (這份報導獲得pulizer prize for public service)
美國安全局內部的特定入侵行動辦公室 TAO 量子(quatum)駭客工具 界監聽網際網路上的網路流量 量子可以偵測到目標的網頁練覽器打算載入某個網頁 量子可以創造一份網頁副本並安插惡意程式碼 在正牌網頁伺服器前就把假網頁傳送到目標的瀏覽器上 國安局:"如果我們可以讓目標來到化身為某種網頁瀏覽器的我們面前，那我們多半可以把他們變成我們的囊中物"
國家安全局 世界各地伺服器 影子網路 危機解密顯示 量子突破 Yahho! LinkedIN facebook twitter youtube等其他熱門網站

量子還被用來害入電信公司BELACOM 石油輸出國家組織OPEC 英國政府通訊總部GCHQ

紐約時報卻揭露，在川普第一任期2019年川金會前，曾下令派遣美國海豹菁英部隊潛入北韓海岸，企圖竊聽金正恩，行動最後以失敗告終，甚至傳出擔心行動曝光，有北韓平民被射殺[^6]

**中國**
61398 極光
2010 goolge通報 遇襲對象除自己 包括金融、媒體、國防、貨運、製造、電子與軟體 取額資訊包括醫學臨床測試結果、產品的藍圖與製程
從美國組組織中竊取智慧財產 美國軍方 V-22 F-35戰鬥機 黑鷹之生機  海龍計畫書
"中國聘請駭客的速度 跟不上美國安全系統冒出弱點的速度"

**俄羅斯**
- 2014 2014 俄羅斯害入 美國國務院 白宮 五角大廈 參謀長聯席會議
- 俄羅斯駭客RomCom將其用於實際攻擊行動藉此於歐洲及加拿大的金融、製造、國防、物流產業發動攻擊，部署SnipBot、RustyClaw、Mythic等惡意程式[^10]
- 奇幻雄 特物X 潛入全國委員會和國會競選委員會的網路內部 偷聽著民主黨高層最機密的談話和分析
- 74455 anatoliy kovalev 害進選舉委員會 姓名 住址 生日 駕照號碼 社會安全馬
- SolarWinds 專門製作企業用的網路監控轉體 無角大廈 網路司令部 聯邦調查局 財政局 國土安全部 商務部 衛生及公共服務
- 俄羅斯駭客Curly COMrades鎖定前蘇聯國家，透過惡意程式MucorAgent從事隱密的網路間諜活動[^12]

**其他**
- 法國國防業者Naval Group傳出遭駭，攻擊者竊得1 TB內部資料[^6]
- 韓國電信業者SK Telecom事故最新調查出爐，駭客在網路環境活動近3年[^11]
- 在以巴戰爭中，近五成伊朗國家級網路攻擊的目標鎖定以色列公司，並針對學校、政府機關、金融機構及醫療機構進行滲透與攻擊[^12]
- 在以色列與伊朗的網路衝突中，伊朗曾於2021年遭遇大型網路攻擊，導致燃料銷售中斷，全國加油站出現長長的排隊人龍。

- APT28利用郵件系統漏洞從事網路間諜活動，鎖定政府機關竊取重要資料[^13]

##  竊取企業智慧財產權
**經濟間諜**
中國持續從美國企業翹取智慧財產 F-35戰鬥機整設計圖 google, facebook
聯邦調查局長james comey 2014:美國公司只分兩種，一種被中國駭過，一種不知道自己被中國駭過
**勒索科技業**
在資安事件方面，這一星期國內多家上市櫃公司發布資安事件重訊，其遭遇事故類型涵蓋供應鏈攻擊、勒索軟體攻擊，以及DDoS攻擊事件。

●易飛網在1月7日說明遭遇供應鏈攻擊及資料竊取，致有個資外洩。
●新海瓦斯1月9日揭露伺服器內部檔案遭受勒索軟體加密。
●悠泰科技、華航在1月7日與8日分別公布官網遭受網路DDoS攻擊。
●針對中華電信海底電纜遭貨輪破壞的事故，數位發展部表示中華電信當日已通報並啟動其他海纜備援，之後將配合海巡署、法務部、NCC與司法機關加強執法。
●資安業者Tenable傳出外掛程式更新出錯的意外事故，造成端點代理程式停擺。


Dell傳出遭駭客組織World Leaks勒索，該公司坦承測試平臺遭駭[^1]
【資安日報】6月26日，勒索軟體Dire Wolf鎖定臺灣、美國、泰國而來，科技與製造產業是主要標的[^2]
今年1月、5月兩度遭到勒索軟體攻擊的矽光子及光電封測大廠聯鈞光電[^3]。
荷蘭警告Citrix NetScaler出現重大漏洞攻擊行動，當地企業組織已傳出受害[^6]

## 網路諜報

俄羅斯、中國駭客組成網路犯罪集團ShadowSilk，利用滲透測試工具和已知漏洞，入侵中亞、亞太地區政府機關[^8]
瑞士政府周一指出，受非營利機構Radix受勒索軟體攻擊事件波及，致使數個瑞士政府機構辦公室資料外洩[^4]。
加拿大眾議院遭網路攻擊[^5] 


美國國家安全局(NSA)與英國政府通訊總部(GCHQ)遭窺探






資安業者S2 Grupo揭露俄羅斯駭客APT28鎖定北約組織（NATO）成員國企業組織的最新一波攻擊行動，駭客打造新的後門程式NotDoor，部署在受害電腦的收信軟體Outlook，以便接收命令、洩露資料，以及上傳作案工具[^9]



[^1]: https://www.ithome.com.tw/news/170190
[^2]: https://www.ithome.com.tw/news/169742
[^3]: https://it.nycu.edu.tw/it/ch/app/data/view?module=nycu0129&id=4054&serno=d1737297-3d1f-42d9-a37c-7d1c23b7a00c
[^4]: https://www.ithome.com.tw/news/169850
[^5]: https://www.ithome.com.tw/news/170637
[^6]: https://www.ithome.com.tw/news/170651
[^7]: https://www.ithome.com.tw/news/170747
[^8]: https://www.ithome.com.tw/news/170955
[^9]: https://www.ithome.com.tw/news/171020
[^10]: https://www.ithome.com.tw/news/166911
[^11]: https://www.ithome.com.tw/news/169870
[^12]: https://www.ithome.com.tw/news/170631
[^13]: https://www.ithome.com.tw/news/168993