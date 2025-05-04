# Subdomain Enumeration Tool (subdenum)

A fast and flexible Bash-based subdomain enumeration toolkit that uses a wide range of tools and techniques to find, validate, and visualize subdomains for a target domain.

---

## 🚀 Features

- Multi-source subdomain enumeration using:
  - `amass`, `assetfinder`, `crt.sh`, `ffuf`, `findomain`, `puredns`, `subfinder`, `sublist3r`
- DNS brute forcing using `puredns` and a curated Seclists wordlist
- HTTP probing using `httpx`
- Screenshot automation using `aquatone`
- Dynamic scan modes: `fast` and `deep`
- Clean output organization in per-target directories

---

## 🛠 Requirements

Make sure these tools are installed and available in your `$PATH`:

- [`assetfinder`](https://github.com/tomnomnom/assetfinder)
- [`jq`](https://stedolan.github.io/jq/)
- [`curl`](https://curl.se/)
- [`subfinder`](https://github.com/projectdiscovery/subfinder)
- [`sublist3r`](https://github.com/aboul3la/Sublist3r)
- [`findomain`](https://github.com/findomain/findomain)
- [`puredns`](https://github.com/d3mondev/puredns)
- [`massdns`](https://github.com/blechschmidt/massdns)
- [`ffuf`](https://github.com/ffuf/ffuf)
- [`httpx`](https://github.com/projectdiscovery/httpx)
- [`aquatone`](https://github.com/michenriksen/aquatone)
- [`amass`](https://github.com/owasp-amass/amass) *(used in deep mode)*
- [`seclists`](https://github.com/danielmiessler/SecLists)

> ⚠️ The script uses the Seclists file `deepmagic.com-prefixes-top500.txt`. Ensure it exists at `/usr/share/seclists/Discovery/DNS/`.

---

## 📦 Installation

1. Clone this repo or copy the script locally:
   ```bash
   git clone https://github.com/yourusername/subdenum.git
   cd subdenum
   chmod +x subdenum.sh
   ```

2. Update the `WORDLIST` and `RESOLVER` variables in the script if needed.

---

## ⚙️ Usage

```bash
./subdenum.sh <target-domain> <scan-mode>
```

- `<target-domain>` – Domain you want to scan (e.g. `example.com`)
- `<scan-mode>` – `fast` or `deep` (deep enables `amass`)

Example:

```bash
./subdenum.sh example.com deep
```

---

## 📁 Output Structure

All outputs are saved in:

```
~/data/<target-domain>/subdomain/
```

Includes:
- One file per tool (`*.txt`)
- `sort.txt`: merged, unique subdomains
- `httpx.txt`: live subdomains with HTTP status
- `aquatone/`: screenshots and HTML report

---

## 📸 Visualization

After the scan completes:

- View screenshots in:
  ```
  ~/data/<target-domain>/subdomain/aquatone/screenshots/
  ```
- HTML overview report:
  ```
  ~/data/<target-domain>/subdomain/aquatone/aquatone_report.html
  ```

---

## 💡 Pro Tips

- Extend functionality by adding `dnsx`, `anubis`, or GitHub-based enumeration.
- Use `notify` or `slack` scripts to get real-time results.
- Automate regular scans with cronjobs or systemd timers.

---

## 📜 License

This project is open-source and intended for educational and ethical hacking use only.

---

## 🧠 Stay Creative

Explore, break, build, and learn. Tailor the script to your recon workflow for optimal results.

Happy Hunting!
