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

### 5.2. Типы последовательностей

<tabs>
<tab title="Возрастающая">

<emphasis>Возрастающая последовательность</emphasis> — это последовательность, в которой каждый следующий член больше предыдущего.

<procedure>

```tex
\forall{n\in\mathbb{N}}:a_n\lt{a_{n+1}}
```

</procedure>
</tab>

<tab title="Убывающая">

<emphasis>Убывающая последовательность</emphasis> — это последовательность, в которой каждый следующий член меньше предыдущего.

<procedure>

```tex
\forall{n\in\mathbb{N}}:a_n\gt{a_{n+1}}
```

</procedure>
</tab>

<tab title="Неубывающая">

<emphasis>Неубывающая последовательность</emphasis> — это последовательность, в которой каждый следующий член не меньше предыдущего.

<procedure>

```tex
\forall{n\in\mathbb{N}}:a_n\leq{a_{n+1}}
```

</procedure>
</tab>

<tab title="Невозрастающая">

<emphasis>Невозрастающая последовательность</emphasis> — это последовательность, в которой каждый следующий член не больше предыдущего.

<procedure>

```tex
\forall{n\in\mathbb{N}}:a_n\geq{a_{n+1}}
```

</procedure>
</tab>

<tab title="Монотонная">

<emphasis>Монотонная последовательность</emphasis> — это последовательность, которая либо постоянно возрастает,
либо постоянно убывает.

<procedure>

```tex
\forall{n\in\mathbb{N}}:a_n\leq{a_{n+1}}\vee\forall{n\in\mathbb{N}}:a_n\geq{a_{n+1}}
```

</procedure>
</tab>
</tabs>

Ещё очень важно знать про ограниченные последовательности.

<tabs>
<tab title="Ограниченная сверху">

<emphasis>Ограниченная сверху последовательность</emphasis> — это последовательность, в которой все члены не превосходят некоторого числа.

<procedure>

```tex
\exists{M\in\mathbb{R}}:\forall{n\in\mathbb{N}}:a_n\leq{M}
```

</procedure>
</tab>

<tab title="Ограниченная снизу">

<emphasis>Ограниченная снизу последовательность</emphasis> — это последовательность, в которой все члены не меньше некоторого числа.

<procedure>

```tex
\exists{m\in\mathbb{R}}:\forall{n\in\mathbb{N}}:a_n\geq{m}
```

</procedure>
</tab>

<tab title="Ограниченная">

<emphasis>Ограниченная последовательность</emphasis> — это последовательность, в которой все члены по модулю не превосходят некоторого числа.

<procedure>

```tex
\exists{m}\in\mathbb{R}:\forall{n\in\mathbb{N}}:\left|a_n\right|\leq{m}
```

</procedure>
</tab>
</tabs>

### 5.3. Определение предела последовательности

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

### 5.4. Эпсилон-окрестность

<emphasis>Эпсилон-окрестность</emphasis> — это симметричный интервал вокруг точки `A` с радиусом `ε`.

<procedure>

```tex
\begin{align}
&\varepsilon\texttt{-окрестность}=\left\{x:\left|x-A\right|\lt\varepsilon\right\}&
\end{align}
```

</procedure>

Ещё существует <emphasis>проколотая эпсилон-окрестность</emphasis> - это эпсилон-окрестность без самой точки `A`.

<procedure>

```tex
\begin{align}
&\varepsilon\texttt{-проколотая окрестность}=\left\{x:0\lt\left|x-A\right|\lt\varepsilon\right\}&
\end{align}
```

</procedure>

## 6. Свойства сходящихся

### 6.0. Определение сходящейся последовательности

<emphasis>Сходящаяся последовательность</emphasis> — это последовательность, которая имеет предел.

<procedure>

```tex
\begin{align}
\exists{\mathcal{A}\in\mathbb{R}}:\forall{\varepsilon\gt0}\Rightarrow\exists{\,N=N(\varepsilon)\in\mathbb{N}:}
\left|a_n-\mathcal{A}\right|\lt\varepsilon,\,\forall{n\gt{N}}
\end{align}
```

