# Research Problem

## Problem Statement

A machine-learning-based IDS learns relationships from historical network traffic.

When the network changes, the traffic observed by the IDS may also change.

Examples include:

* introducing a new VLAN;
* changing routing;
* modifying firewall policy;
* deploying a new application;
* migrating services;
* changing network interfaces;
* changing traffic paths.

The resulting traffic change does not necessarily represent a security event.

Therefore:

```text
Traffic changed
        ≠
Attack occurred
```

and:

```text
Traffic changed
        ≠
IDS must immediately retrain
```

The research problem is to understand how operational network changes affect observed traffic and the behavior of ML-based NIDS.

## Operational View

The project separates four observations:

### 1. Operational event

Something changed in the network.

### 2. Traffic response

The change produced a measurable effect in NetFlow/IPFIX.

### 3. Drift

The observed traffic differs from the previously established traffic behavior.

### 4. Security interpretation

The traffic response must be assessed to determine whether it is consistent with the operational event or contains unexplained behavior.

## Working Model

```text
Network state
     │
     ├── operational change
     │
     ▼
New network behavior
     │
     ▼
Flow telemetry changes
     │
     ▼
Drift detector observes change
     │
     ├── operationally explained
     │
     └── unexplained
```

The project investigates whether the operational event can provide useful context for the final interpretation.

## Important Distinction

This project distinguishes:

### Feature / traffic drift

The observed traffic characteristics change.

Example:

* flow volume changes;
* source/destination distribution changes;
* port distribution changes;
* interface usage changes;
* connection duration changes.

### Security-related concept drift

The relationship between observed traffic behavior and security classification changes.

An operational network change may create traffic drift without creating security concept drift.

This distinction is therefore part of the experimental design.

## Research Position

The current position is that concept-drift research already provides extensive methods for detecting and adapting to changing data.

The proposed work investigates the additional operational dimension:

> **What independently recorded network event corresponds to the observed traffic change?**

This is a research hypothesis to be tested, not a conclusion.
