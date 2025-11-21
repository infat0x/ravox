Congratulations on completing your final project\! 🔥 This tool looks highly functional and "advanced."

To make it look professional when you share it on GitHub or in your portfolio, I have prepared a **Premium Level README.md** file below.

This includes all features, installation steps, usage instructions, and details about the AI integration.

-----

### 📄 `README.md` (Copy and save this file)

````markdown
# 🚀 RAVOX - Recon Automated Vulnerability Observation eXecutor

![Bash](https://img.shields.io/badge/Language-Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)
![AI](https://img.shields.io/badge/AI-Mistral_Integrated-FFD700?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-7.5-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-red?style=for-the-badge)

```text
   ____    _    __     __  ___   __  __
  |  _ \  / \   \ \   / / / _ \  \ \/ /
  | |_) |/ _ \   \ \ / / | | | |  \  / 
  |  _ <| ___ \   \ V /  | |_| |  /  \ 
  |_| \_\_| \_\    \_/    \___/  /_/\_\
  Recon Automated Vulnerability Observation eXecutor
````

**RAVOX** is an advanced, automated reconnaissance pipeline designed for Bug Bounty hunters and Penetration Testers. It streamlines the process of asset discovery, chaining together industry-standard tools (`ProjectDiscovery` suite) and enhancing the results with **Generative AI (Mistral AI)** to identify potential vulnerabilities like IDOR, SQLi, and XSS automatically.

-----

## ✨ Key Features

  * **⚡ Automated Pipeline:** Seamlessly chains Subdomain Enumeration -\> DNS Resolution -\> Port Scanning -\> Web Probing -\> Crawling.
  * **🤖 AI-Powered Analysis:** Integrated **Mistral AI** to analyze crawled URLs and highlight high-risk endpoints (IDOR, XSS, SQLi) in a readable text report.
  * **📂 Dynamic Organization:** Automatically creates output directories based on the target domain and current timestamp.
  * **🔶 Proxy Support:** Route traffic through **Burp Suite** or any other HTTP proxy for manual inspection.
  * **🎨 Rich UI/UX:** Features modern progress bars, status icons, and high-intensity color formatting for better readability.
  * **💾 Smart Reporting:** Generates both raw data files and a summarized final report.

-----

## 🛠️ Prerequisites

Before running RAVOX, ensure you have the following tools installed. The script requires **Go (Golang)** and **Python 3**.

### 1\. Install Core Tools (ProjectDiscovery)

```bash
go install -v [github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest](https://github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest)
go install -v [github.com/projectdiscovery/dnsx/cmd/dnsx@latest](https://github.com/projectdiscovery/dnsx/cmd/dnsx@latest)
go install -v [github.com/projectdiscovery/naabu/v2/cmd/naabu@latest](https://github.com/projectdiscovery/naabu/v2/cmd/naabu@latest)
go install -v [github.com/projectdiscovery/httpx/cmd/httpx@latest](https://github.com/projectdiscovery/httpx/cmd/httpx@latest)
go install -v [github.com/projectdiscovery/katana/cmd/katana@latest](https://github.com/projectdiscovery/katana/cmd/katana@latest)
```

### 2\. Install System Dependencies

```bash
# Kali Linux / Debian / Ubuntu
sudo apt update
sudo apt install python3 jq fonts-noto-color-emoji -y
```

-----

## 📥 Installation

Clone the repository and make the script executable:

```bash
git clone [https://github.com/yourusername/ravox.git](https://github.com/yourusername/ravox.git)
cd ravox
chmod +x ravox.sh
```

-----

## 🚀 Usage

You can use RAVOX in **Interactive Mode** (Wizard) or **CLI Mode** (Flags).

### 1\. Interactive Mode (Recommended for beginners)

Simply run the script without arguments:

```bash
./ravox.sh
```

*The wizard will ask for the target domain, output directory, proxy settings, and API keys.*

### 2\. CLI Mode (Automation)

For fast, scripted usage:

```bash
# Basic Scan
./ravox.sh -d example.com

# Scan with AI Analysis (Requires API Key)
./ravox.sh -d example.com --llm

# Scan with Burp Proxy & AI
./ravox.sh -d example.com -p [http://127.0.0.1:8080](http://127.0.0.1:8080) --llm

# Scan from a list of targets
./ravox.sh -l targets.txt
```

### 🚩 Flags

| Flag | Description |
| :--- | :--- |
| `-d`, `--domain` | Target domain (e.g., `tesla.com`) |
| `-l`, `--list` | Path to a file containing a list of domains |
| `-o`, `--output` | Base output directory (Default: `ravox_results`) |
| `-p`, `--proxy` | HTTP Proxy URL (e.g., `http://127.0.0.1:8080`) |
| `--llm` | Enable Mistral AI analysis (Prompt for Key) |
| `--dry-run` | Show commands without executing them |
| `-h`, `--help` | Show the help menu |

-----

## 🧠 AI Integration (Mistral AI)

RAVOX uses the **Mistral AI API** (`mistral-small-latest`) to analyze crawled JavaScript files and API endpoints.

1.  When prompted, enter your **Mistral API Key**.
2.  The tool sends the top 50 crawled URLs to the AI.
3.  The AI analyzes them for keywords and patterns related to **IDOR**, **SQL Injection**, and **XSS**.
4.  A readable report is saved as `llm_analysis.txt` in the output folder.

> **Tip:** You can export your key permanently to avoid typing it every time:
> `export MISTRAL_API_KEY="your_key_here"`

-----

## 📂 Output Structure

RAVOX keeps your workspace clean. Results are saved in: `ravox_results/domain_date_time/`

```text
ravox_results/
└── example.com_2025-11-21_12-00/
    ├── subfinder.txt       # All found subdomains
    ├── dnsx.txt            # Active (resolved) subdomains
    ├── naabu.txt           # Open ports
    ├── httpx.txt           # Live web services (URLs)
    ├── katana.txt          # Crawled endpoints and parameters
    └── llm_analysis.txt    # AI Vulnerability Report 🧠
```

-----

## ⚠️ Disclaimer

**RAVOX is intended for educational purposes and authorized security testing only.**
Do not use this tool on targets you do not have explicit permission to test. The author is not responsible for any misuse or damage caused by this tool.

-----

## 👨‍💻 Author

**Developed by:** [Your Name/Alias]
**Final Project:** Offensive Security Tool Development

-----

*Happy Hunting\! 🚀*

```

### How to use this:
1.  Create a new text file in your project folder.
2.  Copy the code block above.
3.  Paste it into the file.
4.  Save the file as **`README.md`**.

Good luck with your project presentation! 🚀
```
