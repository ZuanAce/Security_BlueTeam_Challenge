# Introduction
The Harvester is a tool that was developed in python. Using this you can gather information like emails, subdomains, hosts, employee names, open ports and banners from different public sources like search engines, PGP key servers, and SHODAN computer database.
This tool is useful for anyone like you who needs to know what an attacker can see about the organization.

# Activity
In the below screenshot, I am performing simple reconnaissance on the domain Google.com, using Duckduckgo as the data source:
using the command *theHarvester -d google.com -l 100 -b duckduckgo*
(tool) (target domain = google.com) (list 100 results max) (source = duckduckgo)

**Notes**: Some of the sources such as linkedin, twitter, and google can't be used anymore since version 4.2.0

![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/a278d431-209f-4740-a769-4b6c2ba97f1d)

Here are all the of the sources that can be used as data source in the 4.4.3 version:
- anubis: Anubis-DB - https://github.com/jonluca/anubis
- bevigil: CloudSEK BeVigil scans mobile application for OSINT assets (Requires an API key, see below.) - https://bevigil.com/osint-api
- baidu: Baidu search engine - www.baidu.com
- binaryedge: List of known subdomains (Requires an API key, see below.) - https://www.binaryedge.io
- bing: Microsoft search engine - https://www.bing.com
- bingapi: Microsoft search engine, through the API (Requires an API key, see below.)
- brave: Brave search engine - https://search.brave.com/
- bufferoverun: (Requires an API key, see below.) https://tls.bufferover.run
- censys: Censys search engine will use certificates searches to enumerate subdomains and gather emails
(Requires an API key, see below.) https://censys.io
- certspotter: Cert Spotter monitors Certificate Transparency logs - https://sslmate.com/certspotter/
- criminalip: Specialized Cyber Threat Intelligence (CTI) search engine (Requires an API key, see below.) - https://www.criminalip.io
- crtsh: Comodo Certificate search - https://crt.sh
- dnsdumpster: DNSdumpster search engine - https://dnsdumpster.com
- duckduckgo: DuckDuckGo search engine - https://duckduckgo.com
- fullhunt: Next-generation attack surface security platform (Requires an API key, see below.) - https://fullhunt.io
- github-code: GitHub code search engine (Requires a GitHub Personal Access Token, see below.) - www.github.com
- hackertarget: Online vulnerability scanners and network intelligence to help organizations - https://hackertarget.com
- hunter: Hunter search engine (Requires an API key, see below.) - https://hunter.io
- hunterhow: Internet search engines for security researchers (Requires an API key, see below.) - https://hunter.how
- intelx: Intelx search engine (Requires an API key, see below.) - http://intelx.io
- netlas: A Shodan or Censys competitor (Requires an API key, see below.) - https://app.netlas.io
- onyphe: Cyber defense search engine (Requires an API key, see below.) - https://www.onyphe.io/
- otx: AlienVault open threat exchange - https://otx.alienvault.com
- pentestTools: Cloud-based toolkit for offensive security testing, focused on web applications and network penetration
testing (Requires an API key, see below.) - https://pentest-tools.com/
- projecDiscovery: We actively collect and maintain internet-wide assets data, to enhance research and analyse changes around
DNS for better insights (Requires an API key, see below.) - https://chaos.projectdiscovery.io
- rapiddns: DNS query tool which make querying subdomains or sites of a same IP easy! https://rapiddns.io
- rocketreach: Access real-time verified personal/professional emails, phone numbers, and social media links (Requires an API key,
see below.) - https://rocketreach.co
- securityTrails: Security Trails search engine, the world's largest repository of historical DNS data (Requires an API key, see
below.) - https://securitytrails.com
- -s, --shodan: Shodan search engine will search for ports and banners from discovered hosts (Requires an API key, see below.)
https://shodan.io
- sitedossier: Find available information on a site - http://www.sitedossier.com
- subdomaincenter: A subdomain finder tool used to find subdomains of a given domain - https://www.subdomain.center/
- subdomainfinderc99: A subdomain finder is a tool used to find the subdomains of a given domain - https://subdomainfinder.c99.nl
- threatminer: Data mining for threat intelligence - https://www.threatminer.org/
- tomba: Tomba search engine (Requires an API key, see below.) - https://tomba.io
- urlscan: A sandbox for the web that is a URL and website scanner - https://urlscan.io
- vhost: Bing virtual hosts search
- virustotal: Domain search (Requires an API key, see below.) - https://www.virustotal.com
- yahoo: Yahoo search engine
- zoomeye: China's version of Shodan (Requires an API key, see below.) - https://www.zoomeye.org

# Resources
- https://www.kali.org/tools/theharvester/
- https://github.com/laramies/theHarvester
- https://www.oreilly.com/library/view/web-penetration-testing/9781788623377/71203ba9-3894-4192-af66-1003405ab8ed.xhtml
