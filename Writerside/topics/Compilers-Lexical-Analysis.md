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
&\alpha_1 \alpha_2 \ldots \alpha_n \ -\ \texttt{concatenation of words}
\end{align} 
```

</procedure>

Besides concatenation, there are also few other operations on words.

<procedure>

```tex
\begin{align}
&\alpha^k = \underbrace{\alpha \alpha \ldots \alpha}_{k \text{ times}} \ -\ \texttt{power of word}\\
&\Rightarrow \alpha^0 = \varepsilon \ -\ \texttt{empty word}\\
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
