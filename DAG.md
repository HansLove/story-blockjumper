A continuación te preparo un **paper conceptual** que puedes usar internamente o incluso publicar como parte del lore técnico de Block Jumper. La idea es que suene como una **especificación del protocolo narrativo**, no solo como una convención de carpetas.

---

# Block Jumper Multiverse Graph Protocol

### Deterministic Narrative Branching Without Metadata

**Author:** Block Jumper Universe
**Version:** Draft v1
**Status:** Proposed Standard

---

# Abstract

Block Jumper introduces a novel narrative navigation system where a story is represented as a **deterministic directed graph** derived entirely from the structure of a filesystem. Unlike traditional branching story systems that rely on explicit metadata or databases to determine relationships between narrative nodes, Block Jumper defines a **naming grammar that encodes lineage directly in the chapter identifier**.

This approach enables:

* deterministic graph reconstruction
* filesystem-native storytelling
* compatibility with AI generation pipelines
* decentralized narrative forks
* multiverse navigation without external state

The protocol defines a naming convention based on **chapter sequence and branch lineage**, enabling the parent of every chapter to be inferred mathematically.

---

# 1. Introduction

Traditional interactive storytelling systems rely on databases or metadata to store relationships between narrative nodes.

However, Block Jumper aims to create a **story multiverse that can be reconstructed entirely from folder structure**, allowing:

* distributed storage
* AI generation pipelines
* Git-based collaboration
* deterministic graph reconstruction

To achieve this, the Block Jumper protocol encodes narrative lineage directly into the **chapter identifier**.

Each chapter folder becomes a **graph node**, and the naming grammar defines how nodes connect.

---

# 2. Core Concept: Story as a Directed Graph

The Block Jumper universe is modeled as a **directed acyclic graph (DAG)** where:

| Concept | Meaning                    |
| ------- | -------------------------- |
| Node    | A chapter                  |
| Edge    | Narrative continuation     |
| Branch  | Alternate universe         |
| Path    | Timeline through the story |

Example:

```
1 → 2 → 3 → 4 → 5
          ↘
           3-A → 4-A → 5-A
                     ↘
                      5-A-B → 6-A-B
```

This structure allows the story to evolve as a **multiverse of narrative possibilities**.

---

# 3. Chapter Identifier Grammar

Each chapter folder must follow the grammar:

```
<sequence>-<branch-path>
```

Where:

| Component   | Description                |
| ----------- | -------------------------- |
| sequence    | chapter number             |
| branch-path | lineage of narrative forks |

Examples:

```
1
2
3
3-A
4
4-A
4-A-B
5
5-A
5-A-B
6-A-B
```

---

# 4. Branch Lineage Encoding

The branch path represents **the lineage of narrative forks**.

Examples:

| Chapter | Meaning                       |
| ------- | ----------------------------- |
| 3       | main storyline                |
| 3-A     | first fork from main timeline |
| 4-A     | continuation of branch A      |
| 4-A-B   | new fork born within branch A |
| 5-A-B   | continuation of branch AB     |

This structure creates a **hierarchical universe tree**.

---

# 5. Deterministic Parent Inference

The key property of the Block Jumper protocol is that **parent nodes can be inferred deterministically**.

The parent inference algorithm follows these rules.

---

## Rule 1 — Same Branch Continuation

If a chapter exists with the same branch path at the previous sequence:

```
parent = (sequence - 1, same branch path)
```

Example:

```
5-A-B → parent = 4-A-B
```

---

## Rule 2 — Branch Birth

If the branch path does not exist at the previous sequence, then the node represents the **birth of a new sub-branch**.

The parent becomes the previous chapter of the parent branch.

Example:

```
4-A-B
```

Search for:

```
3-A-B
```

Not found.

Then search for:

```
3-A
```

Therefore:

```
parent(4-A-B) = 3-A
```

---

## Rule 3 — Main Chain

If no branch path exists:

```
parent = sequence - 1
```

Example:

```
4 → parent = 3
```

---

# 6. Example Multiverse Graph

Filesystem structure:

```
1/
2/
3/
3-A/
4/
4-A/
4-A-B/
5/
5-A/
5-A-B/
6-A-B/
```

Derived graph:

```
1 → 2 → 3 → 4 → 5
          ↓
          3-A → 4-A → 5-A
                ↓
                4-A-B → 5-A-B → 6-A-B
```

---

# 7. Graph Layout Rules

For visual navigation, the graph follows deterministic spatial rules.

### Horizontal axis

Represents chapter sequence.

```
X = sequence
```

### Vertical axis

Represents branch lineage.

Each branch path occupies a **dedicated lane**.

Example:

| Lane | Branch |
| ---- | ------ |
| 0    | main   |
| 1    | A      |
| 2    | A-B    |
| 3    | B      |

Thus:

```
4-A   → lane A
5-A   → lane A
4-A-B → lane A-B
5-A-B → lane A-B
```

This keeps branches visually stable across the graph.

---

# 8. Multiverse Navigation

The navigation system supports the following interactions.

### Node Selection

Clicking a node highlights the entire narrative path from the genesis chapter.

Example:

Clicking `5-A-B` highlights:

```
1 → 2 → 3 → 3-A → 4-A-B → 5-A-B
```

### Branch Exploration

Users can visually explore alternate timelines as branching paths.

---

# 9. Compatibility With AI Story Generation

The protocol was designed to support **AI generated universes**.

AI systems can generate new chapters by simply creating folders following the naming grammar.

Example:

```
7-A-B
7-A-B-C
8-A-B-C
```

The system will automatically reconstruct the narrative graph.

No additional metadata is required.

---

# 10. Relationship to Proof of Work Lore

In the Block Jumper universe, computational power determines narrative evolution.

Transformations, abilities, and multiverse expansions are tied to **Proof of Work processes**, mirroring Bitcoin mining.

Forks in the narrative represent **parallel computational universes**.

This makes the multiverse not only a storytelling device but also a **computationally grounded mythos**.

---

# 11. Advantages of the Protocol

### Deterministic

Graphs can be reconstructed without databases.

### Decentralized

Stories can be distributed as filesystem structures.

### AI Friendly

AI agents can generate forks without needing schema knowledge.

### Git Compatible

Branching stories integrate naturally with version control.

### Scalable

The universe can grow indefinitely without structural ambiguity.

---

# 12. Future Extensions

Possible protocol extensions include:

* power level encoding
* universe difficulty metrics
* proof-of-work story gates
* AI generated forks
* community funded timelines

---

# Conclusion

The Block Jumper Multiverse Graph Protocol introduces a deterministic method for encoding narrative graphs directly into filesystem structures.

By embedding lineage in chapter identifiers, the protocol enables:

* decentralized storytelling
* infinite multiverse expansion
* deterministic graph navigation

without requiring metadata or centralized databases.

This makes Block Jumper not just a story, but a **computational storytelling system**.

---

Si quieres, en el siguiente paso puedo ayudarte a escribir también:

1. **el algoritmo exacto para generar el grafo en JavaScript**
2. **el parser de carpetas**
3. **el layout del multiverse map**
4. **el motor para resaltar rutas al hacer click**

y dejar listo el **Block Jumper Graph Engine**.
