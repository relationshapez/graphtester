# Graph Tester

Graph Tester is a single-file HTML tool that combines three classroom practice activities related to the Handshaking Formula into one mobile-friendly app.

The combined interface includes three tabs:

- **Existence** — the graph existence tester
- **Valence** — the graph valence solver
- **Grouping** — the graph team grouping challenge

To run remotely:

- Access the tool at https://relationshapez.github.io/graphtester/

## Files

- `index.html` — combined single-file HTML tool
- `README.md` — combined documentation for the HTML tool
- `LICENSE` — MIT License text

## Tab 1: Existence

It presents students with short yes/no questions about whether a connected graph can exist under a given set of valence conditions. After answering, students receive immediate feedback and can reveal a short explanation.

### Purpose

This tool is intended for classroom practice and independent review. It helps students build fluency with the core existence rules for connected undirected graphs when:

- repeated edges are allowed,
- self-loops are allowed,
- self-loops count as 2 toward valence,
- and connectedness is required.

Rather than asking students to construct a graph explicitly, the tool asks whether such a graph **can exist**. This encourages students to reason from patterns, parity, and the structure of the Handshaking Formula.

### Graph Model Used

All questions in this tool assume:

- graphs are **undirected**,
- graphs must be **connected**,
- **repeated edges are allowed**,
- **self-loops are allowed**,
- a self-loop contributes **2** to the valence,
- every vertex must have valence at least **1**,
- and the graph must have at least **2 vertices**.

This means the tool is **not** restricted to simple graphs.

### Master Rule

A connected graph can exist exactly when all of the following hold:

1. every valence is at least 1,
2. the total valence is even,
3. the total valence is at least
   \
   2(n-1)
   \
   where \(n\) is the number of vertices.

A useful parity fact is:

- the number of odd-valence vertices must be even.

### Student Checklist

When deciding whether the answer is **Yes** or **No**, students can check the following:

1. Are all valences at least 1?
2. Is the total valence even?
3. Is the total valence large enough for connectedness?
4. Is the number of odd-valence vertices even?

If all required conditions pass, the answer is **Yes**.  
If any required condition fails, the answer is **No**.

### Interface

The **Existence** tab includes four buttons:

- **Yes**
- **No**
- **Why?**
- **Refresh**

Behavior:

- After the student answers, that single feedback box displays **Correct** or **Incorrect**.
- The selected answer button is prominently outlined.
- The outline is **green** when the answer is correct.
- The outline is **red** when the answer is incorrect.
- The **Why?** button stays disabled until an answer is chosen.
- Pressing **Why?** adds the explanation into that same feedback box below the initial result text.
- Pressing **Refresh** generates a new question and clears the prior feedback.

### Question Types

The **Existence** tab includes the following question families.

#### 1. All vertices have the same valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if all vertices have the same valence?”

**Answer rule:**
Yes.

**Reasoning:**
Any positive even common valence works for any number of vertices. A positive odd common valence works when the number of vertices is even, because then the total valence is even.

#### 2. Every vertex has valence \(x\)
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if every vertex has valence \(x\)?”

**Answer rule:**
Yes exactly when \(nx\) is even.

**Reasoning:**
The total valence is \(nx\). Since every valence is already positive in these prompts, the main issue is whether the total is even.

#### 3. All vertex valences are different
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if all vertex valences are different?”

**Answer rule:**
Yes.

**Reasoning:**
The exact valences are not fixed. It is enough that some distinct positive valences can be chosen so the total is even and large enough.

#### 4. Valences are \(1,2,\dots,n\)
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if the valences are 1, 2, ..., \(n\)?”

**Answer rule:**
Yes exactly when
\[
1+2+\cdots+n
\]
is even.

**Reasoning:**
The valence list is fixed, so the decision comes down to whether that total is even.

#### 5. Every vertex has even valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if every vertex has even valence?”

**Answer rule:**
Yes.

**Reasoning:**
Positive even valences automatically give an even total. There are connected choices that satisfy the rule.

