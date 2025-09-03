Security Scanner – Fast Origin IP & Asset Discovery
Overview

This project is a high-speed, asynchronous security scanner built to uncover hidden web assets, origin IPs, and misconfigured services often left exposed behind providers like Cloudflare.

Unlike traditional scanners or search engines (e.g., Shodan), this tool is designed to:

Bypass CDN masking and identify real backend servers

Map SSL certificates to discover domains and subdomains

Scrape and fingerprint websites across multiple ports

Store results in MongoDB for fast querying and analysis via an API

In short: it’s a powerful reconnaissance tool for red teams, security analysts, and researchers.

Features

Masscan Integration – Lightning-fast IP range scanning (millions of hosts in minutes)

SSL Certificate Extraction – Maps Common Name and SAN fields to uncover real domains

Asynchronous Scraper – Collects titles, headers, and first 300 words of responses at scale

Cloudflare Bypass Detection – Identifies origin IPs not in CDN ranges

API + MongoDB Backend – Query results by IP, port, domain, or title (e.g., http://localhost:5000/bytitle?title=nginx&from=0&to=10)

Customizable Ports & Protocols – Scan beyond defaults (e.g., login pages on :8080 or :31337)

Architecture
IP List → Masscan → SSL Cert Extractor → Async Scraper → JSON → API → MongoDB

Setup

Clone the repository

git clone https://github.com/idi100/security-scanner.git
cd security-scanner


Install dependencies

pip install -r requirements.txt


Enable VPN
Ensure your VPN is active before scanning.

Example: Mullvad VPN

Start the API server

python server.py


Run the scanner

python scanner.py
