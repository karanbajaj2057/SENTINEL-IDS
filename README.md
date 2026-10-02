# SENTINEL IDS

### Network Intrusion Detection System — Synthetic Simulation

SENTINEL IDS is a browser-based cybersecurity simulation for monitoring synthetic network flows, identifying potentially malicious behavior, generating security alerts, and supporting basic SOC-style investigation.

> **Safety & scope:** This project is designed for defensive simulation and education. It uses synthetic flow records and documentation IP ranges. It does not generate or capture real network traffic.

## Live Demo

**[Launch SENTINEL IDS](https://networkintrusiondetectionsystemidssimulation.lovable.app/)**

## Highlights

- Real-time-style synthetic network traffic monitoring
- Mixed-traffic simulation mode for normal and suspicious flows
- Signature-based detection
- Statistical anomaly detection using z-score logic
- Severity-based alert visualization
- Potential-intrusion classification
- SOC investigation workflow
- Incident-report view
- Synthetic live-flow records
- Export of a 5,000-flow CSV dataset
- Safe use of documentation IP ranges for simulation

## Detection Overview

SENTINEL IDS exposes two active detection engines:

1. **Signature detection** — identifies traffic patterns matching configured suspicious signatures.
2. **Anomaly detection** — evaluates deviations from a learned traffic baseline using z-score style statistical analysis.

The public interface describes the system as using **signature + anomaly (z-score)** detection and classifies relevant events as **POTENTIAL_INTRUSION**.

## Core Workflow

```text
Synthetic Network Flows
          │
          ▼
   Traffic Simulation
          │
          ▼
 ┌─────────────────────┐
 │ Detection Layer     │
 │                     │
 │  • Signatures       │
 │  • Anomaly / Z-score│
 └──────────┬──────────┘
            │
            ▼
     Alert Generation
            │
            ▼
   Severity / Incident
        Analysis
            │
            ▼
      SOC Investigation
            │
            ▼
      Incident Report
            │
            ▼
       CSV Export
```

## Example Data Fields

The live simulation exposes synthetic flow records with fields such as:

| Field | Description |
|---|---|
| Time | Flow/event timestamp |
| Source | Synthetic source IP |
| Destination | Synthetic destination IP |
| Proto | Network protocol |
| Packets | Packet count |
| Bytes | Byte volume |
| Conns | Connection count |
| Failed | Failed connection count |
| Scenario | Simulated traffic scenario |

## Repository Structure

```text
sentinel-ids/
├── public/                 # Static assets exported from the application
├── src/                    # Application source code
├── components/             # Reusable UI components, if present in exported source
├── docs/
│   └── architecture.md    # Project architecture and design notes
├── scripts/
│   └── push-to-github.sh  # Git initialization / push helper
├── .gitignore
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
├── SECURITY.md
└── CITATION.cff
```

> **Important:** Populate `src/`, `public/`, and related folders with the actual source exported from your project platform. Do not upload secrets, API keys, private credentials, or environment files.

## Getting the Source Code into GitHub

Export/download the project source from your app builder, place the files in this repository, then run:

```bash
git init
git add .
git commit -m "feat: initial release of Sentinel IDS"
git branch -M main
git remote add origin https://github.com/karanbajaj2057/sentinel-ids.git
git push -u origin main
```


## Recommended GitHub Repository Description

```text
SENTINEL IDS — a defensive network intrusion detection simulation with synthetic traffic, signature-based detection, z-score anomaly detection, SOC investigation, alerting, and incident reporting.
```

## Suggested GitHub Topics

```text
cybersecurity
intrusion-detection
ids
network-security
soc
threat-detection
anomaly-detection
security-monitoring
cyber-defense
simulation
```

## Screenshots

```text
docs/
└── screenshots/
    ├── dashboard.png
    ├── alerts.png
    ├── soc-investigation.png
    └── incident-report.png
```

Example Markdown:

```markdown
![SENTINEL IDS Dashboard](docs/screenshots/dashboard.png)
```

## Security Notice

This is a simulation/educational project. It should not be represented as a production IDS without validating the underlying detection logic, data pipeline, false-positive behavior, performance, and security controls in a controlled environment.

For security concerns, see [SECURITY.md](SECURITY.md).

## Roadmap

Potential future improvements include:

- Additional network attack scenarios
- More configurable detection signatures
- Model-backed anomaly detection
- Historical event analytics
- Detection-rule management
- User authentication and role-based access
- Persistent alert storage
- Automated report generation
- Benchmarking with recognized IDS datasets
- Precision, recall, F1-score, and false-positive analysis
- Containerized deployment
- Automated tests and CI/CD

## Disclaimer

SENTINEL IDS is provided for cybersecurity education, defensive experimentation, and controlled simulation. Any future integration with live traffic should be performed only in environments where you have authorization to monitor and analyze the network.

## License

This project is released under the MIT License. See [LICENSE](LICENSE).


