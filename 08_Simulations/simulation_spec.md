# Simulation Specification

## Purpose

Evaluate the resilience of the Shield-Knot Lattice under dynamic load,
stochastic failures, and adaptive rerouting.

---

## Simulation Objectives

- Measure routing efficiency
- Measure failure propagation
- Measure recovery capability
- Compare against baseline topologies

---

## Network Models

- Linear Chain
- Square Grid
- Random Graph
- Shield-Knot Lattice

---

## Time Model

Discrete timestep simulation

t = 0 ... N

Each timestep executes:

1. Inject load
2. Route traffic
3. Evaluate failures
4. Remove failed edges
5. Recalculate routes
6. Collect metrics
7. Advance timestep

---

## Experimental Variables

Independent Variables

- Input Load
- Arrival Rate λ
- Failure Threshold θ
- Sigmoid Steepness k
- Braided Coefficient λ_b

Dependent Variables

- BER
- Connectivity Ratio
- Cascade Depth
- Recovery Time
