# Penetration-Testing
## 種類
- 1.黑盒子測試（Black Box Testing）
- 定義：測試者對目標系統沒有任何內部訊息，只基於公開可用的資訊進行測試。
- 目標：模擬外部攻擊者對系統的攻擊，偵測系統在完全不了解的情況下能夠暴露的漏洞。
- 特點：
- 測試者從攻擊者的角度出發，使用公開資源、掃描工具、和社會工程手段。
- 測試結果通常能反映系統的外部防禦能力。
- 適用場景：外部網路測試、Web應用程式測試。
- 2.白盒測試（White Box Testing）
- 定義：測試者對目標系統有全面的了解，包括原始碼、網路架構、以及系統配置。
- 目標：深入分析系統內部的漏洞，包括程式碼層級的缺陷和設計上的問題。
- 特點：
- 測試更深入、全面，能夠發現隱藏的邏輯漏洞或設計缺陷。
- 需要更多的內部資訊和技術支援。
- 適用場景：應用程式程式碼審查、內部系統安全評估。
- 3.灰盒測試（Gray Box Testing）
- 定義：測試者對目標系統有部分了解，例如特定的存取權限、網路拓撲圖或部分原始程式碼。
- 目標：結合外部攻擊和內部漏洞分析，模擬半信任的內部人員或有部分資訊的外部攻擊者的攻擊行為。
- 特點：
- 綜合了黑盒和白盒測試的優點，能夠更有效地發現漏洞。
- 著重於特定部分的安全性評估，如認證機制、資料流等。
- 適用場景：內部網路測試、認證機制測試。
- 4.網路滲透測試
- 定義：測試網路基礎架構的安全性，包括路由器、交換器、防火牆、無線網路等。
- 目標：發現網路設備和配置中的漏洞，以及不安全的通訊協定或未授權的網路存取點。
- 特點：
- 測試可能包括連接埠掃描、網路設備漏洞利用、網路嗅探等。
- 涉及防火牆規則、路由表、以及VPN等的測試。
- 適用場景：企業網路、資料中心網路、無線網路。
- 5. Web 應用滲透測試
- 定義：專門針對Web應用程式進行的滲透測試，檢查應用程式的安全性。
- 目標：發現Web應用程式中的常見漏洞，如SQL注入、跨站腳本攻擊（XSS）、會話劫持、CSRF等。
- 特點：
- 重點在於應用層安全，測試輸入驗證、認證機制、會話管理等。
- 使用工具如Burp Suite、OWASP ZAP、SQLMap 等。
- 適用場景：企業入口網站、線上交易系統、API服務。
- 6.無線網路滲透測試
- 定義：測試無線網路（Wi-Fi）的安全性，評估無線存取點的安全配置和通訊加密強度。
- 目標：發現無線網路中的不安全設定、弱密碼、未加密通訊等漏洞。
- 特點：
- 測試包括無線網路嗅探、破解加密、捕獲和分析流量等。
- 評估無線存取點的安全性和存取控制策略。
- 適用場景：企業Wi-Fi網路、公共Wi-Fi熱點。
- 7.社交工程測試
- 定義：利用心理操縱技術，誘使人員洩漏敏感資訊或執行特定操作。
- 目標：測試人員對社會工程攻擊（如釣魚郵件、偽裝電話）的防禦能力。
- 特點：
- 重點在於人性弱點而非技術漏洞。
- 測試方法包括釣魚郵件、假冒身分電話、社群媒體攻擊等。
- 適用場景：員工安全意識訓練測試、企業反釣魚機制測試。
- 8.物理滲透測試
- 定義：測試實體安全措施的有效性，評估防止未經授權的人員存取敏感區域的能力。
- 目標：偵測實體安全漏洞，如門禁系統的漏洞、監控盲點、安全守衛的反應能力等。
- 特點：
- 測試可能涉及進入限制區、尾隨、克隆訪問卡等。
- 評估設施的實體存取控制、入侵偵測系統等。
- 適用場景：資料中心、公司總部、機房。
- 9.行動應用滲透測試
- 定義：專門針對行動應用程式（如iOS、Android）的滲透測試。
- 目標：發現行動應用程式中的安全漏洞，如資料外洩、不安全的API呼叫、不當的權限使用等。
- 特點：
- 涉及對行動應用程式碼、後端伺服器、資料儲存、通訊加密的測試。
- 使用工具如MobSF、Frida、Burp Suite 等。
- 適用場景：企業行動應用程式、金融應用程式、社群媒體應用程式。
- 10.雲端安全滲透測試
- 定義：測試雲端運算環境的安全性，包括IaaS、PaaS、SaaS等服務模型的安全評估。
- 目標：偵測雲端環境中的設定錯誤、API漏洞、權限設定不當等問題。
- 特點：
- 涉及雲端服務供應商的配置、虛擬機器、容器、儲存服務的安全性測試。
- 特別關注多租戶隔離、API 安全、資料保護等方面。
- 適用場景：使用AWS、Azure、Google Cloud 等的企業雲端環境。
- 11.紅隊測試
- 定義：紅隊測試是一種綜合性的滲透測試，模擬進階持續性威脅（APT）攻擊，目的是全面評估組織的防禦能力。
- 目標：偵測組織對複雜且持久的攻擊的防禦能力，包括從初始滲透到權限提升、橫向移動、資料外洩的整個過程。
- 特點：
- 包含社會工程、物理滲透、網路滲透等多種技術。
- 通常由一組專家團隊（紅隊）進行，目標是全面突破組織的防禦。
- 適用場景：大企業、金融機構、政府部門。
- 12.內部滲透測試
- 定義：模擬內部威脅（如不滿員工、被攻陷的內部網路設備）的攻擊行為，測試組織的內部網路安全。
- 目標：偵測內部網路中可能存在的漏洞、錯誤配置或弱點。
- 特點：
- 涉及對內部網路的橫向移動、權限提升、敏感資料存取等。
- 可揭示內部威脅對系統的影響，並協助加強內部安全防護。
- 適用場景：企業內部網路、組織內部網路系統。
