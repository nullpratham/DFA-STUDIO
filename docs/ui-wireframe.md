# UI Wireframe

## 1. Design Goal

The proposed DFA Studio interface is organized so users can define an automaton, inspect its graph, run an input string and understand the execution result in one workspace.

## 2. Main Interface Regions

1. **Application Header** — identifies DFA Studio and provides actions such as creating a new DFA, loading an example and resetting the workspace.
2. **DFA Configuration Panel** — lets the user manage states, alphabet, initial state, accepting states and transitions.
3. **State Transition Diagram** — displays states and directed, labelled transitions. Initial and accepting states use standard visual distinctions.
4. **Simulation Panel** — accepts an input string and provides validation, run, step, play and reset controls.
5. **Execution Trace** — lists the sequence of input symbols and state changes.
6. **Result Panel** — displays ACCEPTED or REJECTED, or a validation/input error.

## 3. Interaction Flow

The user first defines the DFA in the configuration panel. The application validates the definition and updates the transition diagram and transition table. The user then enters an input string and runs the simulation. During step-by-step execution, the current state and active transition are highlighted, while the execution trace is updated. The final result is displayed after all input symbols have been processed.

## 4. Wireframe

See [ui-wireframe.svg](ui-wireframe.svg) for the low-fidelity interface drawing.

## 5. Design Rationale

The configuration, visualization and simulation areas are visible together to reduce navigation. The execution trace and result are placed below the main workspace so users can connect each transition with the final acceptance decision. This is a low-fidelity design proposal; visual styling and responsive refinements will be addressed during implementation.