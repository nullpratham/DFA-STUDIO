# Theoretical Specification

## 1. Formal Definition

A Deterministic Finite Automaton (DFA) is a mathematical model represented by a five-tuple:

\[
M = (Q, \Sigma, \delta, q_0, F)
\]

Where:

- **Q:** A finite, non-empty set of states.
- **Σ:** A finite, non-empty input alphabet.
- **δ:** The transition function, defined as \(\delta: Q \times \Sigma \rightarrow Q\).
- **q₀:** The initial state, where \(q_0 \in Q\).
- **F:** The set of accepting states, where \(F \subseteq Q\).

## 2. Properties of DFA

1. A DFA contains a finite set of states.
2. Each state has exactly one transition for every input symbol in the alphabet.
3. Each transition leads to exactly one destination state.
4. The initial state belongs to the set of states.
5. Accepting states are a subset of the state set.
6. All transition symbols must belong to the defined alphabet.

A complete DFA therefore has a defined transition for every pair in \(Q \times \Sigma\).

## 3. Example Automaton

Consider a DFA that accepts all binary strings ending in `1`.

Its components are:

- \(Q = \{q_0, q_1\}\)
- \(\Sigma = \{0, 1\}\)
- Initial state: \(q_0\)
- \(F = \{q_1\}\)

### Transition Table

| Current State | Input 0 | Input 1 |
|---|---|---|
| q₀ | q₀ | q₁ |
| q₁ | q₀ | q₁ |

## 4. Language Recognized

The language recognized by this automaton consists of all binary strings whose last symbol is 1:

\[
L(M) = \{w \in \{0,1\}^* \mid w \text{ ends with } 1\}
\]

## 5. Acceptance Condition

An input string is accepted if, after processing all its symbols, the automaton reaches an accepting state. Otherwise, the input string is rejected.

For the example DFA, the empty string \(\epsilon\) is rejected because the initial state \(q_0\) is not accepting.

## 6. Application in DFA Studio

The theoretical definition will form the basis of the simulator's implementation. The application will represent states, alphabets, transitions, initial states and accepting states as structured data and use the transition function to process input strings.