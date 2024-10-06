# Windows Server Penetration Testing
## Step By Step
### Step 1 
- 安裝一台kali_linux虛擬機
- 安裝一台Windows_Server虛擬機,並配置AD DS
- 安裝一台Windows_10虛擬機並加入Windows Server的網域下
### Step 2
- 進入kali linux的終端機,使用nmap掃描Windows Server的運行服務
- **2-1確認Windows Server還活著**
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
> Metasploit Framework是一個漏洞利用框架,通過已被發現的漏洞與已經存在的攻擊模塊去進行自動化攻擊。

> 意思是說可以不用自己去漏洞分析目標系統漏洞,就自動化去攻擊目標系統。

> 但是如果是攻擊正版授權系統而且已經修復大多數被發現的漏洞,就需要去學習逆向工程或學習漏洞分析。

> 滲透測試專家與安全研究人員就是在學習與研究這些發現漏洞的技術。
- **3-1開啟漏洞掃描工具Metasploit Framework**
```
sudo msfconsole
```
- Metasploit Framework成功開啟畫面
- ![image](https://github.com/user-attachments/assets/d458bf3b-5619-41b7-9a0d-47eebbd6fe4c)

- 
- 利用漏洞掃描工具掃描可利用的系統漏洞
- 利用系統漏洞進入Windows Server
### Step 4
- 進入Windows Server後提升至管理員權限
- 查看網域下的PC有幾台
