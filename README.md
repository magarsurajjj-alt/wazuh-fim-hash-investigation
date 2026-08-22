# Wazuh FIM Hash Investigation Dashboard

A File Integrity Monitoring (FIM) dashboard, modeled after the Wazuh security platform, focused on tracking file changes and investigating checksum (hash) history for monitored files.

## Overview

This project simulates a FIM lab environment where files under a monitored directory (`C:\FIM-Lab`) are created, modified, and deleted, and every change is logged as a syscheck-style event — mirroring how a real FIM/SIEM tool records file integrity alerts (rule IDs 550, 553, 554).

## Features

- **Overview page** with severity breakdown and module navigation (Endpoint security, Threat intelligence, Security operations, Cloud security)
- **File Integrity Monitoring module**
  - Event table with timestamp, event type (added/modified/deleted), rule ID, rule level, file path, user, and hash
  - Filter events by type and search by file path
  - Click any event to open a detail drawer with full syscheck metadata and content diff
- **Hash investigation**
  - Paste any MD5/SHA256 checksum into the search box to find which monitored file it belongs to
  - Compare a hash against the recorded baseline for that file (matches vs. deviates)
  - View the full hash history/timeline for a file across all its recorded events
  - One-click copy of hash values
- Additional simulated modules: Configuration assessment, Malware detection, Vulnerability detection, MITRE ATT&CK, Security operations, Cloud security, Agents management, Rules, Settings


## Background: how FIM hash comparison works

File Integrity Monitoring tracks changes to files by computing a cryptographic checksum (MD5, SHA1, or SHA256) at scan time and storing it as a baseline. Any later scan that produces a different checksum for the same file indicates the content has changed, which triggers an alert. This dashboard models that same baseline-comparison logic for a small lab dataset.

## License

This project is provided for educational and demonstration purposes.
