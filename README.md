# Shotgun Test Eval

Adversarial evaluation of AI reasoning under conflicting objectives, contextual shifts, and constrained environments.

## What this is

Shotgun Test Eval is an experimental benchmark for testing whether AI agents can preserve valid reasoning when the environment changes around them.

The benchmark focuses on failure modes such as:

- conflicting local and global objectives;
- changing constraints and permissions;
- partial or asymmetric information;
- resource scarcity;
- authority and scope mismatches;
- context updates that invalidate previously acceptable actions;
- locally rational decisions that produce globally unacceptable outcomes.

The goal is not to test whether a model can answer isolated questions correctly.

The goal is to test whether an agent can continue to act coherently when the structure of the problem itself changes.

## Current status

**v0.1 — design stage**

The first version will use a small controlled environment with explicit resources, systems, constraints, and sequential state changes.

Planned baseline evaluation dimensions:

- survival / system preservation;
- primary task completion;
- constraint violations;
- unsafe actions;
- context updates detected;
- recovery after state changes.

## Planned structure

```text
shotgun-test-eval/
├── README.md
├── methodology.md
├── scenarios/
├── results/
└── docs/
