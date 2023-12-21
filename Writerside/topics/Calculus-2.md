# Анализ 2

Это продолжение [Анализа 1](Calculus-1.md).

## 5. Последовательности

### 5.1. Определение бесконечной числовой последовательности

<emphasis>Бесконечная числовая последовательность</emphasis> — это функция, определённая на множестве натуральных чисел.

<procedure>

```tex
\begin{align}
\begin{array}{ll}
    \left\{a_n\right\}_{n=1}^{\infty}=\left\{a_1, a_2, a_3, \ldots\right\} & \texttt{(С помощью множеств)} \\
    \forall n \in \mathbb{N}: a_n \in \mathbb{R} & \texttt{(Иной способ)}
\end{array}
\end{align}
```

</procedure>

<img src="calculus_sequence.png" alt="Бесконечная числовая последовательность" width="400" align="right"/>

### 5.2. Определение предела последовательности

<emphasis>Предел последовательности</emphasis> — это число, к которому стремится последовательность, если
устремить её аргумент к бесконечности.

<procedure>

```tex
\begin{align}
&\mathcal{A}=\lim_{n \to \infty}a_n & \texttt{(для удобства пишем так)}& \\
&\Leftrightarrow \forall{\varepsilon\gt0}\Rightarrow\exists{\,N=N(\varepsilon)\in\mathbb{N}:}& \\
&\left|a_n-\mathcal{A}\right|\lt\varepsilon,\,\forall{n\gt{N}}&
\end{align}
```

</procedure>

<img src="calculus_sequence_limit.png" alt="Предел последовательности" width="400" align="right"/>

<note>
Начиная с некоторого номера, все точки (значения) попадают в эпсилон-окрестность точки `A`.
</note>

### 5.3. Эпсилон-окрестность

<emphasis>Эпсилон-окрестность</emphasis> — это симметричный интервал вокруг точки `A` с радиусом `ε`.

<procedure>

```tex
\begin{align}
&\varepsilon\texttt{-окрестность}=\left\{x:\left|x-A\right|\lt\varepsilon\right\}&
\end{align}
```

</procedure>

## 6. Свойства сходящихся

### 6.1. Определение ограниченной последовательности

<emphasis>Ограниченная последовательность</emphasis> — это последовательность, которая ограничена сверху или снизу
так, что все её значения не превосходят некоторого числа.

<procedure>

```tex
\begin{align}
\left[
\begin{array}{ll}
    \texttt{Ограничена сверху:} & \exists{M\in\mathbb{R}}:\forall{n\in\mathbb{N}}:a_n\leq{M} \\
    \texttt{Ограничена снизу:} & \exists{m\in\mathbb{R}}:\forall{n\in\mathbb{N}}:a_n\geq{m}
\end{array}
\right .
\end{align}
```

</procedure>

Однако я так понимаю, определение ограниченной последовательности следует понимать по другому:

<procedure>

```tex
\texttt{Ограничена:}\,\exists{A, B\in\mathbb{R}}:\forall{n\in\mathbb{N}}:A\leq{a_n}\leq{B}
```

</procedure>

<img src="calculus_bounded_sequence.png" alt="Ограниченная последовательность" width="400" align="right"/>

### 6.2. Предел существует только один

Если у последовательности и существует предел, то он единственный.

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{Следуем из противного:}& \\
&\texttt{let}\,\lim_{n\to\infty}a_n\in\left\{\mathcal{A,B}\right\}& \\
&\texttt{let}\,\varepsilon=\frac{\varepsilon}{2}\Rightarrow\forall{\,\varepsilon\gt0:}& \\
&\underline{\left|\mathcal{A}-\mathcal{B}\right|}\le\left|a_n-\mathcal{A}\right|+\left|
a_n-\mathcal{B}\right|\lt\underline{\varepsilon}&\texttt{(по определению)} \\
&\begin{cases}
\mathcal{A}\gt\mathcal{B}\Rightarrow \begin{array}{ll}
\left|\mathcal{A}-\mathcal{B}\right|=\mathcal{A}
-\mathcal{B},\,\texttt{let}\,\varepsilon=\frac{\mathcal{A}-\mathcal{B}}{4}\\
\Leftrightarrow \mathcal{A}-\mathcal{B}\lt \frac{\mathcal{A}-\mathcal{B}}{4}\Rightarrow
\mathcal{A}\lt\mathcal{B}_\texttt{(противоречие)}
\end{array} \\

