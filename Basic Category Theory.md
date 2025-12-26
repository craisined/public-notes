#Math #CT

# Categories

Categories contain:

- A collection of **objects**
- A collection of **morphisms** (also called **arrows**) connecting objects denoted by $f: S \to T$, where $f$ is the **morphism**, $S$ is the **source**, and $T$ is the **target**
    - Note: $f: A \to B$ and $g: A \to B$ **DOES NOT IMPLY** $f = g$
    - Formally this can also be expressed as a relation between a collection of objects and a collection of morphisms
    - Morphisms have a notion of **composition**, that being if $f: A \to B$, $g: B \to C$, then $g \circ f: A \to C$

There are three rules for categories:

- **Associativity:** For morphisms $a$, $b$, and $c$, $(a \circ b) \circ c = a \circ (b \circ c)$
- **Closed composition:** If for morphisms $a$ and $b$,  $a \circ b$ exists, then there must be morphism $c = a \circ b$
- **Identity morphisms:** For every object $A$ in a category, there must be an identity morphism $\text{id}_A: A \to A$