#### 6. Every vertex has odd valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if every vertex has odd valence?”

**Answer rule:**
Yes exactly when the number of vertices is even.

**Reasoning:**
A total made from odd valences is even only when there are an even number of odd terms.

#### 7. Every valence is a multiple of \(x\)
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if every valence is a multiple of \(x\)?”

**Answer rule:**
Yes, for all allowed values \(x \ge 2\).

**Reasoning:**
Any positive even multiple of \(x\) works for any number of vertices. Positive odd multiples of \(x\) can also work when the number of vertices is even.

#### 8. A full valence list is given
**Prompt form:**
“A connected graph has \(n\) vertices with valences ... . Can it exist?”

**Answer rule:**
Check the full list directly.

**Reasoning:**
The answer is Yes exactly when:

- each valence is at least 1,
- the total valence is even,
- and the total valence is at least \(2(n-1)\).

In this tool, these explicit-list questions are limited to at most **10 vertices** for readability.

#### 9. \(x\) vertices have valence \(a\), and \(y\) vertices have valence \(b\)
**Prompt form:**
“Can a connected graph exist with \(x\) vertices of valence \(a\) and \(y\) vertices of valence \(b\)?”

**Answer rule:**
Yes exactly when the total valence is even and at least \(2(n-1)\), where \(n=x+y\).

**Reasoning:**
The total valence is
\[
xa+yb.
\]
Then apply the master rule.

#### 10. The sum of the valences is odd
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if the sum of the valences is odd?”

**Answer rule:**
No.

**Reasoning:**
In any undirected graph, the total valence must be even.

#### 11. The sum of the valences is even
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if the sum of the valences is even?”

**Answer rule:**
Yes.

**Reasoning:**
An even total is required, although not every even total works. It still must be large enough for connectedness. But some valid even totals do work, so the answer is Yes.

#### 12. The product of the valences is odd
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if the product of the valences is odd?”

**Answer rule:**
Yes exactly when the number of vertices is even.

**Reasoning:**
A product is odd only when every valence is odd. Then the number of odd-valence vertices is the number of vertices, which must be even.

#### 13. The product of the valences is even
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if the product of the valences is even?”

**Answer rule:**
Yes.

**Reasoning:**
An even product means at least one valence is even. That alone does not force a valid graph, but many valid cases do exist, so the answer is Yes.

#### 14. Exactly \(x\) edges
**Prompt form:**
“Can a connected graph with \(n\) vertices exist with exactly \(x\) edges?”

**Answer rule:**
Yes exactly when \(x \ge n-1\).

**Reasoning:**
A connected graph with \(n\) vertices must have at least \(n-1\) edges.

#### 15. Exactly \(k\) vertices have odd valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if exactly \(k\) vertices have odd valence?”

**Answer rule:**
Yes exactly when \(k\) is even.

**Reasoning:**
The number of odd-valence vertices must be even.

#### 16. Exactly \(k\) vertices have even valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if exactly \(k\) vertices have even valence?”

**Answer rule:**
Yes exactly when \(n-k\) is even.

**Reasoning:**
If exactly \(k\) vertices are even, then the remaining \(n-k\) vertices are odd. That odd-count must be even.

#### 17. The sum of the valences is \(s\)
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if the sum of the valences is \(s\)?”

**Answer rule:**
Yes exactly when:

- \(s\) is even, and
- \(s \ge 2(n-1)\).

**Reasoning:**
These are exactly the total-valence conditions from the master rule.

#### 18. Exactly one vertex has odd valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if exactly one vertex has odd valence?”

**Answer rule:**
No.

**Reasoning:**
The number of odd-valence vertices must be even.

#### 19. Exactly one vertex has even valence
**Prompt form:**
“A connected graph has \(n\) vertices. Can it exist if exactly one vertex has even valence?”

**Answer rule:**
Yes exactly when \(n-1\) is even.

**Reasoning:**
If exactly one vertex is even, then the other \(n-1\) vertices are odd. That count must be even.

### Important Design Restrictions

