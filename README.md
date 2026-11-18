# DFA Studio

**Interactive Deterministic Finite Automata Simulator**

DFA Studio is a proposed browser-based educational application for constructing, visualizing and simulating Deterministic Finite Automata (DFA).

## M1 scope

The M1 submission establishes the problem, theoretical basis, existing-tool review, system design, interface proposal, simulation algorithm and manually solved validation examples. This repository contains the M1 design documentation; it does not claim that the full simulator has already been implemented.

## Proposed technology

- HTML and CSS for structure and presentation
- JavaScript for DFA validation and simulation
- SVG for state-transition diagrams
- Git and GitHub for version control

## Core mathematical model

A DFA is represented by:

`M = (Q, Σ, δ, q0, F)`

The simulator starts at `q0`, processes each input symbol using `δ`, records the execution trace and accepts exactly when the state reached after consuming the entire input belongs to `F`.

## M1 documents

See the `docs/` directory for:
- Problem statement, objectives and scope
- Theoretical specification
- Existing-tools analysis
- System architecture
- Use-case diagram and system flowchart
- UI wireframe
- Simulation algorithm and pseudocode
- Manually solved validation examples

## Project status

M1 design and documentation package. Implementation is planned as a subsequent development phase.
