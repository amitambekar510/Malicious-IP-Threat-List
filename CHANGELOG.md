# Changelog — Malicious IP Threat Intelligence Feed

All notable changes to this threat intelligence feed are documented here.

## [2026-01-15] — Automated Pipeline Launch

### Added
- Automated 12-hour collection pipeline via GitHub Actions
- Multi-source collection: AbuseIPDB, FireHOL (L1-L4), Tor Project, AlienVault OTX
- Validation against VirusTotal (≥3 detections), AbuseIPDB (≥25% confidence)
- Multi-layer deduplication: Bloom filter + Git history scan
- GPG-signed commits for supply chain integrity
- Partition file management (100K IPs per file)

### Changed
- Migrated from manual updates to fully automated collection
- Increased update frequency from weekly to every 12 hours
- Standardized file format with detailed headers

### Statistics
| Feed | Before | Added | After |
|------|--------|-------|-------|
| Total IPs | 146,000 | 3,000+ | 149,000+ |
| Partitions | 2 | 0 | 2 |

---

## [2025-12-01] — Major Feed Expansion

### Added
- FireHOL Level 1-4 blocklists integration
- Tor exit node feed
- AlienVault OTX pulse integration
- AbuseIPDB high-confidence feed

### Statistics
| Feed | Before | Added | After |
|------|--------|-------|-------|
| Total IPs | 45,000 | 101,000 | 146,000 |

---

## [2025-06-15] — Initial Release

### Added
- Initial malicious IP feed with 45,000 IPs
- Basic GitHub repository structure
- RAW feed URLs for direct tool integration
- Documentation for Palo Alto, Splunk, Sentinel integrations

---

## Changelog Format

Each entry follows:
```
## [YYYY-MM-DD] — Brief Description

### Added / Changed / Removed / Fixed
- Details

### Statistics
| Feed | Before | Added | Removed | After |
|------|--------|-------|---------|-------|
| IPs  | 0      | +X    | -Y      | Z     |
```