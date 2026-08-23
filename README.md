<div align="center">

```
███╗   ███╗██╗███╗   ██╗██╗███████╗████████╗ █████╗ ██████╗  ██████╗ ██████╗ ██████╗ ██╗   ██╗
████╗ ████║██║████╗  ██║██║██╔════╝╚══██╔══╝██╔══██╗██╔══██╗██╔═══██╗██╔══██╗██══██╗╚██╗ ██╔╝
██╔████╔██║██║██╔██╗ ██║██║███████╗   ██║   ███████║██████╔╝██║   ██║██████╔╝██████╔╝ ╚████╔╝
██║╚██╔╝██║██║██║╚██╗██║██║╚════██║   ██║   ██╔══██║██╔══██╗██║   ██║██══██╗██══██╗  ╚██╔╝
██║ ╚═╝ ██║██║██║ ╚████║██║███████║   ██║   ██║  ██║██║  ██║╚██████╔╝██║  ██║██║  ██║   ██║
╚═╝     ╚═╝╚═╝╚═╝  ╚═══╝╚═╝╚══════╝   ╚═╝   ╚═╝  ╚═╝╚═════╝ ╚═════╝ ╚═════╝ ╚═════╝   ╚═╝
```

# 🔴 Malicious IP Threat Intelligence Feed
### Community-curated list of active malicious IP addresses for network defense

