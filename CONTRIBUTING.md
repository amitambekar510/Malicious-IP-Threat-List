# Contributing to Malicious IP Threat Intelligence Feed

Thank you for contributing! This feed is maintained by the community and automated pipelines.

## Ways to Contribute

### 1. Report False Positives
Use the [False Positive Report template](.github/ISSUE_TEMPLATE/false_positive.yml).

### 2. Submit New Malicious IPs
Use the [IOC Submission template](.github/ISSUE_TEMPLATE/ioc_submission.yml).

### 3. Improve Documentation
Submit PRs for integration guides, README improvements, etc.

### 4. Request Tool Integrations
Use the [Integration Request template](.github/ISSUE_TEMPLATE/integration_request.yml).

## IOC Format Requirements

### IP Addresses
- **Valid**: `185.220.101.45` (IPv4 only)
- **Invalid**: 
  - `http://185.220.101.45` (no protocol)
  - `185.220.101.45:8080` (no port)
  - `10.0.0.1` (no private/RFC1918 ranges)
  - `185.220.101.0/24` (no CIDR/subnets)

### Validation Checklist
Before submitting, verify:
- [ ] Not a private IP range (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16)
- [ ] Not a major CDN/cloud range (Cloudflare, AWS, Azure, Akamai, Fastly, Google Cloud)
- [ ] Verified on VirusTotal (≥3 vendor detections)
- [ ] Checked on AbuseIPDB (confidence ≥25%)
- [ ] Checked on Cisco Talos (if available)

## Automated Pipeline

This feed is updated **every 12 hours** via GitHub Actions:
1. Collection from 7+ sources (async)
2. Validation against VT, AbuseIPDB, Talos
3. Deduplication (Bloom filter + Git history)
4. Top 25 new IPs selected per cycle
5. Appended to partition files
6. GPG-signed commit & push

## Partition Management

- Part 1: 1-100,000 IPs → `Malicious-IP-Threat-List.txt`
- Part 2: 100,001-200,000 IPs → `Malicious-IP-Threat-List_aa`
- Part 3+: Auto-created as needed

## License

By contributing, you agree your submissions are licensed under MIT License.

## Questions?

Open a [Discussion](https://github.com/amitambekar510/Malicious-IP-Threat-List/discussions) or [Issue](https://github.com/amitambekar510/Malicious-IP-Threat-List/issues).