</procedure>

<emphasis>Расходящаяся последовательность</emphasis> — это последовательность, которая не имеет предела.

<procedure>

```tex
\begin{align}
\forall{\mathcal{A}\in\mathbb{R}}:\exists{\varepsilon\gt0}\Rightarrow\forall{\,N=N(\varepsilon)\in\mathbb{N}:}
\left|a_n-\mathcal{A}\right|\geq\varepsilon,\,\exists{n\gt{N}}
\end{align}
```

</procedure>

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
{\max_{i=1}^{N(1)}a_i}\right)}&\\
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

<tab title="Обратное">
<tip>

```tex
\lim_{n\to\infty}\frac{1}{b_n}=\frac{1}{\mathcal{B}};\ b_n, \mathcal{B}\neq0
```

</tip>

<procedure title="Доказательство">

```tex
\begin{align}
&1)\,\texttt{let}B>0:\,\texttt{let}\,\varepsilon_1=\frac{\mathcal{B}}{2}&\\
&\Rightarrow\left|b_n-\mathcal{B}\right|\lt\frac{\mathcal{B}}{2},\forall{n}\gt{N_1(\varepsilon_1)}&\\
&\Leftrightarrow\frac{\mathcal{B}}{2}\lt{b_n}\lt\frac{3\mathcal{B}}{2}&\\
&\texttt{let}\,m=\min\left(b_1,b_2,\ldots,b_{N_1(\varepsilon_1)},\frac{\mathcal{B}}{2}\right)&\\
&\Rightarrow\forall{n}\in\mathbb{N}:\left|b_n\right|\ge{m}\gt0&\\
&\texttt{let}\,\varepsilon_2=\varepsilon m\mathcal{B}&\\
&\Rightarrow\left|b_n-\mathcal{B}\right|\lt\varepsilon_2,\forall{n}\gt{N_2(\varepsilon_2)}&\\
&\left|\frac{1}{b_n}-\frac{1}{\mathcal{B}}\right|=\left|\frac{\mathcal{B}-b_n}{b_n\mathcal{B}}\right|&\\
&=\frac{\left|b_n-\mathcal{B}\right|}{\mathcal{B}\cdot\left|b_n\right|}\lt\frac{\varepsilon_2}{\mathcal{B}\cdot{m}}
=\frac{\varepsilon\cdot{m}\cdot\mathcal{B}}{\mathcal{B}\cdot{m}}=\varepsilon_\texttt{(как определение предела)}&\\
&\Rightarrow\lim_{n\to\infty}\frac{1}{b_n}=\frac{1}{\mathcal{B}}&\\\\
&2)\,\texttt{let}\,B\lt0:\,\Rightarrow\lim_{n\to\infty}\frac{1}{-b_n}=\frac{1}{-\mathcal{B}}
\ _\texttt{(по пункту 1)}&\\
&\Rightarrow\lim_{n\to\infty}\frac{1}{b_n}=\frac{1}{\mathcal{B}}&\\
\end{align}
```

</procedure>

<warning>

Будьте очень осторожны, ведь не зря `B > 0` в первом пункте,
иначе минимум будет работать неправильно!

</warning>
</tab>

<tab title="Частное">
<tip>

```tex
\lim_{n\to\infty}\frac{a_n}{b_n}=\frac{\mathcal{A}}{\mathcal{B}};\ b_n, \mathcal{B}\neq0
```

</tip>

<procedure title="Доказательство">

```tex
\begin{align}
&\lim_{n\to\infty}\frac{a_n}{b_n}=\lim_{n\to\infty}a_n\times\frac{1}{b_n}
=\mathcal{A}\times\frac{1}{\mathcal{B}}=\frac{\mathcal{A}}{\mathcal{B}}&\\
&_\texttt{(тут мы пользуемся пределами последовательностей, которые мы уже доказали)}&
\end{align}
```