\mathcal{A}\lt\mathcal{B}\Rightarrow \begin{array}{ll}
\left|\mathcal{A}-\mathcal{B}\right|=\mathcal{B}
-\mathcal{A},\,\texttt{let}\,\varepsilon=\frac{\mathcal{A}-\mathcal{B}}{4}\\
\Leftrightarrow \mathcal{B}-\mathcal{A}\lt \frac{\mathcal{A}-\mathcal{B}}{4}\Rightarrow
\mathcal{A}\gt\mathcal{B}_\texttt{(противоречие)}
\end{array} \\
\Rightarrow\mathcal{A}=\mathcal{B}
\end{cases}&
\end{align}
```

</procedure>

### 6.3. Положительный предел

Если последовательность сходится (имеет предел) к положительному числу, то начиная
с некоторого номера все её значения будут больше нуля.

```tex
\lim_{n\to\infty}a_n=A\gt0\Rightarrow\exists{N},\,\forall{n\gt{N}}:a_n\gt0
```

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,\varepsilon=\frac{\mathcal{A}}{2}\Rightarrow_\texttt{(определение предела)}\ldots:&\\
&\underset{\texttt{=epsilon}}{-\frac{\mathcal{A}}{2}}\lt{\left|a_n-\mathcal{A}\right|}\lt\underset{\texttt{=epsilon}}{\frac{\mathcal{A}}{2}},
\forall{n}\gt{N(\varepsilon)}&\\&\Leftrightarrow{\frac{\mathcal{A}}{2}}
\lt{a_n}\lt\frac{3\mathcal{A}}{2}\Rightarrow\underline{a_n
\gt\frac{\mathcal{A}}{2}\gt0,\,\forall{n}\gt{N(\varepsilon)}}&
\end{align}
```

</procedure>

## 7. Сходящаяся ограничена

Для всяких последовательностей, которые сходятся, справедливо то, что они ограничены.

```tex
\lim_{n\to\infty}a_n=A\Rightarrow\exists{A, B\in\mathbb{R}},\forall{n\in\mathbb{N}}:A\leq{a_n}\leq{B}
```

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,\varepsilon=1\Rightarrow_\texttt{(по определению предела)}\ldots:&\\
&-1\lt{a_n}-\mathcal{A}\lt1,\forall{n\gt}N(\varepsilon)&\\
&\Leftrightarrow \mathcal{A}-1\lt{a_n}\lt\mathcal{A}+1&\\
&\Rightarrow \begin{aligned}
&\texttt{let}\,\alpha=\min{\left(\mathcal{A}-1,
\underset{\underline{\texttt{finite array}}}
{\min_{i=1}^{N(1)}a_i}\right)}&\\
&\texttt{let}\,\beta=\max{\left(\mathcal{A}+1,
\underset{\underline{\texttt{finite array}}}
{\min_{i=1}^{N(1)}a_i}\right)}&\\
\end{aligned}&\\
&\Rightarrow\forall{n\in\mathbb{N}}:\underline{\alpha\lt{a_n}\lt\beta}&
\end{align}
```

</procedure>

<note>
Не все ограниченные последовательности сходятся.

Например, последовательность `a_n=(-1)^n` ограничена, но не сходится.
</note>

## 8. Теорема о милиционерах

Ещё эту теорему называют <emphasis>теоремой о зажатой последовательности</emphasis>.

<procedure title="Формулировка">

Если <format style="bold" color="DarkSeaGreen">последовательность</format> зажата
<format style="bold" color="SlateBlue">сверху</format> и 
<format style="bold" color="Tomato">снизу</format> сходящимися последовательностями, то она сходится к тому же пределу.

```tex
\begin{align}
&\begin{cases}
\forall{n\in\mathbb{N}}:a_n\leq{b_n}\leq{c_n} \\
\lim_{n\to\infty}a_n=\lim_{n\to\infty}c_n=\mathcal{A}
\end{cases}&\Rightarrow\lim_{n\to\infty}b_n=\mathcal{A}
\end{align}
```

<img src="calculus_sandwich_theorem.png" alt="Теорема о милиционерах" width="400" align="right"/>

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\forall\varepsilon\gt0\Rightarrow_\texttt{(по определению предела)}\ldots:&\\
&\begin{cases}
\exists{N_1\in\mathbb{N}}:\forall{n\gt{N_1}}:\left|a_n-\mathcal{A}\right|\lt\varepsilon \\
\exists{N_2\in\mathbb{N}}:\forall{n\gt{N_2}}:\left|c_n-\mathcal{A}\right|\lt\varepsilon
\end{cases}&\\
&\texttt{let}\,N=\max(N_1,N_2)\Rightarrow&\\
&\Rightarrow\begin{cases}
\forall{n\gt{N}}:\left|a_n-\mathcal{A}\right|\lt\varepsilon \\
\forall{n\gt{N}}:\left|c_n-\mathcal{A}\right|\lt\varepsilon
\end{cases}&\\
&\Rightarrow\begin{cases}
\mathcal{A}-\varepsilon\lt{a_n}\lt\mathcal{A}+\varepsilon \\
\mathcal{A}-\varepsilon\lt{c_n}\lt\mathcal{A}+\varepsilon
\end{cases}&\\
&\Rightarrow\mathcal{A}-\varepsilon\lt{a_n}\leq{b_n}\leq{c_n}\lt\mathcal{A}+\varepsilon&\\
&\Rightarrow\left|b_n-\mathcal{A}\right|\lt\varepsilon,\forall{n\gt{N}}&\\
&\Rightarrow\lim_{n\to\infty}b_n=\mathcal{A}_\texttt{(как определение предела)}&
\end{align}
```

