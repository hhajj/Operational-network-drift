# Operational Network Drift

Research workbench for studying the relationship between **operational network changes**, **flow telemetry**, and **machine-learning-based intrusion detection under changing network conditions**.

> **Status: Early-stage research / experimental work.**
>
> This repository does not claim a completed IDS framework, a validated causal model, or a novel drift-detection algorithm.

## Research Motivation

Machine-learning-based Network Intrusion Detection Systems (NIDS) are commonly evaluated using fixed datasets or artificially constructed drift scenarios.

Real networks, however, continuously change because of events such as:

* VLAN changes
* routing changes
* firewall policy changes
* application deployments
* infrastructure migrations
* interface changes
* scheduled operational activity

These events can change the observed traffic distribution even when there is no attack.

The central question being investigated is:

> **Can independently recorded operational network events be used to provide context for observed traffic drift and improve the evaluation and interpretation of ML-based NIDS?**

## Current Research Idea

The current experimental direction is:

```text
Operational network event
        │
        ▼
Syslog / configuration evidence
        │
        ▼
Timestamp correlation
        │
        ▼
NetFlow / IPFIX traffic response
        │
        ▼
Observed traffic drift
        │
        ▼
Expected operational response
        │
        ▼
Unexplained / residual behavior
```

The longer-term research direction is to determine whether repeated observations of the same operational event can establish an expected traffic-response profile.

For example:

```text
Known change
     │
     ▼
Expected traffic response
     │
     ├── matches observed behavior
     │
     └── unexplained residual behavior
```

The residual behavior may warrant further security investigation, but this project does **not** assume that unexplained drift is automatically malicious.

## Research Position

The literature reviewed in this project contains substantial work on:

* concept drift detection;
* feature drift;
* continual learning;
* adaptive NIDS;
* zero-day detection;
* active learning;
* synthetic drift generation;
* chronological evaluation.

The current research hypothesis is narrower:

> Existing work appears to study how to detect and adapt to changing traffic, while the operational context producing those changes is less consistently represented as an independently recorded experimental variable.

This is a working research position, **not a claim that no previous work exists**.

The literature review is maintained separately in [`literature/`](literature/).

## Data Sources

The experimental architecture is designed around several evidence channels:

| Source                        | Purpose                                                 |
| ----------------------------- | ------------------------------------------------------- |
| NetFlow/IPFIX                 | Observe the traffic response                            |
| Syslog                        | Record device-reported events                           |
| Configuration snapshots/diffs | Record actual configuration changes                     |
| Manual annotations            | Record operational events not visible through telemetry |

All sources are intended to use a common time reference so that events can be correlated chronologically.

## Current Status

This repository is currently focused on:

* literature analysis;
* research-question development;
* telemetry collection;
* operational event recording;
* data-schema development;
* drift-monitoring experiments;
* chronological experimentation.

It is **not yet** a production IDS and does not claim production-grade detection performance.

## Research Questions

The current questions are exploratory:

1. How do real operational network changes affect flow-level traffic characteristics?
2. Can these changes be reliably associated with independently recorded operational events?
3. Can repeated operational events produce recognizable traffic-response profiles?
4. Can those profiles help distinguish expected operational drift from unexplained drift?
5. Does operational context improve the evaluation or interpretation of ML-based NIDS under temporal change?
6. What operational and computational constraints limit such a methodology in live networks?

These questions may change as experiments and literature review progress.

## Reproducibility

The repository will contain:

* collection scripts;
* schemas;
* sanitized examples;
* experiment definitions;
* analysis scripts;
* configuration examples;
* documented assumptions.

Production data remain outside the repository.

## Important Limitations

This project does not currently claim:

* formal causal inference from timestamps alone;
* that every traffic change is concept drift;
* that unexplained drift is malicious;
* universal applicability across all enterprise networks;
* a new ML architecture;
* a new drift-detection algorithm;
* production-scale validation at arbitrary network speeds.

The objective is to build evidence first and make stronger claims only if experiments justify them.

## Why This Repository Exists

This repository is a public research log and experimental environment.

It is intended to make the development of the research transparent:

**literature → hypothesis → instrumentation → experiment → evidence → revision**

The research direction is expected to evolve as results and literature review provide new evidence.
