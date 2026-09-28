# Methodology

## Purpose

Shotgun Test Eval is designed to evaluate whether an AI agent can maintain coherent decision-making when the structure of a task changes over time.

The benchmark does not focus on isolated question answering.

It focuses on sequential decision-making under changing constraints.

## Core idea

An action may be valid in one state of the environment and invalid in another.

The benchmark therefore evaluates whether an agent can detect when:

- constraints have changed;
- authority has changed;
- available resources have changed;
- a local objective conflicts with a higher-level objective;
- previously valid actions are no longer admissible;
- new information changes the meaning of earlier instructions.

## Evaluation model

Each scenario is represented as a sequence of states.

At each step, the agent receives new information and must decide what action to take.

A typical scenario contains:

1. an initial objective;
2. a set of explicit constraints;
3. available resources;
4. one or more authority sources;
5. state changes introduced over time;
6. conflicting or incomplete information;
7. a final outcome that can be evaluated independently of the agent's explanation.

## What is measured

The first version of the benchmark will track:

- task completion;
- system preservation;
- constraint violations;
- unsafe actions;
- recognition of relevant state changes;
- recovery after incorrect assumptions;
- consistency across sequential decisions.

## Failure modes of interest

The benchmark is especially interested in cases where an agent:

- continues following an outdated instruction after the environment changes;
- optimizes a local objective while damaging the overall system;
- follows an instruction outside the authority of its source;
- treats all instructions as equally authoritative;
- fails to distinguish information from permission;
- notices a change but does not propagate it into later decisions;
- produces a plausible explanation for an action that is operationally invalid.

## Design principle

The benchmark should separate:

**reasoning quality**

from

**outcome quality**

A model may produce a convincing explanation and still select an invalid action.

Likewise, an agent may reach an acceptable outcome for the wrong reasons.

Both should be recorded separately.

## Initial implementation

Version 0.1 will use a small synthetic environment with:

- a limited number of resources;
- several competing subsystems;
- explicit operational constraints;
- sequential state changes;
- conflicting objectives.

The environment will be deliberately simple.

Complexity should come from the structure of the decision problem, not from domain-specific knowledge.

## Status

Current stage: **scenario design and scoring specification**
