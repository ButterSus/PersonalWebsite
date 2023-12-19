# Математический анализ

Это актуальные билеты по сессии в СУНЦ МГУ.
Надеюсь, что они помогут вам сдать экзамен.

> **Внимание!**
>
> Это не конспект лекций, а билеты по сессии. Некоторые темы могут быть не раскрыты полностью,
> поэтому рекомендую использовать их в качестве подготовки к экзамену.
>
{style="warning"}

## 1. Множества

### 1.1. Определение множества

<tabs>
    <tab title="Множество">
        Это совокупность различных объектов, называемых элементами множества.
        <img src="calculus_set.png" alt="Множество" width="200" align="right"/>
    </tab>
    <tab title="Числовое множество">
        Это множество, элементами которого являются числа.
        <img src="calculus_set_of_numbers.png" alt="Числовое множество" width="300" align="right"/>
    </tab>
</tabs>

### 1.2. Стандартные множества

<procedure collapsible="true" title="Принято обозначать стандартные множества следующим образом:">

```tex
\begin{align}
\begin{array}{ll}
\mathbb{N}=\{1, 2, 3, \ldots\} \\
\mathbb{Z}=\{\ldots, -2, -1, 0, 1, 2, \ldots\} \\
\mathbb{Q}=\left\{\frac{m}{n} \mid m \in \mathbb{Z}, n \in \mathbb{N}\right\} \\
\mathbb{R}=(-\infty, +\infty) \\
\mathbb{C}=\{a+bi \mid a, b \in \mathbb{R}, i^2=-1\}
\end{array}
\end{align}
```

</procedure>

### 1.3. Операции над множествами

<tabs>
    <tab title="Объединение">
        <code-block lang="tex">$\forall A, B: A \cup B=\{x \mid x \in A \vee x \in B\}</code-block>
        <img src="calculus_union.png" alt="Объединение" width="200" align="right"/>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\cup}</code-block>
        </tip>
    </tab>
    <tab title="Пересечение">
        <code-block lang="tex">$\forall A, B: A \cap B=\{x \mid x \in A \wedge x \in B\}</code-block>
        <img src="calculus_intersection.png" alt="Пересечение" width="200" align="right"/>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\cap}</code-block>
        </tip>
    </tab>
    <tab title="Разность">
        <code-block lang="tex">$\forall A, B: A \setminus B=\{x \mid x \in A \wedge x \notin B\}</code-block>
        <img src="calculus_difference.png" alt="Разность" width="200" align="right"/>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\setminus}</code-block>
        </tip>
    </tab>
    <tab title="Симметрическая разность">
        <code-block lang="tex">$\forall A, B: A \triangle B=(A \setminus B) \cup(B \setminus A)</code-block>
        <img src="calculus_symmetric_difference.png" alt="Симметрическая разность" width="200" align="right"/>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\triangle}</code-block>
        </tip>
    </tab>
</tabs>

### 1.4. Основная формула включений и исключений

Запомните формулу включений и исключений, она пригодится вам на экзамене.

```tex
\left|\bigcup_{i=1}^{n}A_i\right|=\sum^n_{i=1}\left|A_i\right|-\sum^n_{i\lt j}\left|A_{ij}\right|+\sum^n_{i\lt j\lt k}\left|A_{ijk}\right|-\ldots
+\left(-1\right)^n\sum^n_{i\ldots}\left|A_{i\ldots}\right|
```

## 2. Числовые функции

<tldr>

```tex
\begin{align}
\begin{array}{ll}
\text{let}\,\mathbb{X}=\texttt{Область определения функции}  \\
\text{let}\,\mathbb{Y}=\texttt{Область значений функции}
\end{array}
\end{align}
```

</tldr>

### 2.1. Определение функции

<tabs>
    <tab title="Функция">
        Это отображение, которое каждому элементу из области определения ставит в соответствие единственный элемент из области значений.
        <img src="calculus_function.png" alt="Функция" width="400" align="right"/>
    </tab>
    <tab title="Область определения">
        Это множество, элементы которого являются аргументами функции.
        <img src="calculus_domain_and_range.png" alt="Область определения" width="400" align="right"/>
    </tab>
    <tab title="Область значений">
        Это множество, элементы которого являются значениями функции.
        <img src="calculus_domain_and_range.png" alt="Область значений" width="400" align="right"/>
    </tab>
</tabs>

### 2.2. Когда функции равны?

