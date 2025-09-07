# Google Dorking Cheat Sheet

---

## Dork/Operator Reference

| Dork/Operator | Syntax | Example | Purpose / Description |
|---------------|--------|---------|------------------------|
| site: | site:example.com | Show only results from a specific website. |
| inurl: | inurl:admin | Find pages with a specific word in the URL. |
| intitle: | intitle:login | Find pages with a specific word in the title. |
| allintitle: | allintitle:admin login | Find pages with all keywords in the title. |
| intext: | intext:"password" | Find pages that contain specific text in the content. |
| allintext: | allintext:username password | Find pages containing all the words in the body text. |
| filetype: | filetype:pdf OR filetype:xls | Find specific file types like PDF, XLS, DOCX, TXT, SQL, etc. |
| ext: | ext:sql | Same as filetype – find files with a specific extension. |
| cache: | cache:example.com | View the cached version of a webpage saved by Google. |
| link: | link:example.com | Show pages that link to a specific domain (less effective now). |
| related: | related:example.com | Find sites related to the domain. |
| * (Wildcard) | "admin * login" | Use wildcard to replace any word – useful when exact keyword is unknown. |
| " (Quotes) | "confidential report" | Search for exact match of the phrase. |
| OR | "login" OR "signup" | Search for either of the terms. |
| AND | "username" AND "password" | Search for both terms (usually implied by default). |
| - (Exclude) | login -facebook | Exclude specific words from results. |
| define: | define:csrf | Get definition of a word (quick glossary search). |
| site: + filetype: | site:gov.in filetype:xls | Find Excel files in .gov.in domains (sensitive data). |
| intitle: + index of | intitle:"index of" "backup" | Directory listing – often leads to open folders or backup files. |

---

## OSINT Tools & Categories

| Category | Tool/Resource | Purpose / Use-Case | Example Command / Usage | Pro Tip |
|----------|---------------|---------------------|--------------------------|---------|
| 🌐 Domain Info | whois, whoxy, viewdns.info | Domain registration data, expiry, contact info | `whois example.com` | Use whoxy API for automation in scripts |
| 🌐 DNS Recon | dig, nslookup, dnsrecon, dnsenum | Get DNS records, subdomains, mail servers | `dnsrecon -d example.com` | Try zone transfers: `dig AXFR` |
| 🔍 Subdomain Enum | sublist3r, crt.sh, amass, assetfinder | Discover hidden subdomains | `sublist3r -d example.com` | Combine tools for more coverage |
| 🔎 Website Analysis | whatweb, wappalyzer, builtwith, `nmap -sV` | Detect CMS, server tech, plugins | `whatweb example.com` | Use Burp + WhatWeb plugin for deep inspection |
| 🔍 Google Dorking | Google + Dorks | Discover sensitive info, files, backups | `site:example.com filetype:xls` | Use `intitle:"index of"` for open directories |
| 🔒 Leak Search | haveibeenpwned, dehashed, snusbase, intelx.io | Check for leaked passwords, email breaches | `email@example.com in dehashed.com` | Use Dehashed with filters (hash, IP, etc.) |
| 📧 Email OSINT | hunter.io, emailrep.io, mailboxlayer, verify-email.org | Find email patterns, validate emails | `emailrep.io/email@example.com` | Use Hunter to find organization email structure |
| 🕵 Username OSINT | maigret, sherlock, whatsmyname.app, knowem | Check if username exists across social platforms | `python3 maigret.py username` | Maigret gives detailed HTML reports |
| 🧍 People Search | pipl, truecaller, whitepages, social-searcher, zaba search | Gather personal info from name, email, phone | Search `Ali Khan` on pipl.com | Use alias names, maiden names, etc. |
| 📱 Phone Number OSINT | numverify, emobiletracker, sync.me, truecaller | Trace phone number location, identity | Lookup `+91XXXXXXXXXX` in truecaller | Use VoIP detection APIs too |
| 📍 Geolocation | exiftool, osintgram, google reverse image, pic2map | Extract location from images or posts | `exiftool image.jpg` | Many WhatsApp images retain GPS in Exif |
| 📸 Image OSINT | exiftool, fotoforensics, tineye, yandex reverse image | Trace image source, metadata | Upload image to fotoforensics.com | Yandex is better than Google for reverse image |
| 🖼 Social Media Recon | osintgram, instaloader, twint, sn0int, metagoofil | Instagram, Twitter, FB info gathering | `instaloader profile_username` | Twint is powerful even without Twitter API |
| 🗺 Metadata Extract | exiftool, strings, pdf-parser, metagoofil | Pull metadata from files (PDF, images, docs) | `metagoofil -d example.com -t pdf -o result/` | Can reveal usernames, file paths, emails |
| 💻 Public Data Leaks | pastebin, github, reddit, trello, archive.org | Find exposed tokens, passwords, backups | `site:github.com "api_key" AND "example.com"` | Use GitHub dorks & recon-ng GitHub module |
| 🌐 IP OSINT | ipinfo.io, shodan, censys, virustotal | Discover services on IPs, open ports | `shodan host 1.2.3.4` | Check C2 servers, open webcams, routers |
| 🏢 Company OSINT | linkedin, rocketreach, hunter, crunchbase, truelist | Get employee names, email formats, contact info | `Search "Company Name site:linkedin.com/in"` | Use hunter.io with filters for job role, location |
| 👁 Visual OSINT | Mapillary, Google Earth, StreetView, Sentinel Hub | Visual surveillance of locations | Look up specific addresses in StreetView | Combine with satellite image diff tools like sentinelhub |
| 🧰 Frameworks | Maltego, Spiderfoot, Recon-ng, Buscador VM | All-in-one OSINT platforms | `spiderfoot -s example.com` | Automate everything using recon-ng modules |

---
