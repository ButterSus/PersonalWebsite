# Анализ 3

## 13. Пределы функций

### 13.1. Виды окрестностей

<tabs>
<tab title="Эпсилон-окрестность">

<emphasis>Эпсилон-окрестностью</emphasis> точки `a` называется интервал `(a - ε, a + ε)` на оси `y`,
где `ε` - положительное число.

<img src="calculus_epsilon_delta.png" width="400" alt="Эпсилон-окрестность"/>

</tab>

<tab title="Дельта-окрестность">

<emphasis>Дельта-окрестностью</emphasis> точки `a` называется интервал `(a - δ, a + δ)` на оси `x`,
где `δ` - положительное число.

<img src="calculus_epsilon_delta.png" width="400" alt="Дельта-окрестность"/>

</tab>
</tabs>

### 13.2. Ограниченность в окрестности

Функция `f(x)` ограничена в окрестности точки `a`, если существует такое число `M`,
что для любого `x` из этой окрестности выполняется неравенство `|f(x)| <= M`.

<procedure>

```tex
\begin{align}
&\forall x \in (a - \delta, a) \cup (a, a + \delta) \implies |f(x)| \le M&\\\\
&\Leftrightarrow |f(x)| \le M, \forall x: 0 \lt |x - a| \lt \delta&
\end{align}
``` 

</procedure>

<warning>

Сама точка `a` не входит в окрестность.

</warning>

### 13.3. Определение предела функции

Функция `f(x)` имеет предел `A` в точке `a`, если для любого числа `ε > 0` существует такое число `δ > 0`,
что для любого `x` из окрестности точки `a` выполняется неравенство `|f(x) - A| < ε`.

[youtube]: https://www.youtube.com/watch?v=AtBk9RSeYJY&ab_channel=WildMathing

Это если что уже знакомство [по Коши][youtube]{ignore-vars="true"}.

<procedure>

```tex
\begin{align}
&\forall \varepsilon\gt0\Rightarrow\exists\delta\gt0:\forall x\in(a-\delta,a)\cup(a,a+\delta)\Rightarrow|f(x)-A|\lt\varepsilon&\\\\
&\Leftrightarrow\forall\varepsilon\gt0\Rightarrow\exists\delta\gt0:\forall x:0\lt|x-a|\lt\delta\Rightarrow|f(x)-A|\lt\varepsilon&
\end{align}
```

</procedure>

### 13.4. Свойства пределов функций

#### 13.4.1. Единственность предела

Если предел функции существует в точке `a`, то он единственный.

<procedure>

```tex
\begin{align}
&\exists!\,\lim_{x\to a}f(x)=\mathcal{A}&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{Следуем от противного:}&\\
&\exists\,\mathcal{A},\mathcal{B} - \texttt{пределы функции в точке } a:\mathcal{A}\ne\mathcal{B}&\\

\end{align}
```

</procedure>

