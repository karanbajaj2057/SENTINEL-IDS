# SENTINEL IDS — Architecture

## Purpose

SENTINEL IDS is structured as a defensive simulation pipeline rather than a live packet-capture system.

## Logical Components

### 1. Traffic Simulation

Generates synthetic network-flow records representing normal and suspicious activity.

### 2. Detection Engines

The public application currently exposes two detection approaches:

- **Signature-based detection**
- **Statistical anomaly detection using z-score logic**

### 3. Alert Pipeline

Detected events are transformed into alert records and associated with a severity level.

### 4. SOC Investigation

Analysts can select an alert from the feed and inspect the associated event context.

### 5. Incident Reporting

The interface provides an incident-report view for reviewing detected security events.

### 6. Data Export

The application exposes an export function for a synthetic 5,000-flow CSV dataset.

## High-Level Diagram

```text
              ┌───────────────────────┐
              │ Synthetic Flow Source │
              └───────────┬───────────┘
                          │
                          ▼
              ┌───────────────────────┐
              │ Traffic Simulation    │
              └───────────┬───────────┘
                          │
                ┌─────────┴─────────┐
                ▼                   ▼
      ┌──────────────────┐  ┌──────────────────┐
      │ Signature Engine │  │ Anomaly Engine   │
      │                  │  │ Z-score baseline │
      └─────────┬────────┘  └─────────┬────────┘
                └──────────┬──────────┘
                           ▼
                  ┌──────────────────┐
                  │ Alert Generation │
                  └────────┬─────────┘
                           ▼
             ┌──────────────────────────┐
             │ Severity / Classification│
             └────────────┬─────────────┘
                          ▼
              ┌────────────────────────┐
              │ SOC Investigation      │
              └────────────┬───────────┘
                           ▼
              ┌────────────────────────┐
              │ Incident Report / CSV  │
              └────────────────────────┘
```

## Important Boundary

The public interface explicitly identifies the records as synthetic and states that no real network traffic is generated or captured. Keep that distinction clear in documentation and demonstrations.