<tabs>
    <tab title="Функции равны">
        <code-block lang="tex">$\forall x \in \mathbb{X}: f(x)=g(x)</code-block>
        <img src="calculus_functions_are_equal.png" alt="Функции равны" width="400" align="right"/>
    </tab>
    <tab title="Функции не равны">
        <code-block lang="tex">$\exists x \in \mathbb{X}: f(x) \neq g(x)</code-block>
        <img src="calculus_functions_are_not_equal.png" alt="Функции не равны" width="400" align="right"/>
    </tab>
</tabs>

### 2.3. Монотонность функции

Функция называется <emphasis>монотонно возрастающей/убывающей</emphasis>,
если она строго возрастает/убывает на всей области определения.

<tabs>
    <tab title="Пример монотонной функции">
        <code-block lang="tex">$\forall x_1, x_2 \in \mathbb{X}: x_1 \lt x_2 \implies f(x_1) \lt f(x_2)$</code-block>
        <img src="calculus_monotonic_function.png" alt="Пример монотонной функции" width="400" align="right"/>
    </tab>
    <tab title="Пример не монотонной функции">
        <code-block lang="tex">$\exists x_1, x_2 \in \mathbb{X}: x_1 \lt x_2 \implies f(x_1) \nless f(x_2)$</code-block>
        <img src="calculus_not_monotonic_function.png" alt="Пример не монотонной функции" width="400" align="right"/>
    </tab>
</tabs>

## 3. Графики функций

### 3.1. Определение графика функции

<emphasis>График функции</emphasis> — это множество точек плоскости, координаты которых удовлетворяют уравнению функции.

<img src="calculus_function_graph.png" alt="График функции" width="400" align="right"/>

Каждая из точек удовлетворяют следующему условию:

```tex
\left(x, y\right) \in \mathbb{X} \times \mathbb{Y} \Leftrightarrow  y = f(x)
```

> Важно понимать, что график функции — это не сама функция, а множество точек, которые ей удовлетворяют.
>
{style="warning"}

### 3.2. Цепочка преобразований графика функции

Ниже указан <emphasis>порядок преобразований</emphasis> графика функции:

1. Сжимаем/растягиваем график по оси абсцисс.
    ```tex
    f(x) \to f(ax)
    ```
2. Сдвигаем график влево/вправо.
    ```tex
    f(ax) \to f(ax+b)
    ```
3. Сжимаем/растягиваем график по оси ординат.
    ```tex
    f(ax+b) \to Af(ax+b)
    ```
4. Сдвигаем график вверх/вниз.
    ```tex
    Af(ax+b) \to Af(ax+b)+B
    ```

Конечный результат:

<procedure>

```tex
\large f(x) \to f(ax) \to f(ax+b) \to Af(ax+b) \to Af(ax+b)+B
```

</procedure>

### 3.3. Запоминаем абсциссу/ординату на графике

Вот так можно запомнить, какая из осей называется абсциссой, а какая — ординатой.

<img src="calculus_abscissa_ordinate.png" alt="Абсцисса и ордината" width="400" align="right"/>

## 4. Обратная функция

### 4.1. Определение обратной функции

<emphasis>Обратная функция</emphasis> — это такая функция, которая отображает значения функции в аргументы.
Чтобы можно было получить обратную функцию, функция должна быть <emphasis>взаимно-однозначной</emphasis>.

<procedure>

```tex
\begin{cases}
\forall x \in \mathbb{X}: f^{-1}(f(x))=x \\
\forall y \in \mathbb{Y} \Rightarrow \exists!\,x(y) \in \mathbb{X} & (\texttt{существует единственный аргумент})
\end{cases}
```

</procedure>

<img src="calculus_inverse_function.png" alt="Обратная функция" width="400" align="right"/>

### 4.2. Симметрия графика обратной функции

> Заметим, что график обратной функции симметричен относительно прямой `y=x`.
>
> <img src="calculus_inverse_function_symmetry.png" alt="График обратной функции" height="400" align="right"/>
>
{style="note"}

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
Начиная с некоторого номера, все точки (значения) попадают в эпсилон-окрестность точки `A`, где <code-block lang="tex">
\varepsilon\texttt{-окрестность}=\left\{x:\left|x-A\right|\lt\varepsilon\right\}
</code-block>
</note>

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
\left|a_n-\mathcal{A}\right|\lt\varepsilon_1\\
\left|b_n-\mathcal{B}\right|\lt\varepsilon_2
\end{cases}\,\texttt{let}\,M\in\mathbb{R}:M\ge{b_n},
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
\mathcal{A}\right|}&\\&\Rightarrow \left|a_n\times b_n-\mathcal{A}\times
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
