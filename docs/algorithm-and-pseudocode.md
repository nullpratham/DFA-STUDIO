# DFA Simulation Algorithm and Pseudocode

## 1. Objective

The simulation algorithm determines whether an input string is accepted by a valid deterministic finite automaton.

## 2. Inputs and Output

**Inputs**
- A valid DFA represented by `Q`, `Σ`, `δ`, `q0` and `F`.
- An input string `w`.

**Output**
- `ACCEPTED` if the state reached after consuming the entire string belongs to `F`.
- `REJECTED` otherwise.

Invalid DFA definitions and input symbols outside the alphabet are reported as validation errors before simulation.

## 3. Pseudocode

```text
DFA_SIMULATE(Q, Σ, δ, q0, F, w)

1. current_state ← q0
2. trace ← [current_state]

3. FOR each symbol a in w:
       IF a is not in Σ:
           RETURN INVALID_INPUT

       current_state ← δ(current_state, a)
       append current_state to trace

4. IF current_state is in F:
       result ← ACCEPTED
   ELSE:
       result ← REJECTED

5. RETURN result, trace
```

## 4. Explanation

The algorithm begins at the DFA's initial state. It reads the input string from left to right. For each symbol, it applies the transition function to the current state and that symbol, then records the resulting state. Once all symbols have been consumed, it checks whether the current state belongs to the accepting-state set.

The empty string is handled naturally: the loop executes zero times, so the final state remains the initial state. The empty string is accepted exactly when the initial state is an accepting state.

## 5. Complexity Analysis

Let `n` be the length of the input string.

- **Time complexity:** `O(n)` when transitions are stored in a lookup structure with constant-time average access.
- **Auxiliary space:** `O(n)` if the complete execution trace is retained; `O(1)` additional space if only the current state and result are retained.

The trace is retained in DFA Studio because step-by-step explanation is a core educational feature.

## 6. Validation Before Simulation

The DFA validator checks that the state set and alphabet are non-empty, the initial state belongs to the state set, accepting states and transition endpoints are valid, and exactly one transition exists for each state-symbol pair. Simulation is enabled only after these checks pass.