# Subdomain Enumeration Automation Tool

A powerful, multi-tool automation script for subdomain enumeration, built for bug bounty hunters, web pentesters, and CTF enthusiasts.

---

## 🚀 Features

- Automatically discovers subdomains using multiple tools:
  - `amass`, `assetfinder`, `crt.sh`, `ffuf`, `findomain`, `puredns`, `subfinder`, `sublist3r`
- Live subdomain filtering with `httpx`
- Screenshot capture with `aquatone`
- Merges and deduplicates results
- Supports fast and deep scanning modes
- Stores outputs in a clean directory structure

---

## 🛠 Requirements

Install the following tools and make sure they're accessible in your `$PATH`:

- [`amass`](https://github.com/owasp-amass/amass)
- [`assetfinder`](https://github.com/tomnomnom/assetfinder)
- [`crt.sh`](https://crt.sh/)
- [`curl`](https://curl.se/)
- [`ffuf`](https://github.com/ffuf/ffuf)
- [`findomain`](https://github.com/findomain/findomain)
- [`jq`](https://stedolan.github.io/jq/)
- [`massdns`](https://github.com/blechschmidt/massdns)
- [`puredns`](https://github.com/d3mondev/puredns)
- [`seclists`](https://github.com/danielmiessler/SecLists)
- [`subfinder`](https://github.com/projectdiscovery/subfinder)
- [`sublist3r`](https://github.com/aboul3la/Sublist3r)
- [`httpx`](https://github.com/projectdiscovery/httpx)
- [`aquatone`](https://github.com/michenriksen/aquatone)

---

## 📦 Installation

1. Clone this repo or copy the script locally:
   ```bash
   git clone https://github.com/yourusername/subdomain-toolkit.git
   cd subdomain-toolkit
   chmod +x subdomain_enum.sh
   ```

2. Update the following variables in the script if necessary:
   - `WORDLIST` – location of your subdomain wordlist (defaults to SecLists)
   - `RESOLVER` – path to your DNS resolvers file

---

## ⚙️ Usage

```bash
./subdomain_enum.sh <target-domain> <scan-mode>
```

- `<target-domain>` – The domain to scan (e.g. `example.com`)
- `<scan-mode>` – Either `fast` or `deep`
  - `fast`: skips `amass` for quicker scans
  - `deep`: includes `amass` for comprehensive enumeration

Example:

```bash
./subdomain_enum.sh example.com deep
```

---

## 📁 Output

All outputs are saved under:

```
~/data/<target-domain>/subdomain/
```

Includes:
- Individual tool results (`*.txt`)
- `all.txt`: Merged & unique subdomains
- `httpx.txt`: Live subdomains (status 200)
- Aquatone screenshots and HTML report

---

## 📸 Aquatone Report

After execution, screenshots of live subdomains are saved to:

```
aquatone/screenshots/
```

To view a full HTML report:
```
aquatone/aquatone_report.html
```

---

## 💡 Tip for Creative Hackers

Experiment by:
- Adding `dnsx`, `anubis`, or `github-subdomains`
- Integrating with `notify` or `nuclei` for auto-alerts
- Scheduling with cron for passive recon

---

## 📜 License

Open-source for ethical hacking and educational use only.

---

## 🧠 Learn More

This tool is great for recon in Bug Bounty and Web Penetration Testing programs. Customize and extend it to suit your workflow.

Happy Hacking!