</procedure>
</tab>

<tab title="Корень">
<tip>

```tex
\lim_{n\to\infty}\sqrt{a_n}=\sqrt{\mathcal{A}};\ a_n, \mathcal{A}\geq0
```

</tip>

<procedure title="Доказательство">

```tex
\begin{align}
&1)\,\texttt{let}\,\mathcal{A}=0:\texttt{let}\,\varepsilon_0=\varepsilon^2&\\
&\Rightarrow\left|a_n-\mathcal{A}\right|\lt\varepsilon^2,\forall{n}\gt{N(\varepsilon^2)}&\\
&\Leftrightarrow a_n \lt\varepsilon^2\Rightarrow\sqrt{a_n}\lt\varepsilon&\\
&\Rightarrow\underline{\left|\sqrt{a_n}-0\right|\lt\varepsilon}\Rightarrow\lim_{n\to\infty}\sqrt{a_n}=0&\\\\
&2)\,\texttt{let}\,\mathcal{A}\gt0:\texttt{let}\,\varepsilon_0=\varepsilon\sqrt{\mathcal{A}}&\\
&\left|\sqrt{a_n}-\sqrt{\mathcal{A}}\right|=\frac{\left|a_n-\mathcal{A}\right|}{\sqrt{a_n}+\sqrt{\mathcal{A}}}&\\
&\lt\frac{\left|a_n-\mathcal{A}\right|}{\sqrt{\mathcal{A}}}\lt\frac{\varepsilon_0}{\sqrt{\mathcal{A}}}
=\frac{\varepsilon\sqrt{\mathcal{A}}}{\sqrt{\mathcal{A}}}=\varepsilon_\texttt{(как определение предела)}&\\
&\Rightarrow\lim_{n\to\infty}\sqrt{a_n}=\sqrt{\mathcal{A}}&\\
\end{align}
```

</procedure>
</tab>
</tabs>

## 10. Теорема Вейерштрасса

Всякая монотонная и ограниченная последовательность сходится (имеет предел).

<img src="calculus_weierstrass_theorem.png" alt="Теорема Вейерштрасса" width="400" align="right"/>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a=\sup\{a_n\}&\\
&\Rightarrow \forall\,\varepsilon:\exists{N}\texttt{:}&\\
&x_N\gt{a}-\varepsilon&\\
&x_n\gt{x_N}\gt{a}-\varepsilon,\forall{n}\gt{N}&\\
&\Rightarrow a-\varepsilon\lt{x_n}\lt{a}+\varepsilon,\forall{n}\gt{N}&\\
&\Leftrightarrow \underline{\left|x_n-a\right|\lt\varepsilon},\forall{n}\gt{N}&\\
\end{align}
```

</procedure>

## 11. Базовые пределы

Их всего 5, но они очень важны.

<tabs>
<tab title="1-й предел">

<tip>

```tex
\lim_{n\to\infty}\frac{1}{n}=0
```

</tip>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,\mathcal{A}=0:&\\
&\Rightarrow \left|\frac{1}{n}-0\right|\lt\varepsilon,\forall{n}\gt{N(\varepsilon)}&\\
&\Leftrightarrow \frac{1}{n}\lt\varepsilon\\
&\Leftrightarrow n\gt\frac{1}{\varepsilon}\Rightarrow\exists\,{N(\varepsilon)}=\left[\frac{1}{\varepsilon}\right]+1&\\
\end{align}
```

</procedure>
</tab>

<tab title="2-й предел">

<tip>

```tex
\lim_{n\to\infty}\sqrt[n]{1+a^n}=\left[\begin{aligned}
&0\lt a\le 1&\rightarrow 1& \\
&a\gt 1&\rightarrow a&
\end{aligned}\right .
```