</procedure>

## 9. Арифметические действия с пределами

<tldr>

```tex
\begin{align}
&\text{let}\,\mathcal{A}=\lim_{n\to\infty}a_n&\\
&\text{let}\,\mathcal{B}=\lim_{n\to\infty}b_n&\\
\end{align}
\texttt{Будем использовать эти обозначения в дальнейшем.}
```

</tldr>

Все эти действия с пределами можно делать только в том случае, если пределы существуют.
Иногда бывает так, что одного из пределов не существует, но <shortcut>сумма/разность/...</shortcut> существуют.

<tabs>
<tab title="Сумма">
<tip>

```tex
\lim_{n\to\infty}\left(a_n+b_n\right)=\mathcal{A}+\mathcal{B}
```

</tip>

<procedure title="Доказательство">

```tex
\begin{align}
&\texttt{let}\,\varepsilon=\frac\varepsilon2\Rightarrow_
\texttt{(по определению предела)}\ldots:&\\
&\left|\left(a_n-\mathcal{A}\right)+\left(b_n-\mathcal{B}\right)\right|
=\underline{\left|\left(a_n+b_n\right)-\left(\mathcal{A}+\mathcal{B}\right)\right|}&\\
&\le\left|a_n-\mathcal{A}\right|+\left|b_n-\mathcal{B}\right|\lt\underset
{=2\times\frac\varepsilon2}{\underline{\varepsilon}}&
\end{align}
```

</procedure>
</tab>

<tab title="Разность">
<tip>

```tex
\lim_{n\to\infty}\left(a_n-b_n\right)=\mathcal{A}-\mathcal{B}
```

</tip>

<procedure title="Доказательство">

```tex
\begin{align}
&\texttt{let}\,\varepsilon=\frac\varepsilon2\Rightarrow_
\texttt{(по определению предела)}\ldots:&\\
&\left|\left(a_n-\mathcal{A}\right)-\left(b_n-\mathcal{B}\right)\right|
=\underline{\left|\left(a_n-b_n\right)-\left(\mathcal{A}-\mathcal{B}\right)\right|}&\\
&\le\left|a_n-\mathcal{A}\right|+\left|b_n-\mathcal{B}\right|\lt\underset
{=2\times\frac\varepsilon2}{\underline{\varepsilon}}&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение">
<tip>

```tex
\lim_{n\to\infty}\left(a_n\times{b_n}\right)=\mathcal{A}\times\mathcal{B}
```

</tip>

<procedure title="Доказательство">

```tex
\begin{align}
&\forall\varepsilon_1,\varepsilon_2\gt0:\begin{cases}
\left|a_n-\mathcal{A}\right|\lt\varepsilon_1, \forall\,n>N_1(\varepsilon_1)\\
\left|b_n-\mathcal{B}\right|\lt\varepsilon_2, \forall\,n>N_2(\varepsilon_2)
\end{cases}&\\
&\texttt{let}\,M\in\mathbb{R}:M\ge{b_n},
\forall{n\in\mathbb{N}}&\\&\Leftrightarrow\left|\left(a_n\right)
\times b_n-\mathcal{A}\times\left(\mathcal{B}\right)\right|
=\left|\left(a_n-\mathcal{A}\right)\times b_n-\mathcal{A}
\times\left(\mathcal{B}-b_n\right)\right|&\\
&=\left|\left(a_n-\mathcal{A}\right)\times b_n+\mathcal{A}
\times\left(b_n-\mathcal{B}\right)\right|\le\left|a_n-\mathcal{A}
\right|\times\left|b_n\right|+\left|\mathcal{A}\right|\times
\left|b_n-\mathcal{B}\right|&\\&\lt\varepsilon_1\times\underset
{\ge b_n}{M}+\left|\mathcal{A}\right|\times\varepsilon_2,\,\texttt{let}\,
\varepsilon_1=\frac\varepsilon{2M};\varepsilon_2=\frac\varepsilon{2\left|
\mathcal{A}\right|},\forall\,n>\max\left(N_1,N_2\right)
&\\&\Rightarrow \left|a_n\times b_n-\mathcal{A}\times
\mathcal{B}\right|\lt\frac\varepsilon{2M}\times{M}+\frac\varepsilon{2
\left|\mathcal{A}\right|}\times\left|\mathcal{A}\right|=
\varepsilon_\texttt{(как определение предела)}&
\end{align}
```

</procedure>
</tab>

<tab title="Частное">
<tip>

```tex
\lim_{n\to\infty}\frac{1}{b_n}=\frac{1}{\mathcal{B}}
```

</tip>

<procedure title="Доказательство">

```tex
1
```

</procedure>
</tab>
</tabs>