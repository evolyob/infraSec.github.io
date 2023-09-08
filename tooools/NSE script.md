nmap -vv -sU -Pn -T4 --top-ports 200 <traget>
nmap -Pn --top ports 1000 -sU --stats-every 3m --max-retries 1 -T3 <traget>
nmap -vv -p <port> --script=all <target>// find the vunl
--version-intensity<0-9> //查詢資料庫的深度範圍是 0 ~ 9，預設是 7
-sV //(Connect)列舉開啟服務的詳細版本
-Pn //跳過刺探步驟，直接進行掃描
-sT -O //(Connect)去猜測檢測目標的作業系統版本
-oN <logfile> //輸出到 logfile 檔案與螢幕上

- [ ] 升級nmap資料庫
>nmap --script-updatedb 

- [ ] 漏洞掃描
>nmap -sV --script vuln <target>

- [ ] 是否有CSRF漏洞
>nmap -sV --script http-csrf <target>

- [ ] 是否有XSS漏洞
>nmap -sV --script http-xssed <target>

- [ ] 首頁haeders資訊
>nmap --script http-haeders <target>

- [ ] 主機獲取時間
>nmap --script http-date -p 443 

- [ ] 檢查可存在風險，感覺只是告訴我能用什麼方式。
>nmap --script http-methods -p 443 

- [ ] 目錄結構
>nmapnmap --script http-sitemap-generator -p 443 

- [ ] 443 port憑證
>nmap --script ssl-cert -p 443 <target>

- [ ] 443 port cipher
>nmap --script ssl-enum-ciphers -p 443 <target>

- [ ] 22 port使用的cipher
>nmap --script ssh2-enum-algos -p 22 <target>

- [ ] 發現文件
>nmap -sV --script http-enum <target>

- [ ] 路由追蹤
>nmap --traceroute -sP <target>
>tracepath -n <target> 

- [ ] 探測防火牆規則
>nmap --script firewalk --traceroute <target>

- [ ] 探測WAF
>nmap -p80,443 --script http-waf-detect <>
>nmap -p80,443 --script http-waf-fingerprint <>