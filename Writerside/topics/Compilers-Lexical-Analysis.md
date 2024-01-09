# Lexical Analysis

In this topic, we will discover **the theory behind
lexical analysis**, and the most common algorithms
used to implement it.

In my opinion, **you can skip this topic if you are
only interested in the practical side of compilers.**
However, it's still a good idea to read it, as
in universities, it's usually taught before the
practical side.

## Overview

<procedure>

We will discover the next topics in this order:

- [Foundations](#foundations)
- Implementation
- Implementation Details
- Practical Problems

</procedure>

## Foundations

<procedure>

Lexical analysis is the first phase of a front-end.

<img src="compilers-compiler-structure.png" alt="Compiler Structure" width="600"/>

</procedure>

It takes the program as a sequence of characters, and
produces a sequence of symbols called <emphasis>tokens</emphasis>.

<procedure>

Goals of lexical analysis:

- **Functionality**: Produce tokens from the input program.
  It should be able to handle all valid programs.
- **Programmer Support**: Provide useful error messages, correct
  common mistakes, and provide useful information to the programmer.
- **Remove Redundancy**: Remove redundant information from the
  input program, such as comments and whitespace.
- **Identify Keywords**: Identify keywords in the input program and
  separate them from identifiers.
  **It's important as parser uses token types** to determine the structure of the program.
- **Construct Symbol Table**: Construct a symbol table for the
  input program.
  It's typically **a map with all strings in the program**,
  and instead of storing the string itself, it stores a key to
  the string in the symbol table.
  _(Strings appear multiple times)_

</procedure>

## Notations

Before we start, it's nice to have a common understanding of
[regular expressions and their practical use](https://en.wikipedia.org/wiki/Regular_expression).

### Math behind Lexical Analysis

We are going to use a lot of mathematical notations in this topic,
most of them are related to [set theory](https://en.wikipedia.org/wiki/Set_theory).

<tip>

The theory of formal languages and grammars is **a vast
area of mathematics, adjacent to algebra, mathematical
logic (set theory) and automata theory**.

</tip>

### Alphabets

The first thing we need to define is the alphabet of the language.

<procedure>

```tex
\begin{align}
&\Sigma = \{a, b, c\} \ -\ \texttt{alphabet}
\end{align} 
```

</procedure>

You can think of **an alphabet as a set of characters**.
**Characters are the smallest unit of a language**, and they are used to
construct words.
**The alphabet of a language is finite**.

Now let's take a look at operations on alphabets.

<procedure>

```tex
\begin{align}
&\varepsilon \ -\ \texttt{empty string}\\
&\Sigma^* = \{\varepsilon, a, b, c, aa, ab, \ldots\} \ -\ \texttt{set of all words over alphabet}\\
&\Sigma^+ = \{a, b, c, aa, ab, \ldots\} \ -\ \texttt{set of all non-empty strings over alphabet}\\
&\Sigma^k = \{aa, ab, ac, \ldots\} \ -\ \texttt{set of all strings of length k over alphabet}
\end{align} 
```

</procedure>

They are pretty straightforward, these operations can remind you of regular expressions.
Basically, now we are dealing with sets of strings.

Also, we can use default operations on sets, such as union, intersection, etc.

<procedure>

```tex
\begin{align}
&\Sigma^* = \Sigma^+ \cup \{\varepsilon\}
\end{align}
```

</procedure>

<procedure title="Examples" collapsible="true">

```tex
\begin{align}
&\Sigma_1 = \{1, 2, 3\} \ -\ \texttt{alphabet}\\
&\Sigma_2 = \{a, b, c\} \ -\ \texttt{alphabet}\\
&\Sigma_1^* = \{\varepsilon, 1, 2, 3, 11, 12, \ldots\} \ -\ \texttt{set of all words over alphabet}\\
&\Sigma_1 \cup \Sigma_2 = \{1, 2, 3, a, b, c\} \ -\ \texttt{union of alphabets}\\
&\Sigma_1 \cap \Sigma_2 = \varnothing \ -\ \texttt{intersection of alphabets}\\
\end{align} 
```

</procedure>

### Words and Letters

In the previous section, we defined alphabets using characters and
strings.

<procedure>

```tex
\begin{align}
&a \in \Sigma \ -\ \texttt{letter (character)}\\
&\alpha \in \Sigma^* \ -\ \texttt{word/sentence (string)}
\end{align} 
```

I prefer to use greek letters for words, and latin letters for characters.

</procedure>

But it's more correct to call them <emphasis>letters</emphasis> and <emphasis>words</emphasis>.

<note>

Note that **word and letter are different things**.

```tex
\begin{align}
&\alpha \neq a \ -\ \texttt{word is not a letter}&\\
&\alpha \notin \Sigma \ -\ \texttt{word is not a letter}&\\
&a \notin \Sigma^* \ -\ \texttt{letter is not a word}&
\end{align}  
```

</note>

More formally, word is a concatenation of letters.

<procedure>

```tex
\begin{align}
&\alpha = a_1 \cap a_2 \cap \ldots \cap a_n \ -\ \texttt{word (string)}\\
&\Leftrightarrow \alpha = a_1 a_2 \ldots a_n \ -\ \texttt{word (string)}
\end{align} 
```

It's convenient to use the second notation, as it's more compact.

</procedure>

**Concatenation of words is also a word**.

<procedure>

```tex
\begin{align}
&\alpha_1 \alpha_2 \ldots \alpha_n \ -\ \texttt{concatenation of words}\\
&\alpha^k = \underbrace{\alpha \alpha \ldots \alpha}_{k \text{ times}} \ -\ \texttt{power of word}\\
&\Rightarrow \alpha^0 = \varepsilon \ -\ \texttt{empty word}
\end{align} 
```

</procedure>

Besides concatenation, there are also few other operations on words.

<procedure>

```tex
\begin{align}
&\alpha^* = \underbrace{\alpha \alpha \ldots \alpha}_{k \geq 0 \text{ times}} \ -\ \texttt{Kleene star of word}\\
&\alpha^+ = \underbrace{\alpha \alpha \ldots \alpha}_{k \geq 1 \text{ times}} \ -\ \texttt{Kleene plus of word}\\
&\texttt{Note, that}\ \alpha^* \notin \Sigma^* \ -\ \texttt{Any of these is not a word}
\end{align} 
```

</procedure>

These are not words anymore, it's languages.

<procedure title="Examples" collapsible="true">

```tex
\begin{align}
&\alpha = hello \ -\ \texttt{word (string)}\\
&\beta = world \ -\ \texttt{word (string)}\\
&\alpha \beta = helloworld \ -\ \texttt{concatenation of words}\\
&\not\exists\, \alpha \cup \beta \ -\ \texttt{illegal operation}\\
&\alpha eduard = helloeduard \ -\ \texttt{in this case, it's concatenation}
\end{align} 
```

</procedure>

### Languages

We call a set of words a <emphasis>language</emphasis>.
`L` is a common notation for languages.

<procedure>

```tex
\begin{align}
&L \subseteq \Sigma^* \ -\ \texttt{language (set of words)}&\\
&\texttt{e.g.} \ \begin{aligned}
&L_1 = \{string1, abc, 123\} \subset \{abcgintrs123\}^*&\\
&L_2 = \varnothing \subset \{abcgintrs123\}^*&
\end{aligned}&
\end{align} 
```

</procedure>

What is funny, it's already enough to define simple
constructions, such as numbers.

<procedure>

```tex
\begin{align}
&\Sigma_{num} = \{0, 1, 2, 3, 4, 5, 6, 7, 8, 9\} \ -\ \texttt{alphabet of numbers}&\\
&L_{num} = \Sigma_{num}^+ \ -\ \texttt{language of numbers}&
\end{align} 
```

</procedure>

**Operations on languages produce new languages**.

<procedure>

```tex
\begin{align}
&L_1 \cup L_2 \ -\ \texttt{union of languages}\\
&\Rightarrow L_1 \cup L_2 = \{\alpha \mid \alpha \in L_1 \lor \alpha \in L_2\}\\
&L_1 L_2 \ -\ \texttt{concatenation of languages}\\
&\Rightarrow L_1 L_2 = \{\alpha_1 \alpha_2 \mid \alpha_1 \in L_1 \land \alpha_2 \in L_2\}\\
&\overline{L} \ -\ \texttt{complement of language}\\
&\Rightarrow \overline{L} = \Sigma^* \setminus L\\
&L^n \ -\ \texttt{power of language}\\
&\Rightarrow L^n = \{\alpha_1 \alpha_2 \ldots \alpha_n \mid \alpha_i \in L\}\\
&L^* \ -\ \texttt{Kleene star of language}\\
&\Rightarrow L^* = \{\alpha_1 \alpha_2 \ldots \alpha_n \mid n \geq 0 \land \alpha_i \in L\}\\
&L^+ \ -\ \texttt{Kleene plus of language}\\
&\Rightarrow L^+ = \{\alpha_1 \alpha_2 \ldots \alpha_n \mid n \geq 1 \land \alpha_i \in L\}
\end{align} 
```

</procedure>

<procedure title="Examples" collapsible="true">

```tex
\begin{align}
&L_1(\Sigma_1=\{ab\}) = \{a^n b^n \mid n \geq 0\} \ -\ \texttt{language of words of form}\ a^n b^n&\\
&\Rightarrow \ \left[\begin{aligned}
&\varepsilon \in L_1&\\
&ab \in L_1&\\
&aaabbb \in L_1&\\
&a \notin L_1&\\
&aabbb \notin L_1&
\end{aligned}\right.&\\
&L_2(\Sigma_2=\{\texttt{0123456789+-/*}\}) - \texttt{let's define arithmetic expressions}&\\
&\quad\begin{aligned}
&L_{op} = \{\texttt{+}, \texttt{-}, \texttt{*}, \texttt{/}\}&\\
&L_{num} = \Sigma_{num}^+ = \{0, 1, 2, \ldots, 9\}^+&\\
&L_{expr} = L_{num} (L_{op} L_{num})^*&
\end{aligned}&
\end{align}
```

</procedure>

### Regular Languages

<emphasis>Regular languages</emphasis> are languages that can be
described using **regular expressions**.

<procedure>

<img src="compilers-regular-language.png" alt="Regular Language" height="200"/>

</procedure>

More formally, **regular languages more likely can find practical use,
as they are easier to implement using finite state machines**.

<tip>

All regular languages are languages,
but not all languages are regular.

</tip>

### Regular Expressions

Each regular language can be described using
<emphasis>regular expressions</emphasis>.

| Expression | Language     | Example words          |
|------------|--------------|------------------------|
| `a \| b`   | `{a, b}`     | `a`, `b`               |
| `ab*a`     | `{a}{b}*{a}` | `aa`, `aba`, `abba`    |
| `(ab)*`    | `{ab}*`      | `ε`, `ab`, `abab`, ... |
| `a?`       | `{ε, a}`     | `ε`, `a`               |

We guess that you are already familiar with regular expressions,
so we won't go into details.

To show that a language is regular, we can
use next notation:

<procedure>

```tex
\begin{align}
&L(r) \ -\ \texttt{language described by regular expression r}&\\
&\texttt{e.g.} \ \begin{aligned}
&L(a \mid b) = \{a, b\}&\\
&L(ab^*a) = \{aa, aba, abba, \ldots\}&
\end{aligned}&
\end{align} 
```

</procedure>

<tip>

In 1950, Stephen Kleene extended regular expressions with
new operations:

```tex
\begin{align}
&L([a-z]) = \{a, b, c, \ldots, z\} \ -\ \texttt{range of characters}&\\
&L(r?) = L(r) \cup \{\varepsilon\} \ -\ \texttt{optional}&\\
&L(r_1 \mid r_2) = L(r_1) \cup L(r_2) \ -\ \texttt{union}&\\
&L(r_1 r_2) = L(r_1) L(r_2) \ -\ \texttt{concatenation}&\\
&L(r^*) = L(r)^* \ -\ \texttt{Kleene star}&\\
&L(r^+) = L(r)^+ \ -\ \texttt{Kleene plus}&
\end{align}
```

</tip>

<note>

**Nowadays, regular expressions can also contain a lot of other
operations**, such as _look-ahead_, _look-behind_, _grouping_, etc.
_(We won't cover them in this topic, as they weren't introduced
in lectures)_

</note>

## Automata

**Finite state machines** also known as <emphasis>automata</emphasis>
are often used to **describe regular languages**.
However, usage of automata is not limited to regular languages.

In the case of lexers, we are going to think of automata as
**program that implements regular expressions**.
This is the main part of the lexer.

<procedure>

Facts about automata:

- It makes transitions from one configuration to another. _(They are called <emphasis>states</emphasis>)_
- Each configuration **consists of (the rest of) the input and some memory**.
  _(We use this information to determine the next state)_
- The type of memory determines its ability to recognize a class of languages.

</procedure>

### A Non-Deterministic Finite-State Machine (NFSM)

One of the simplest automata is a <emphasis>non-deterministic finite-state machine</emphasis>.

<procedure>

```tex
\begin{align}
&M = \langle \Sigma, Q, \Delta, q_0, F \rangle \ -\ \texttt{NFSM}&\\ 
&\Sigma \ -\ \texttt{alphabet}&\\
&Q \ -\ \texttt{finite set of states}&\\
&\Delta \subseteq Q \times (\Sigma \cup \{ \varepsilon \}) \times Q \ -\ \texttt{transition relation}&\\
&q_0 \in Q \ -\ \texttt{initial state}&\\
&F \subseteq Q \ -\ \texttt{set of final states}&\\
&\delta(q, w) \in \Delta \ -\ \texttt{transition function}&\\
&\quad \delta(q_0, \varepsilon) \rightarrow q_0 \ -\ \texttt{as example}&\\
&\quad \hat{\delta}(q, \alpha x) \rightarrow \delta(\hat{\delta}(q, \alpha), x) \ -\ \texttt{recursively apply transition function}&\\
&\qquad \texttt{where}\, \hat{\delta} \ -\ \texttt{extended transition function, which accepts words}&
\end{align}
```

</procedure>

<tip>

The hardest part is to understand **the transition relation**.

```tex
\begin{align}
&\texttt{Basically, transition}(\Delta)\,\texttt{depends on}&\\
&\quad\begin{aligned}
&\texttt{what is the current state}(\subseteq Q)&\\
&\texttt{what is the current input}(\times (\Sigma \cup \{ \varepsilon \}))&\\
&\texttt{and what is the next state}(\times Q)&
\end{aligned}&
\end{align} 
```

</tip>

Other parts will be clear after we see an example.

<procedure title="Example of NFSM">

We use directed graph to represent NFSM.

<img src="compilers-nfsm-example.png" alt="NFSM Example" width="480"/>

Let's take a look at fragments of NFSM:

- <img alt="NFSM" src="compilers-nfsm-fragment-1.png" height="40" style="inline" border-effect="rounded"/> - 
  **initial state** _(first state when we start the program)_
- <img alt="NFSM" src="compilers-nfsm-fragment-2.png" height="24" style="inline" border-effect="rounded"/> - 
  **alphabet**
- <img alt="NFSM" src="compilers-nfsm-fragment-3.png" height="40" style="inline" border-effect="rounded"/> and
  <img alt="NFSM" src="compilers-nfsm-fragment-4.png" height="40" style="inline" border-effect="rounded"/> - 
  **final states** _(with double stroke)_
- <img alt="NFSM" src="compilers-nfsm-fragment-5.png" width="320" style="inline" border-effect="rounded"/> -
  **transition relation** _(table)_
- <img alt="NFSM" src="compilers-nfsm-fragment-6.png" height="40" style="inline" border-effect="rounded"/> and
  <img alt="NFSM" src="compilers-nfsm-fragment-7.png" height="40" style="inline" border-effect="rounded"/> -
  **transition requirements** as part of the transition relation
- **states** are represented as circles

In this example, we have NFSM that recognizes **fractional numbers with scientific notation**.
`2.14e3` as example.

</procedure>

<note>

<img src="compilers-nfsm-reason.png" alt="NFSM Reason" height="160" style="inline" border-effect="rounded"/>
Here is the reason **why it's called non-deterministic**.

</note>

The only problem with NFSM is that its **time complexity is exponential**,
as we need to check all possible paths.

### FSM to Lexical Analyzer

Of course, we can't use FSM (NFSM) as a lexical analyzer without
any modifications.

<procedure>

Here's my diagram of how FSM is used in the lexical analyzer.

<img src="compilers-nfsm-to-lexer.png" alt="NFSM to Lexer" width="480"/>

As you can see, each time we end new token, we need to
**reset the FSM to the initial state with the rest of the input**.

</procedure>

#### Maximal Munch Strategy

Note, our **FSM** uses greedy strategy; it tries to
**match as many characters as possible**.

It's shown in the diagram as **saving the last end token position** _(if it's a final state)_.

<tip>

The only thing not shown in the diagram is that
**if we can't find any token, we need to output illegal token**.

</tip>

<procedure title="Example" collapsible="true">

Let's assume we have the next input: `2.14e+s`:

1. We **save the last end token position** a few times, the last one is `2.14`.
2. We can **save 'e+'** as part of the number **if it ends with a digit** like so: `2.14e+3`.
3. After it gets to the `s`, we can't find any legal transition, so we **end the token**.
4. It's important that in this case we are **using non-deterministic automata**, so we can
   **try to find another token with `e+s`**.
5. We will discover other approaches to handle this case later when we talk about
   **deterministic automata**.
6. 
</procedure>

### The Language Accepted by the FSM

Firstly, let's define what configurations are.

<procedure>

```tex
\begin{align}
&M = \langle \Sigma, Q, \Delta, q_0, F \rangle \ -\ \texttt{FSM}&\\
&\Rightarrow q \in Q, w \in \Sigma^*:&\\
&\quad(q, w) \ -\ \texttt{is a configuration}&\\
\end{align} 
```

</procedure>

<emphasis>Configuration</emphasis> is a pair of state and the rest of the input.
It's used to **desribe steps** in formal way.
Like so:

<procedure>

```tex
\begin{align}
&(q, x\alpha) \vdash_M (p, \alpha) \ -\ \texttt{binary relation}&\\
&\texttt{where}\, \alpha \in \Sigma^*, x \in \Sigma, q, p \in Q&
\end{align} 
```

</procedure>

That operation is called <emphasis>transitive closure</emphasis>.
To show more than one step, we can use <emphasis>reflexive transitive closure</emphasis>.

<procedure>

```tex
\begin{align}
&\vdash_M^k \ -\ \texttt{exactly k steps}&\\
&\vdash_M^* \ -\ \texttt{zero or more steps}&\\
&\vdash_M^+ \ -\ \texttt{one or more steps}&
\end{align} 
```

</procedure>

We can also define language using FSM.

<procedure>

```tex
\begin{align}
&L(M) = \{w \in \Sigma^* \mid \exists\,q_f \in F : (q_0, w) \vdash_M^* (q_f, \varepsilon)\}&
\end{align} 
```

</procedure>
