# 🔍 Nmap Cheat Sheet 

---

## 🛰️ Scanning Options

| Option               | What It Does                          | Example Command                           |
| -------------------- | ------------------------------------- | ----------------------------------------- |
| `10.10.10.0/24`      | Specifies the target network range    | `nmap 10.10.10.0/24`                      |
| `-sn`                | Skips port scanning                   | `nmap -sn 10.10.10.0/24`                  |
| `-Pn`                | Disables ICMP Echo Requests (no ping) | `nmap -Pn 10.10.10.0/24`                  |
| `-n`                 | Avoids DNS resolution                 | `nmap -n 10.10.10.0/24`                   |
| `-PE`                | Ping scan using ICMP Echo Requests    | `nmap -PE 10.10.10.0/24`                  |
| `--packet-trace`     | Shows detailed packet logs            | `nmap --packet-trace 10.10.10.0/24`       |
| `--reason`           | Displays reason for results           | `nmap --reason 10.10.10.0/24`             |
| `--disable-arp-ping` | Disables ARP Ping                     | `nmap --disable-arp-ping 10.10.10.0/24`   |
| `--top-ports=<num>`  | Scans top `<num>` common ports        | `nmap --top-ports=100 10.10.10.0/24`      |
| `-p-`                | Scans all ports                       | `nmap -p- 10.10.10.0/24`                  |
| `-p22-110`           | Scans ports 22 to 110                 | `nmap -p22-110 10.10.10.0/24`             |
| `-p22,25`            | Scans only ports 22 and 25            | `nmap -p22,25 10.10.10.0/24`              |
| `-F`                 | Scans top 100 ports                   | `nmap -F 10.10.10.0/24`                   |
| `-sS`                | TCP SYN scan                          | `nmap -sS 10.10.10.0/24`                  |
| `-sA`                | TCP ACK scan                          | `nmap -sA 10.10.10.0/24`                  |
| `-sU`                | UDP scan                              | `nmap -sU 10.10.10.0/24`                  |
| `-sV`                | Service version detection             | `nmap -sV 10.10.10.0/24`                  |
| `-sC`                | Runs default scripts                  | `nmap -sC 10.10.10.0/24`                  |
| `--script <script>`  | Runs specified script                 | `nmap --script http-title 10.10.10.0/24`  |
| `-O`                 | OS detection                          | `nmap -O 10.10.10.0/24`                   |
| `-A`                 | OS, service, and traceroute detection | `nmap -A 10.10.10.0/24`                   |
| `-D RND:5`           | Uses 5 random decoys                  | `nmap -D RND:5 10.10.10.0/24`             |
| `-e`                 | Specifies network interface           | `nmap -e eth0 10.10.10.0/24`              |
| `-S <IP>`            | Sets source IP                        | `nmap -S 10.10.10.200 10.10.10.0/24`      |
| `-g`                 | Sets source port                      | `nmap -g 80 10.10.10.0/24`                |
| `--dns-server <ns>`  | Custom DNS server                     | `nmap --dns-server 8.8.8.8 10.10.10.0/24` |

---

## 💾 Output Options

| Option | What It Does | Example Command |
|--------|---------------|-----------------|
| `-oA filename` | Saves all formats | `nmap -oA scan_results 10.10.10.0/24` |
| `-oN filename` | Normal text format | `nmap -oN scan.txt 10.10.10.0/24` |
| `-oG filename` | Grepable format | `nmap -oG scan.grep 10.10.10.0/24` |
| `-oX filename` | XML format | `nmap -oX scan.xml 10.10.10.0/24` |

---

## ⚙️ Performance Options

| Option | What It Does | Example Command |
|--------|---------------|-----------------|
| `--max-retries <num>` | Retry limit | `nmap --max-retries 3 10.10.10.0/24` |
| `--stats-every=5s` | Scan progress updates | `nmap --stats-every=5s 10.10.10.0/24` |
| `-v` / `-vv` | Increases verbosity | `nmap -vv 10.10.10.0/24` |
| `--initial-rtt-timeout` | Initial RTT timeout | `nmap --initial-rtt-timeout 50ms 10.10.10.0/24` |
| `--max-rtt-timeout` | Max RTT timeout | `nmap --max-rtt-timeout 100ms 10.10.10.0/24` |
| `--min-rate` | Packet send rate per sec | `nmap --min-rate 300 10.10.10.0/24` |
| `-T <0-5>` | Scan timing (0=slow, 5=fast) | `nmap -T4 10.10.10.0/24` |

---

## 📜 Script Categories

| Category | What It Does | Example Command |
|----------|----------------|-----------------|
| `auth` | Tests for authentication issues | `nmap --script auth 10.10.10.0/24` |
| `broadcast` | Broadcast-based discovery | `nmap --script broadcast 10.10.10.0/24` |
| `brute` | Brute-force logins | `nmap --script brute 10.10.10.0/24` |
| `default` | Runs default scripts (`-sC`) | `nmap -sC 10.10.10.0/24` |
| `discovery` | Identifies services | `nmap --script discovery 10.10.10.0/24` |
| `dos` | Checks DoS vulnerabilities | `nmap --script dos 10.10.10.0/24` |
| `exploit` | Exploits known vulns | `nmap --script exploit 10.10.10.0/24` |
| `external` | Uses external services | `nmap --script external 10.10.10.0/24` |
| `fuzzer` | Sends malformed packets | `nmap --script fuzzer 10.10.10.0/24` |
| `intrusive` | Potentially disruptive scans | `nmap --script intrusive 10.10.10.0/24` |
| `malware` | Malware detection | `nmap --script malware 10.10.10.0/24` |
| `safe` | Safe, non-intrusive scans | `nmap --script safe 10.10.10.0/24` |
| `version` | Detects version info | `nmap --script version 10.10.10.0/24` |
| `vuln` | Vulnerability scanning | `nmap --script vuln 10.10.10.0/24` |
