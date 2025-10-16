# Partiel 

#### **What to Focus On**

1.  **Master the Fundamentals: Automata and Regular Expressions**
    *   Don't just memorize definitions. Practice the *process*. Be able to fluidly convert between a language description, a regular expression, and a finite automaton (both NFA and DFA).
    *   The NFA-to-DFA determinization algorithm is a mechanical process. Practice it until it becomes second nature.
    *   Understand *why* some languages are not regular. The key idea is that finite automata have finite memory. They cannot count unboundedly. Be prepared to explain this for languages involving nested parentheses or `a^n b^n`-style structures.

2.  **Deep Dive into Grammars and Ambiguity**
    *   Ambiguity is not a side topic; it's a central theme. You **must** be able to spot it.
    *   **Study the "Dangling Else" Problem:** This is the canonical example of ambiguity. Understand the two possible interpretations (associating the `else` with the inner or outer `if`) and how different languages resolve it (e.g., Python with indentation, Java/C by rule).
    *   Practice creating multiple parse trees from an ambiguous grammar for the same input string. This is the clearest way to demonstrate ambiguity.
