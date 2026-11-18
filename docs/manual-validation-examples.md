# Manually Solved Validation Examples

## 1. DFA Under Test

Consider the DFA that accepts all binary strings ending in `1`.

- `Q = {q0, q1}`
- `Σ = {0, 1}`
- Initial state: `q0`
- Accepting states: `F = {q1}`

| Current state | Input 0 | Input 1 |
|---|---|---|
| q0 | q0 | q1 |
| q1 | q0 | q1 |

## 2. Example A — Accepted Input: `1011`

| Step | Read symbol | Current state before | State after |
|---:|---|---|---|
| 0 | — | — | q0 (initial) |
| 1 | 1 | q0 | q1 |
| 2 | 0 | q1 | q0 |
| 3 | 1 | q0 | q1 |
| 4 | 1 | q1 | q1 |

The complete input has been consumed and the automaton finishes in `q1`. Since `q1` belongs to the accepting-state set, the string is **ACCEPTED**.

## 3. Example B — Rejected Input: `100`

| Step | Read symbol | Current state before | State after |
|---:|---|---|---|
| 0 | — | — | q0 (initial) |
| 1 | 1 | q0 | q1 |
| 2 | 0 | q1 | q0 |
| 3 | 0 | q0 | q0 |

The complete input has been consumed and the automaton finishes in `q0`. Since `q0` is not an accepting state, the string is **REJECTED**.

## 4. Example C — Empty Input: `ε`

No input symbols are consumed. The automaton remains in its initial state `q0`. Since `q0` is not accepting, the empty string is **REJECTED**.

## 5. Example D — Invalid Input: `102`

The symbol `2` does not belong to the alphabet `{0, 1}`. The input is therefore reported as **INVALID INPUT**; it is not treated as a valid DFA execution.

## 6. Expected Test Summary

| Input | Expected outcome | Reason |
|---|---|---|
| `1011` | ACCEPTED | Ends in accepting state q1 |
| `100` | REJECTED | Ends in non-accepting state q0 |
| `ε` | REJECTED | Initial state q0 is non-accepting |
| `1` | ACCEPTED | Ends in accepting state q1 |
| `102` | INVALID INPUT | Symbol 2 is outside the alphabet |

These examples provide hand-worked cases against which the implementation can later be tested.