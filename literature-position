# Literature Position

## Purpose

This document records the current position of the research based on the papers reviewed so far.

It is intentionally conservative.

The repository does not claim that a complete systematic literature review has proved the absence of previous work.

## What the Literature Clearly Covers

The reviewed literature contains substantial work on:

* concept drift detection;
* feature drift;
* adaptive IDS;
* continual learning;
* memory replay;
* active learning;
* semi-supervised learning;
* zero-day detection;
* drift simulation;
* chronological evaluation;
* heterogeneous drift;
* operational/infrastructure-related changes.

For example, reviewed literature explicitly identifies infrastructure changes as one source of traffic evolution affecting IDS behavior.

## What Existing Work Often Investigates

A common experimental chain is:

```text
Traffic data
    ↓
Artificial or naturally observed distribution change
    ↓
Drift detection
    ↓
Model adaptation
    ↓
Performance evaluation
```

Other studies investigate:

```text
Drift
    ↓
Select informative samples
    ↓
Obtain labels
    ↓
Adapt IDS
```

## Current Research Direction

The proposed direction adds another information source:

```text
Operational event
       +
Traffic telemetry
       ↓
Temporal correlation
       ↓
Observed traffic response
       ↓
Drift interpretation
```

The research question is therefore not simply:

> "Can we detect drift?"

It is:

> "Can independently recorded operational context help explain and evaluate observed traffic drift?"

## Current Gap Statement

The current evidence supports the following cautious statement:

> **Among the literature reviewed so far, I have not identified a study whose primary experimental methodology is to independently record operational network-change events, synchronize them with flow telemetry, characterize the resulting change-to-drift relationship, and use repeated operational events to construct expected traffic-response profiles.**

This statement is subject to change as the literature review expands.

## Claims That Are Explicitly Avoided

This repository does not currently claim:

> "Nobody has studied operational causes of drift."

It does not claim:

> "This is the first operational concept-drift framework."

It does not claim:

> "Existing IDS research ignores network changes."

It does not claim:

> "All drift caused by operational changes is benign."

## Literature Tracking

Every important claim should eventually be linked to:

* paper;
* section/page;
* exact observation;
* interpretation;
* confidence level.

The literature matrix is maintained in `literature/paper-matrix.csv`.
