# Skill: Research Paper → Toy Implementation

This skill transforms academic research papers into executable,
pedagogical Jupyter notebooks.

The goal is to help learners understand papers by building them.

## Core Principle

The algorithm does not know it is a toy.

We preserve:
- Interfaces
- Control flow
- Decision logic

We simplify:
- Models
- Data
- Scale
- Compute

## Philosophy

| Paper | Toy Implementation |
|------|-------------------|
| Large models | Mock or tiny models |
| Real datasets | Synthetic datasets |
| Performance focus | Transparency focus |
| Proofs | Step-by-step execution |
| GPUs | CPU only |

## Design Rules

- Every algorithm is a pure function
- Heavy components are dependency-injected
- Verbose execution is mandatory
- Intermediate states must be visible
- Qualitative trends must match the paper

## Valid Simplifications

- Rule-based reward models
- Random or heuristic generators
- Synthetic datasets under 100 samples
- Approximate scoring functions

## Invalid Simplifications

- Removing the paper’s core loop
- Collapsing multi-step algorithms into one step
- Hiding decisions inside black boxes