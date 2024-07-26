# Visual_dfa_minimization

This project provides a solution for minimizing Deterministic Finite Automata (DFA). The tool accepts a DFA, performs minimization to eliminate redundant states, and outputs the minimized DFA along with its graphical representation. The core functionality includes:

- Constructing a DFA based on user input or predefined data.
- Minimizing the DFA to reduce the number of states while preserving its language.
- Visualizing both the original and minimized DFA using Graphviz.
- Displaying DFA details in a readable format.

## Features

- **DFA Construction**: Allows the user to define states, transitions, and final states.
- **DFA Minimization**: Applies state minimization algorithms to reduce the number of states.
- **Graphical Visualization**: Uses Graphviz to render graphical representations of both the original and minimized DFA.
- **Readable Output**: Prints DFA details, including states, transitions, initial state, and accepting states.

## Technologies Used

- **Programming Language**: Python
- **Libraries**: NumPy, Matplotlib, NetworkX, Graphviz, Tabulate

## Usage

1. **Input DFA**: Define states, transitions, initial state, and accepting states. 

2. **Minimize DFA**: The script performs minimization to simplify the DFA by merging equivalent states.

3. **Visualize DFA**: Generates graphical representations of both the original and minimized DFA.

4. **Print DFA Details**: Outputs DFA details for both the original and minimized versions.


The program will generate and save graphical representations of the DFA before and after minimization as `old_dfa.png` and `new_dfa.png`, respectively. The details of both the original and minimized DFA will be printed to the console.

## Code Description

- **`minimize_dfa`**: Function to minimize the DFA by merging equivalent states.
- **`visualize_dfa`**: Function to create graphical representations of the DFA using Graphviz.
- **`print_dfa`**: Function to print DFA details in a human-readable format.

## Example Output

**Original DFA:**

```
States: {'0', '1', '2', '3', '4', '5', '6', '7', '8', '9'}
Alphabet: {'0', '1'}
Transitions:
0 -> {'0': '1', '1': '9'}
1 -> {'0': '8', '1': '2'}
2 -> {'0': '3', '1': '2'}
3 -> {'0': '2', '1': '4'}
4 -> {'0': '5', '1': '8'}
5 -> {'0': '4', '1': '5'}
6 -> {'0': '7', '1': '5'}
7 -> {'0': '6', '1': '5'}
8 -> {'0': '1', '1': '3'}
9 -> {'0': '7', '1': '8'}
Initial State: 0
Accepting States: {'3', '4', '8', '9'}
```

**Minimized DFA:**

```
States: {'0', '9', '67', '348', '512'}
Alphabet: {'0', '1'}
Transitions:
0 -> {'0': '512', '1': '9'}
9 -> {'0': '67', '1': '348'}
67 -> {'0': '67', '1': '512'}
348 -> {'0': '512', '1': '348'}
512 -> {'0': '348', '1': '512'}
Initial State: 0
Accepting States: {'9', '348'}
```

## Limitations

- The minimization algorithm assumes that the input DFA is complete and deterministic.
- The graphical visualization may not handle very large DFAs efficiently.

