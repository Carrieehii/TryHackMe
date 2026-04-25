# TryHackMe Pre-Security Cheat Sheet
> A quick reference for key concepts, acronyms, and terms across the Pre-Security path.
> Written in plain english — no textbook definitions.

---

## 1. Network Fundamentals

### Core Concepts
| Term | What it actually means |
|------|----------------------|
| **Network** | Two or more devices connected and able to communicate |
| **Internet** | A massive global network of networks |
| **IP Address** | A unique address for a device on a network — like a postal address |
| **MAC Address** | A permanent hardware ID burned into a network card — like a serial number |
| **Packet** | A small chunk of data — large files are broken into packets to be sent and reassembled |
| **Frame** | A packet wrapped with extra info (MAC addresses) for delivery on a local network |
| **Bandwidth** | How much data can move through a connection at once |
| **Ping** | A tool to test if a device is reachable and how long it takes to respond |

### Key Acronyms
| Acronym | Stands For | Plain English |
|---------|-----------|---------------|
| **LAN** | Local Area Network | Your home or office network |
| **WAN** | Wide Area Network | A network across large distances — the internet is the biggest WAN |
| **IP** | Internet Protocol | The rules for addressing and routing data across networks |
| **MAC** | Media Access Control | The hardware address of a network device |
| **DHCP** | Dynamic Host Configuration Protocol | Automatically gives devices an IP address when they join a network |
| **ARP** | Address Resolution Protocol | Figures out which MAC address belongs to which IP address |
| **DNS** | Domain Name System | Translates website names (google.com) into IP addresses |
| **NAT** | Network Address Translation | Lets multiple devices share one public IP address (what your router does) |
| **VPN** | Virtual Private Network | Creates an encrypted tunnel so your traffic looks like it comes from elsewhere |

### OSI Model (7 Layers)
> Think of it as how data travels from one device to another — each layer has a job.

| Layer | Name | Job | Example |
|-------|------|-----|---------|
| 7 | Application | What the user sees | HTTP, DNS, FTP |
| 6 | Presentation | Formats/encrypts data | SSL/TLS |
| 5 | Session | Manages connections | Login sessions |
| 4 | Transport | Breaks data into chunks, ensures delivery | TCP, UDP |
| 3 | Network | Routing between networks | IP addresses |
| 2 | Data Link | Delivery on local network | MAC addresses, frames |
| 1 | Physical | Actual cables and signals | Ethernet, Wi-Fi |

> **Memory trick:** All People Seem To Need Data Processing (bottom to top)

### TCP vs UDP
| | TCP | UDP |
|-|-----|-----|
| **Reliable?** | Yes — checks everything arrived | No — just sends and hopes |
| **Speed** | Slower | Faster |
| **Used for** | Web browsing, emails, file transfers | Video streaming, gaming, DNS |

### Subnetting
| Term | Plain English |
|------|--------------|
| **Subnet** | A smaller network carved out of a larger one |
| **Subnet Mask** | Defines which part of an IP is the network and which is the device |
| **CIDR** | A shorthand for subnet masks — e.g. /24 means 256 addresses |
| **Gateway** | The device that connects your network to another (usually your router) |

### Extending Networks
| Term | Plain English |
|------|--------------|
| **Port Forwarding** | Lets outside traffic reach a specific device inside your network |
| **Firewall** | Filters traffic — blocks what shouldn't get through |
| **Port** | A numbered door on a device — different services use different ports |

**Common ports worth knowing:**
- 80 — HTTP (web, unencrypted)
- 443 — HTTPS (web, encrypted)
- 22 — SSH (remote terminal access)
- 21 — FTP (file transfer)
- 3389 — RDP (Windows remote desktop)

---

## 2. How the Web Works

### Key Acronyms
| Acronym | Stands For | Plain English |
|---------|-----------|---------------|
| **HTTP** | HyperText Transfer Protocol | How your browser requests web pages |
| **HTTPS** | HTTP Secure | HTTP with encryption — the padlock in your browser |
| **URL** | Uniform Resource Locator | A web address |
| **DNS** | Domain Name System | Converts domain names to IPs (also in networking but heavily web-related) |
| **CDN** | Content Delivery Network | Copies of a website stored closer to users for faster loading |
| **WAF** | Web Application Firewall | Filters malicious web traffic before it hits the server |
| **HTML** | HyperText Markup Language | The structure of a web page |
| **JS** | JavaScript | Makes web pages interactive |
| **SSL/TLS** | Secure Sockets Layer / Transport Layer Security | The encryption behind HTTPS |

### HTTP Methods
| Method | What it does |
|--------|-------------|
| **GET** | Requests data (loading a page) |
| **POST** | Sends data (submitting a form) |
| **PUT** | Updates existing data |
| **DELETE** | Removes data |

### HTTP Status Codes
| Code | Meaning |
|------|---------|
| 200 | OK — everything worked |
| 301 | Moved Permanently — page has a new address |
| 403 | Forbidden — you don't have permission |
| 404 | Not Found — page doesn't exist |
| 500 | Server Error — something broke on the server |

