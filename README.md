# SKillHorizon-Internships
Passive Footprinting & Reconnaissance – Assignment 2
Definition

Passive Reconnaissance (Footprinting) is the process of collecting publicly available information about a target system, domain, or organization without directly engaging with its systems. This helps ethical hackers and penetration testers understand the target’s digital footprint before performing active tests.

Unlike active recon, passive recon does not interact directly with the target, making it stealthier and safer.

Objective

The goal of this assignment is to perform passive recon on a chosen domain using Kali Linux tools. You will:

Collect domain and DNS information

Discover subdomains

Gather emails and employee information

Extract metadata from documents

Use Google Dorks to search for sensitive data

Explore OSINT sources (social media, GitHub, etc.)

Collect URLs, filter JavaScript files, and check for secrets

Tools Used

whois, dig, nslookup → Domain & DNS info

subfinder, assetfinder, amass → Subdomain enumeration

theHarvester → Emails & employee data

metagoofil, exiftool, strings → Metadata extraction

Google Dorking → Advanced search queries

Maltego (CE), SpiderFoot → OSINT tools

gau, katana, linkfinder → Collect URLs & JS files

JSleak → Find possible secrets in JS files

Step-by-Step Tasks with Examples
1. Domain Information Gathering
whois example.com
dig example.com
nslookup example.com

2. Subdomain Enumeration
subfinder -d example.com
assetfinder --subs-only example.com
amass enum -passive -d example.com

3. Email & Employee Information
theHarvester -d example.com -l 100 -b google

4. Metadata Extraction
exiftool sample.pdf
strings document.docx | less

5. Google Dorking (manual in browser)
site:example.com filetype:pdf
site:example.com intitle:"index of"

6. Social Media & OSINT

Use Maltego CE or SpiderFoot to analyze target’s online presence.

7. Collect URLs & Filter JS Files
gau example.com | tee urls.txt
katana -u example.com -o katana_urls.txt

8. Search for Secrets in JS Files
cat urls.txt | grep ".js" | tee jsfiles.txt
jsleak -f jsfiles.txt

Deliverables

Submit a Passive Recon Report including:

Target domain name

WHOIS & DNS findings

Subdomains discovered

Email IDs or employee data (if found)

Metadata information (with screenshots)

Google dorks attempted (with results)

OSINT summary

URLs & JS leak findings

Conclusion: Possible attack surfaces
