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