</tip>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&1)\,\texttt{let}\,0\lt{a}\le1:&\\
&\textbf{Зажимаем по милиционерам:}&\\
&\texttt{Снизу ограничен:} \sqrt[n]{1+a^n}\ge1+an\ge1\ _\texttt{(по неравенству Бернулли)}&\\
&\texttt{Сверху предел:} \lim_{n\to\infty}1+a^n=1&\\
&\texttt{т.к:} \lim_{n\to\infty}1+a^n\gt\lim_{n\to\infty}\sqrt[n]{1+a^n}\ge1&\\
&\textbf{Получаем:} \lim_{n\to\infty}\sqrt[n]{1+a^n}=1&\\\\

&2)\,\texttt{let}\,a=1:&\\
&\lim_{n\to\infty}\sqrt[n]{1+1^n}=\lim_{n\to\infty}\sqrt[n]{2}=1&\\\\

&3)\,\texttt{let}\,a\gt1:&\\
&\lim_{n\to\infty}\sqrt[n]{1+a^n}=\lim_{n\to\infty}\sqrt[n]{a^n(1+\frac{1}{a^n})}&\\
&=\lim_{n\to\infty}a\sqrt[n]{1+\frac{1}{a^n}}=a\cdot1=a&\\
\end{align}
```

</procedure>
</tab>

<tab title="3-й предел">
<tip>

```tex
\lim_{n\to\infty}\sqrt[n]{a}=1;\ a\gt0
```

</tip>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&1)\,\texttt{let}\,a=1:&\\
&\lim_{n\to\infty}\sqrt[n]{1}=1&\\\\
&2)\,\texttt{let}\,a\gt1:&\\
&a=(\sqrt[n]{a})^n\gt\sqrt[n]{a}=(1+\sqrt[n]{a}-1)^n\ge1+n(\sqrt[n]{a}-1)&\\
&\gt n(\sqrt[n]{a}-1)\Rightarrow 1+\frac{a}{n}\gt\sqrt[n]{a}\gt1&\\
&\textbf{Зажимаем по милиционерам:}&\\
&\texttt{Снизу ограничен:} \sqrt[n]{a}\ge1, \forall{n}\gt1&\\
&\texttt{Сверху предел:} \lim_{n\to\infty}1+\frac{a}{n}=1&\\
&\texttt{т.к:} \lim_{n\to\infty}1+\frac{a}{n}\gt\lim_{n\to\infty}\sqrt[n]{a}\ge1&\\
&\textbf{Получаем:} \lim_{n\to\infty}\sqrt[n]{a}=1&\\\\
&3)\,\texttt{let}\,0\lt{a}\lt1:&\\
&\lim_{n\to\infty}\sqrt[n]{a}=\frac{1}{\lim_{n\to\infty}\sqrt[n]{\frac{1}{a}}}
\ _\texttt{(для пункта 2 переворачиваем дробь)}&\\
&=\frac{1}{1}=1&\\
\end{align}
```

</procedure>
</tab>

<tab title="4-й предел">
<tip>

```tex
\lim_{n\to\infty}q^n=0,\ \left|q\right|\lt1
```

