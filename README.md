# I-Ching State Engine

An implementation of the Shield Braided Matrix (SBM) research framework.

This repository is a simulation core that transforms an I Ching hexagram into
a deterministic network simulation. Rather than acting only as an oracle, it
serves as an experimental engine for studying network resilience under
controlled fault conditions.

## Overview

The project maps symbolic I Ching state into reproducible network experiments.
Its architecture is organized around independent components responsible for:

- deriving simulation parameters from a hexagram reading
- building network topologies
- injecting moving-line faults before execution
- routing packets through the network
- calculating BER (Braid Effectiveness Ratio)
- orchestrating complete trials and Monte Carlo experiments

## Network Models

The engine is designed around three progressively more resilient topologies:

- **Linear** – a simple chain of six nodes
- **Grid** – a 2×3 rectangular network
- **Shield-Knot** – a braided topology with redundant pathways inspired by
  Celtic shield-knot geometry

The Shield-Knot architecture is intended to demonstrate improved fault
tolerance through multiple alternative routing paths.

## I Ching Integration

The oracle directly controls simulation behavior. Each hexagram determines:

- network topology
- traffic load (λ)
- injected fault locations
- deterministic random seed
- upper and lower trigrams

Moving lines (6 and 9) become pre-existing network faults before packet
routing begins.

## Simulation Process

For each trial, the engine:

1. builds the network
2. injects faults
3. routes packets between random nodes
4. tracks overloaded links
5. detects cascading failures
6. computes resilience metrics
7. returns a structured result object

## Metrics Collected

Each trial records:

- successful packet routes
- failed edges
- cascade depth
- network connectivity
- BER (Braid Effectiveness Ratio)

BER compares observed connectivity against a linear baseline and can emphasize
the redundant routing capacity of the Shield-Knot topology.

## Statistical Features

The framework is intended to support repeatable experiments through:

- deterministic random seeds for reproducibility
- Monte Carlo execution across many trials
- 95% confidence interval calculations for BER and related metrics

## Strengths

Key design qualities of the repository include:

- clear separation of responsibilities
- structured data modeling
- deterministic execution
- extensibility for additional network topologies and metrics
- a research-oriented architecture suitable for controlled experimentation

## Research Direction

This project has evolved beyond an I Ching simulator into a research framework
for mapping symbolic states into reproducible network experiments. A natural
next step is increasing the realism of the networking model with more advanced
routing and failure propagation while preserving the existing modular
architecture.

## Current Repository Contents

The current repository primarily contains simulation planning and specification
materials under `/08_Simulations`, including:

- `simulation_spec.md`
- `experiment_plan.md`
- `metrics.md`
- `scenarios.yaml`
- `run_experiment.py`