### DNS Record Types
| Record | Purpose |
|--------|---------|
| **A** | Maps domain to IPv4 address |
| **AAAA** | Maps domain to IPv6 address |
| **CNAME** | Points one domain to another domain |
| **MX** | Mail server for the domain |
| **TXT** | Text records — used for verification, can leak info |

### How a Web Request Works (simplified)
1. You type a URL
2. DNS looks up the IP for that domain
3. Browser sends HTTP request to that IP
4. Server responds with the page content
5. Browser renders HTML/CSS/JS

### Other Web Terms
| Term | Plain English |
|------|--------------|
| **Cookie** | Small file stored in your browser — keeps you logged in, tracks sessions |
| **Session** | A period of activity between your browser and a server |
| **Load Balancer** | Spreads traffic across multiple servers so none get overwhelmed |
| **Database** | Where websites store their data |
| **Static Content** | Files that don't change — images, CSS |
| **Dynamic Content** | Pages generated on the fly based on user/data |

---

## 3. Linux Fundamentals

### Essential Commands
| Command | What it does |
|---------|-------------|
| `ls` | List files in current directory |
| `cd` | Change directory |
| `pwd` | Show current directory path |
| `cat` | Display file contents |
| `find` | Search for files |
| `grep` | Search inside files for text |
| `echo` | Print text to screen |
| `whoami` | Show current user |
| `sudo` | Run command as administrator |
| `chmod` | Change file permissions |
| `ps` | Show running processes |
| `ssh` | Connect to a remote machine securely |

### File System Structure
| Path | What's there |
|------|-------------|
| `/` | Root — top of everything |
| `/home` | User home directories |
| `/etc` | Config files |
| `/var` | Logs and variable data |
| `/tmp` | Temporary files — writable by anyone |
| `/bin` | Essential commands |
| `/root` | Home directory for the root user |

### Key Terms
| Term | Plain English |
|------|--------------|
| **Shell** | The interface where you type commands |
| **Terminal** | The window you run the shell in |
| **Root** | The superuser — has full control of the system |
| **Permission** | Controls who can read, write, or execute a file |
| **Package Manager** | Tool for installing software (apt on Ubuntu/Debian) |
| **Process** | A running program |
| **Flag/Switch** | An option added to a command e.g. `ls -la` |
| **Pipe** | Sends output of one command into another — `|` symbol |

---

## 4. Windows Fundamentals

### Key Terms
| Term | Plain English |
|------|--------------|
| **Registry** | A database storing Windows settings and config — important in forensics and malware analysis |
| **Active Directory** | Microsoft's system for managing users and computers across a network |
| **RDP** | Remote Desktop Protocol — lets you control a Windows machine remotely |
| **UAC** | User Account Control — prompts you before allowing system changes |
| **Task Manager** | Shows running processes and resource usage |
| **PowerShell** | Windows' powerful command line — like Linux terminal but for Windows |
| **CMD** | Older Windows command prompt |
| **NTFS** | Windows file system — handles permissions and encryption |
| **SMB** | Protocol Windows uses to share files across a network |

### Key Acronyms
| Acronym | Stands For | Plain English |
|---------|-----------|---------------|
| **AD** | Active Directory | Central system for managing Windows networks |
| **GPO** | Group Policy Object | Rules pushed out to computers across a Windows network |
| **RDP** | Remote Desktop Protocol | Windows remote access tool |
| **UAC** | User Account Control | Windows permission prompt |
| **NTFS** | New Technology File System | Windows file system |
| **SMB** | Server Message Block | Windows file sharing protocol — famously exploited by WannaCry |
| **SAM** | Security Account Manager | Where Windows stores password hashes locally |

---

## 5. General Security Concepts

### Key Terms
| Term | Plain English |
|------|--------------|
| **Vulnerability** | A weakness that can be exploited |
| **Exploit** | Code or technique that takes advantage of a vulnerability |
| **Payload** | The part of an attack that does the actual damage |
| **Enumeration** | Gathering information about a target |
| **Privilege Escalation** | Going from a basic user to admin/root |
| **Reverse Shell** | The target machine connects back to the attacker |
| **Bind Shell** | The attacker connects to a listener on the target |
| **CTF** | Capture The Flag — security challenges where you find hidden flags |
| **Flag** | A text string you find to prove you completed a challenge e.g. THM{example} |

### Attack Types (intro level)
| Attack | Plain English |
|--------|-------------|
| **Phishing** | Fake emails/sites to steal credentials |
| **Brute Force** | Trying every possible password until one works |
| **SQL Injection** | Inserting malicious database commands into a form |
| **XSS** | Cross-Site Scripting — injecting scripts into web pages |
| **MITM** | Man in the Middle — intercepting traffic between two parties |

---

> **Remember:** You don't need to memorise all of this upfront.
> Come back to this when something comes up in a room and you need a quick reminder.
> The doing is what makes it stick.