The current implementation also enforces the following:

- no valence 0 cases,
- no single-vertex cases,
- no “multiple of 1” questions,
- explicit valence-list prompts are capped at 10 vertices,
- valence 1 is only allowed in the fixed-valence question when the graph has 2 vertices.

These choices keep the questions aligned with connectedness and with the intended classroom focus.

## Tab 2: Valence

It presents short graph questions in which one value, labeled `X`, must be found from the relationship

`sum of all valences = 2 × (number of edges)`.

The tool is designed to be simple, mobile-friendly, and easy to use in class, for homework, or for quick self-check practice.

### Features

- mobile-friendly layout for phones, tablets, and laptops
- randomly generates two kinds of practice questions
- small values so problems can be solved by hand
- one-tap button to reveal the value of `X`
- refresh button for a new random question

### Question Types

The tool randomly displays one of these two question formats:

1. Suppose a graph consists of `X` edges and `V` vertices with valences `a, b, c, ...`. Solve for `X`.
2. Suppose a graph consists of `E` edges and `V` vertices with valences `a, b, c, ..., X`. Solve for `X`.

### Mathematical Idea

Each question uses the Handshaking Formula:

`sum of all valences = 2 × (number of edges)`

Because this version allows self-loops and repeated edges, the tool focuses only on this formula and keeps the arithmetic small for classroom use.

### Classroom Use

This tool is intended for quick skill practice. Students can:

- add the listed valences and divide by 2 to find the number of edges, or
- double the number of edges and subtract the known valences to find the missing valence.

The simplified layout is designed so students can focus on the arithmetic and the structure of the Handshaking Formula without extra distractions.

## Tab 3: Grouping

The challenge presents questions of the form:

> A group of **P** people form teams of **N**. If the total valence is **V**, how many teams were formed?

The goal is for students to determine the number of teams by interpreting the situation as a graph problem.

### Mathematical Idea

This scenario can be modeled with a **bipartite graph**:

- one part contains the **people**
- the other part contains the **teams**
- an edge connects a person to a team when that person belongs to that team

In this model:

- the **valence of a person vertex** is the number of teams that person belongs to
- the **valence of a team vertex** is the number of people on that team

Since every team has exactly **N** people, each team vertex has valence **N**.

If there are **T** teams, then the number of edges is:

> E = N × T

By the Handshaking Formula, the total valence is:

> V = 2E = 2NT

So the number of teams is:

> T = V / (2N)

Students should also check that the situation can be drawn as a valid bipartite graph. The graph does **not** need to be connected.

### Instructions for Students

Use the tool to answer each question.

1. Read the prompt.
2. Model the situation as a bipartite graph with people on one side and teams on the other.
3. Use the Handshaking Formula to determine the number of teams.
4. Press **Solution** to reveal the answer.
5. Press **Refresh** for a new question.
6. Press **Instructions** to view the in-app explanation, and press **Question** to return to the current prompt.

### Buttons

- **Solution** — reveals the number of teams and shows the answer box
- **Refresh** — generates a new question and clears the previous answer
- **Instructions** — replaces the current question with the instructions text
- **Question** — restores the same question after viewing the instructions

In instruction mode, the Teams text is left-justified for readability.

### Question Generation

The tool randomly chooses:

- the number of people **P**
- the team size **N**
- the number of teams **T**

It then computes the total valence using:

> V = 2NT

The displayed values are intentionally kept fairly small so students can also sketch a possible graph by hand.

## Combined Interface Notes

The combined version keeps the three original tools in one shared shell.

- The full HTML page title is **Graph Tester**.
- The tabs are named **Existence**, **Valence**, and **Grouping**.
- The mathematical logic of each tool is preserved.
- The appearance is unified across tabs using a consistent color palette, fonts, card styling, and button styling.
- No functionality or instructional notes were intentionally removed.

## License

Copyright (c) 2026 Alan Miller.

This project is released under the **MIT License**.

See the [`LICENSE`](LICENSE) file for the full license text.