![Feed Status](https://img.shields.io/badge/Feed-ACTIVE-00ff41?style=for-the-badge)
![Total IPs](https://img.shields.io/badge/Total_IPs-149,000+-00ff41?style=for-the-badge)
![Last Update](https://img.shields.io/github/last-commit/amitambekar510/Malicious-IP-Threat-List?style=for-the-badge&label=Updated&color=00ff41)
![Auto-Update](https://img.shields.io/badge/Auto_Update-Every_12h-1abc9c?style=for-the-badge&logo=githubactions)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

</div>

---

## 📥 RAW Feed Links (Direct Integration — No Auth Required)

| Feed | RAW URL | Count | Format |
|------|---------|-------|--------|
| **Primary (Part 1)** | `https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt` | ~100,000 | Plain text, 1 IP/line |
| **Overflow (Part 2)** | `https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List_aa` | ~49,000 | Plain text, 1 IP/line |

> 💡 **New partition files** (Part 3, 4, etc.) are created automatically when Part 1 reaches 100,000 entries. Update your tool configs to include all part URLs.

---

## 📊 Feed Statistics

| Metric | Value |
|--------|-------|
| **Total Unique IPs** | 149,000+ |
| **Partition Files** | 2 (Part 1: 100K, Part 2: 49K) |
| **Update Frequency** | Every 12 hours (automated via GitHub Actions) |
| **Sources** | 7+ intelligence feeds |
| **Validation** | VirusTotal (≥3 detections), AbuseIPDB (≥25%), Cisco Talos |
| **Deduplication** | Multi-layer (Bloom filter + Git history + Cross-partition) |
| **False Positive Rate** | < 0.1% (estimated) |

### Threat Categories Covered

| Category | Tag | Percentage | Description |
|----------|-----|------------|-------------|
| Command & Control | `[C2]` | 42% | Botnet C2, RAT callbacks, implant beacons |
| Scanner/Reconnaissance | `[SCAN]` | 31% | Port scanners, vulnerability scanners, recon |
| Malware Delivery | `[MALWARE]` | 18% | Payload hosting, droppers, exploit kits |
| Spam Infrastructure | `[SPAM]` | 6% | Spam relays, bulk mailer IPs |
| Tor Exit Nodes | `[TOR]` | 3% | Tor network exit relays |

---

## 🔄 Automated Update Pipeline

```mermaid
flowchart TB
    subgraph Sources["🔍 Threat Intelligence Sources"]
        S1[AbuseIPDB API\n(High-confidence abusive IPs)]
        S2[FireHOL Blocklists\n(Level 1-4 community lists)]
        S3[Tor Project\n(Current exit nodes)]
        S4[AlienVault OTX\n(Pulses with IP indicators)]
    end

    Collect["🤖 Automated Collection\n(Every 12h via GitHub Actions)"]
    Validate["✅ Multi-Source Validation\nVT ≥3 · AbuseIPDB ≥25% · Talos"]
    Dedup["🚫 Zero-Duplicate Guarantee\nBloom Filter + Git History + Cross-Partition"]
    Repos["📦 Partitioned Repositories\nPart 1: 100K · Part 2: 100K · Auto-scaling"]
    Deploy["🚀 Direct Tool Integration\nPalo Alto · FortiGate · Sentinel · Splunk · QRadar · CrowdStrike · ELK · MISP"]

    Sources --> Collect --> Validate --> Dedup --> Repos --> Deploy

    classDef source fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#1b5e20;
    classDef process fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#0d47a1;
    classDef output fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px,color:#4a148c;
    classDef final fill:#fff3e0,stroke:#ef6c00,stroke-width:2px,color:#e65100;

    class S1,S2,S3,S4 source;
    class Collect,Validate,Dedup process;
    class Repos output;
    class Deploy final;
```

---

## 🛠️ Security Tool Integration Guides

<div align="center">

### Quick Reference — All Platforms Support 12h Refresh

| Platform | Integration Type | Config Guide |
|----------|------------------|--------------|
| **Palo Alto Networks** | External Dynamic Lists (EDL) | [📖 Guide](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/docs/integration-paloalto.md) |
| **FortiGate / FortiSIEM** | External Connectors → Threat Feed | [📖 Guide](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/docs/integration-fortigate.md) |
| **Sophos XG/XGS** | Sophos Central IoC Management | [📖 Guide](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/docs/integration-sophos.md) |
| **Microsoft Sentinel** | Logic App + Threat Intelligence | [📖 Guide](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/docs/integration-sentinel.md) |
| **Splunk ES** | Intelligence Downloads | [📖 Guide](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/docs/integration-splunk.md) |
| **IBM QRadar** | Reference Sets + API | [📖 Guide](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/docs/integration-qradar.md) |
| **CrowdStrike Falcon** | Custom IOC Management | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-crowdstrike.md) |
| **ELK Stack** | Logstash http_poller | [📄 Pipeline](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/elk-pipeline.conf) |
| **MISP** | Freetext Feed Import | [🐍 Script](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/misp_import.py) |
| **SentinelOne** | Bulk IOC Import | [🐍 Script](https://github.com/amitambekar510/Malicious-IP-Threat-List/blob/main/sentinelone_import.py) |

</div>

### 🔥 Palo Alto Networks (NGFW / Panorama)

**Objects → External Dynamic Lists → Add**

```yaml
List 1 — Primary IPs:
  Name:        GitHub-TI-Malicious-IPs-P1
  Type:        IP List
  Source:      https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt
  Refresh:     Every 12 hours (or Daily at 02:00)

List 2 — Overflow IPs:
  Name:        GitHub-TI-Malicious-IPs-P2
  Type:        IP List
  Source:      https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List_aa
  Refresh:     Every 12 hours
```

**Security Policy**: Apply both lists → Action: **Deny** | Log: **Yes**

**CLI Verification:**
```bash
show object external-list all
request system external-list refresh type ip name GitHub-TI-Malicious-IPs-P1
```

---

### 🔵 Sophos Firewall (XG / XGS)

**Option A — Sophos Central (Recommended):**
```
Sophos Central → Threat Intelligence → IoC Management → Add IoCs
  Type:   IP Address
  Action: Block
  Source: Paste RAW URLs above
```

**Option B — Firewall Admin Console:**
```
Hosts and Services → IP Host → Add
  Name: GitHub-TI-Malicious-IP-Group
  Type: IP List (import from URL)
Reference in Firewall Rules → Action: Drop
```

---

### 🔵 Microsoft Sentinel / Defender TI

```
Threat Intelligence → Import Indicators
→ Logic App connector with RAW URL
→ Map: networkIP
→ Schedule: Every 12 hours
→ Confidence: 75
→ ValidUntil: +30 days from ingestion
```

**Logic App Flow:**
```json
{
  "trigger": { "type": "Recurrence", "frequency": "Hour", "interval": 12 },
  "actions": [
    { "type": "Http", "method": "GET", "uri": "https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt" },
    { "type": "ParseCSV", "delimiter": "\n" },
    { "type": "SecurityInsights", "operation": "UploadIndicators", "indicatorType": "networkIPv4" }
  ]
}
```

---

### 🟠 Splunk SIEM (Enterprise Security)

```
Enterprise Security → Intelligence Downloads → New
  Name:     GitHub-TI-Malicious-IPs
  URL:      https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt
  Type:     ip_intel
  Interval: 43200 (12 hours)
  Fields:   ip → indicator
```

**Search Example:**
```spl
| inputlookup malicious_ips.csv
| lookup malicious_ips.csv ip AS src_ip OUTPUT threat_label
| where isnotnull(threat_label)
```

---

### 🟣 IBM QRadar

```
Admin → Reference Data → Reference Sets
→ Create Set: "Malicious_IPs" (Type: IP)
→ Schedule pull via Reference Data Management API
```

**API Script:**
```bash
#!/bin/bash
curl -s "https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt" \
  | grep -v "^#" | grep -v "^$" \
  | while read ip; do
    curl -X POST "https://<qradar>/api/reference_data/sets/Malicious_IPs" \
      -H "SEC: <API_TOKEN>" -d "value=$ip"
  done
```

---

### 🔴 FortiGate / FortiSIEM

```
Security Fabric → External Connectors → Threat Feed → Create New
  Feed 1: GitHub-TI-IPs-P1 → https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt → Type: IP Address
  Feed 2: GitHub-TI-IPs-P2 → https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List_aa → Type: IP Address
  Refresh: Every 12 hours
→ Reference in Firewall Policy → Action: Deny
```

---

### 🟢 CrowdStrike Falcon

```
Threat Intelligence → Indicators → Custom IOC Management
→ Upload IOCs → Bulk Import (TXT file)
→ Map: indicator / type: IP / action: Block
```

---

### 🔷 MISP (Open Source TIP)

```bash
# Import IPs via CLI
curl -s "https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt" \
  | python3 misp_import.py --type ip-dst --feed github-ti --org "Personal TI"

# Or use MISP UI:
# Sync → Feeds → Add Feed
#   URL: https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt
#   Format: freetext
#   Pull: Every 12h
```

---

### 📊 ELK Stack (Logstash + Kibana)

Save as `/etc/logstash/conf.d/github-ti-ip-feed.conf`:

```ruby
input {
  http_poller {
    urls => {
      github_ips_p1 => "https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt"
      github_ips_p2 => "https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List_aa"
    }
    request_timeout => 60
    schedule        => { "every" => "12h" }
    codec           => "line"
    add_field       => { "indicator_kind" => "ip" }
  }
}

filter {
  if [message] =~ /^\s*#/ or [message] =~ /^\s*$/ { drop { } }
  mutate { strip => ["message"] }
  mutate {
    add_field => {
      "[threat][feed][name]"      => "GitHub-TI-IP"
      "[threat][indicator][type]" => "ipv4"
      "[event][category]"         => "threat"
      "[event][type]"             => "indicator"
    }
  }
  ruby { code => 'event.set("[threat][indicator][last_seen]", Time.now.utc.iso8601)' }
  mutate { add_field => { "[threat][indicator][ip]" => "%{message}" } }
  fingerprint {
    source => ["message"]
    target => "[@metadata][doc_id]"
    method => "SHA256"
  }
  mutate { remove_field => ["indicator_kind", "message", "@version"] }
}

output {
  elasticsearch {
    hosts         => ["https://localhost:9200"]
    index         => "github-ti-ip-feed"
    document_id   => "%{[@metadata][doc_id]}"
    action        => "update"
    doc_as_upsert => true
  }
}
```

**Kibana Detection Rule:**
```json
{
  "name": "GitHub TI — Malicious IP Match",
  "type": "threat_match",
  "index": ["logs-*", "filebeat-*"],
  "threat_index": ["github-ti-ip-feed"],
  "threat_mapping": [
    { "entries": [{ "field": "source.ip", "type": "mapping", "value": "threat.indicator.ip" }] }
  ],
  "severity": "high",
  "risk_score": 75
}
```

---

### 🟣 SentinelOne EDR/XDR

**Python Bulk Import:**
```python
import requests

S1_URL   = "https://<your-instance>.sentinelone.net"
S1_TOKEN = "<your-api-token>"
FEED_URL = "https://raw.githubusercontent.com/amitambekar510/Malicious-IP-Threat-List/main/Malicious-IP-Threat-List.txt"

iocs = requests.get(FEED_URL).text.splitlines()
iocs = [i for i in iocs if i and not i.startswith('#')]

indicators = [
  {
    "type": "IP",
    "value": ip,
    "source": "GitHub-TI",
    "description": "Malicious IP — GitHub Threat Intelligence Feed",
    "method": "BLOCK"
  }
  for ip in iocs
]

headers = {"Authorization": f"ApiToken {S1_TOKEN}", "Content-Type": "application/json"}
response = requests.post(
  f"{S1_URL}/web/api/v2.1/threat-intelligence/iocs",
  headers=headers, json={"data": indicators}
)
print(f"Imported {len(indicators)} IPs — Status: {response.status_code}")
```

---

## 📁 Repository Structure

```
Malicious-IP-Threat-List/
├── Malicious-IP-Threat-List.txt          # Part 1 (1-100,000 IPs)
├── Malicious-IP-Threat-List_aa           # Part 2 (100,001-200,000)
├── Malicious-IP-Threat-List_part03.txt   # Part 3 (auto-created)
├── README.md                             # This file
├── CHANGELOG.md                          # Update history
├── CONTRIBUTING.md                       # Contribution guide
├── LICENSE                               # MIT License
├── elk-pipeline.conf                     # Logstash pipeline config
├── misp_import.py                        # MISP import script
├── sentinelone_import.py                 # SentinelOne import script
└── docs/
    ├── integration-paloalto.md
    ├── integration-sentinel.md
    ├── integration-splunk.md
    └── integration-fortigate.md
```

---

## 📝 File Format

All files follow **plain-text, one IP per line** format:

```
# ============================================================
# Malicious-IP-Threat-List — IP Feed | Part 01
# Author        : Amit Ambekar
# Organization  : Personal Threat Intelligence
# Created       : 2024-01-01
# Updated       : 2026-01-15
# Part          : 01 (max 100,000 per file)
# Count         : 149025
# Source        : Multi-source — AbuseIPDB / FireHOL / OTX / Tor
# Category      : Mixed (C2, Scanner, Malware, Spam, Tor)
# License       : MIT
# Repository    : https://github.com/amitambekar510/Malicious-IP-Threat-List
# Format        : One IPv4 address per line | Lines starting with # are comments
# ============================================================
185.220.101.45
91.108.4.0
194.165.16.11
...
```

- Lines starting with `#` are comments (ignored by all tools)
- IPv4 only (no CIDR, no private ranges)
- No `http://` prefix, no port suffixes

---

## 🤝 Contributing

### Report False Positive
[Open an issue](https://github.com/amitambekar510/Malicious-IP-Threat-List/issues/new?template=false_positive.yml) with:
- IP address
- Reason (CDN, legitimate service, etc.)
- Evidence (VirusTotal link, AbuseIPDB link)

### Submit New Malicious IP
[Open an issue](https://github.com/amitambekar510/Malicious-IP-Threat-List/issues/new?template=ioc_submission.yml) with:
- IP address
- Threat category (C2, Scanner, Malware, Spam, Tor)
- Source/evidence
- Confidence level

### Request Tool Integration
[Open an issue](https://github.com/amitambekar510/Malicious-IP-Threat-List/issues/new?template=integration_request.yml) with:
- Tool/platform name
- Configuration steps
- Example config

---

## 📜 License

MIT License — Free for personal and commercial defensive security use.

```
Copyright (c) 2026 Amit Ambekar

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

---

## ⚠️ Disclaimer

> **IOCs are provided as-is for defensive purposes only.** No warranty of accuracy is made. Users must validate IOCs before enforcement in production environments. Misuse for offensive operations is strictly prohibited.
>
> **Known Limitations:**
> - IPv6 addresses not currently included (planned)
> - Subnet/CIDR notation not supported (single IPs only)
> - Private IP ranges (RFC1918) are automatically excluded
> - Major CDN ranges (Cloudflare, AWS, Azure, Akamai) are filtered

---

## 📞 Contact

| | |
|---|---|
| **Maintainer** | Amit Ambekar |
| **GitHub** | [@amitambekar510](https://github.com/amitambekar510) |
| **LinkedIn** | [amitmilindambekar](https://www.linkedin.com/in/amitmilindambekar/) |
| **Portfolio** | [portfolio.thesafehouse.in](https://portfolio.thesafehouse.in) |
| **Issues** | [GitHub Issues](https://github.com/amitambekar510/Malicious-IP-Threat-List/issues) |
| **Collector** | [threat-intel-collector](https://github.com/amitambekar510/threat-intel-collector) |

---

<div align="center">

**⭐ Star this repo if you find it useful!**

*Defending networks, one indicator at a time.*

</div>