</tip>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&1)\,\texttt{let}\,q=0:&\\
&\lim_{n\to\infty}0^n=0&\\\\
&2)\,\texttt{let}\,0\lt\left|q\right|\lt1:&\\
&\frac{1}{|q^n|}=(1+\alpha)^n\ge 1+n\alpha\gt n\alpha\ _\texttt{(по неравенству Бернулли)}&\\
&\forall\,\varepsilon\gt0:\exists{N}\in\mathbb{N}:\left|q^n\right|\lt\frac{1}
{n\alpha}\lt\varepsilon,\forall{n}\gt{N}&\\
&\Rightarrow \underline{N(\varepsilon)=\left[\frac{1}{\alpha\varepsilon}\right]+1}&\\
\end{align}
```

</procedure>
</tab>

<tab title="5-й предел">
<tip>

```tex
\lim_{n\to\infty}\sqrt[n]{n}=1
```

</tip>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a_n=\sqrt[n]{n}-1&\\
&\Leftrightarrow 1+a_n=\sqrt[n]{n}&\\
&\Rightarrow \left(1+a_n\right)^n=n&\\
&n=\left(1+a_n\right)^n\gt \frac{n(n-1)}{2}\cdot a_n^2\ _\texttt{(по биному Ньютона 3-ий член)}&\\
&\textbf{Зажимаем по милиционерам:}&\\
&\texttt{Снизу ограничен:} a_n\gt0&\\
&\texttt{Сверху предел:} \lim_{n\to\infty}\frac{2}{n-1}=0&\\
&\texttt{т.к:} \lim_{n\to\infty}\frac{2}{n-1}\gt\lim_{n\to\infty}a_n\ge0&\\
&\textbf{Получаем:} \lim_{n\to\infty}a_n=\lim_{n\to\infty}\sqrt[n]{n}-1=0&\\
&\Rightarrow \underline{\lim_{n\to\infty}\sqrt[n]{n}=1}&\\
\end{align}
```

</procedure>
</tab>
</tabs>

## 12. Число эйлера и его свойства

Само число Эйлера обозначается как `e`.

Оно равно пределу последовательности, которое доказывается через теорему Вейерштрасса.

<procedure title="Определение числа `e`" collapsible="true">

```tex
\begin{align}
&e=\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^n&\\
\end{align}
```

</procedure>

Ниже перечислены основные свойства числа `e`. (которые мы успели пройти)

<procedure>

```tex
\begin{align}
&\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^{n\pm c}=e, \forall c\in\mathbb{R} &\\
&\lim_{n\to\infty}\left(1+\frac{k}{nm}\right)^n=e^\frac{k}{m}, \forall k,m\in\mathbb{N} &\\
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

Докажем, что эта последовательность ограничена сверху.

```tex
\begin{align}
&\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^n\overset{?}\lt{3}\ _\texttt{(по биному Ньютона)}&\\
&\Leftrightarrow \sum_{k=1}C_n^k\cdot\frac{1}{n^k}=1+\underset{=1}{\underline{n\cdot\frac{1}{n}}}+\sum_{k=2}C_n^k\cdot\frac{1}{n^k}&\\
&=2+\sum_{k=2}\frac{n!}{k!\cdot(n-k)!}\cdot\frac{1}{n^k}&\\
&=2+\sum_{k=2}\frac{(n-k+1)\cdot(n-k+2)\cdot\ldots\cdot{n}}{k!}\cdot\frac{1}{n^k}&\\
&=2+\sum_{k=2}\frac{1}{k!}\cdot\underset{\lt1}{\underline{\frac{n-k+1}{n}\cdot\frac{n-k+2}{n}\cdot\ldots\cdot\frac{n}{n}}}&\\
&\lt2+\sum_{k=2}\frac{1}{k!}\lt2+\sum_{k=2}\frac{1}{2^{k-1}}&\\
&=2+\frac{1}{2}+\frac{1}{4}+\frac{1}{8}+\ldots=2+\frac{1}{2}\cdot\frac{1}{1-\frac{1}{2}}=3&\\
\end{align}
```

Затем очевидно, что эта последовательность возрастает, так как каждый следующий член больше предыдущего.

```tex
\begin{align}
&\texttt{let}\,a_n=\left(1+\frac{1}{n}\right)^n&\\
&\Rightarrow a_{n+1}\overset{?}\gt{a_n}
\Leftrightarrow \left(1+\frac{1}{n+1}\right)^{n+1}\gt\left(1+\frac{1}{n}\right)^n&\\
&\Leftrightarrow a_n\cdot\underset{\gt1}{\underline{\left(1+\frac{1}{n+1}\right)}}\gt{a_n}&\\
\end{align}
```

По теореме Вейерштрасса, так как эта последовательность **возрастает** и **ограничена** сверху, **то она сходится**.

</procedure>

## 13. Продолжение...

Читайте дальше в [следующей части](Calculus-3.md).