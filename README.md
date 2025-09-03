Security Scanner – Fast Origin IP & Asset Discovery

📌 OVERVIEW: 
This project is a high-speed, asynchronous security scanner built to uncover hidden web assets, origin IPs, and misconfigured services often left exposed behind providers like Cloudflare.

Unlike traditional scanners or search engines (e.g., Shodan), this tool is designed to:

- Bypass CDN masking and identify real backend servers.

- Map SSL certificates to discover domains and subdomains.

- Scrape and fingerprint websites across multiple ports.

- Store results in MongoDB for fast querying and analysis via an API.

⚡ In short: It’s a powerful reconnaissance tool for red teams, security analysts, and researchers.


🚀 Features

1. Masscan Integration: Lightning-fast IP range scanning (millions of hosts in minutes).

2. SSL Certificate Extraction: Maps Common Name and SAN fields to uncover real domains.

3. Asynchronous Scraper: Collects titles, headers, and first 300 words of responses at scale.

4. Cloudflare Bypass Detection: Identifies origin IPs not in CDN ranges.

5. API + MongoDB Backend: Query results by IP, port, domain, or title (e.g., http://localhost:5000/bytitle?title=nginx&from=0&to=10).

6. Customizable Ports & Protocols: Scan beyond defaults (e.g., login pages on :8080 or :31337).

🛠️Architecture

IP List → Masscan → SSL Cert Extractor → Async Scraper → JSON → API → MongoDB
--------------------------------------------------------------------------------------------------------------

Setup:
# Clone repo
git clone https://github.com/idi100/security-scanner.git
cd security-scanner

# Install dependencies
pip install -r requirements.txt

# VPN
Make sure you turn on your vpn of choice
- I use Mullvad VPN
  
# Run scanner
python server.py
python scanner.py

