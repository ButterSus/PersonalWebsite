# Алгебра

Это актуальные билеты по сессии в СУНЦ МГУ.
Надеюсь, что они помогут вам сдать экзамен.

> **Внимание!**
>
> Это не конспект лекций, а билеты по сессии. Некоторые темы могут быть не раскрыты полностью,
> поэтому рекомендую использовать их в качестве подготовки к экзамену.
>
{style="warning"}

## 1. Делимость чисел

Для удобства мне же, я буду использовать странный символ для обозначения делимости.

<tldr>

```tex
\begin{align}
&\texttt{В дальнейшем вместо знака}:\ &\vdots&_\texttt{(делимость)}\\
&\texttt{будет использоваться}:\ &\overset{_\operatorname{div}}{=}
\end{align}
```

</tldr>

### 1.1. Определение делимости

Если `a` делится на `b`, то мы всегда можем разложить `a` на множители `b` и `q`.

<procedure>

```tex
a, b \in \mathbb{Z},\ a \neq 0:\ a \overset{_\operatorname{div}}{=} b \Leftrightarrow \exists c \in \mathbb{Z}:\ b = aq
```

</procedure>

<note>
Таким образом, число 0 делится на любое число, кроме 0. (по определению)
</note>

### 1.2. Теорема о делении с остатком

Для любых целых чисел `a` и `b`, где `b` не равно нулю,
существуют единственные целые числа `q` и `r`, такие что `a = bq + r`, где `0 <= r < |b|`.

<procedure>

```tex
\begin{align}
&a, b \in \mathbb{Z},\ b \neq 0\Rightarrow&\\
&\exists!\,q, r \in \mathbb{Z}:\begin{cases}
a = bq + r\\0 \leq r < |b|&
\end{cases}\end{align}
```

</procedure>

<note>

```tex
\begin{align}
&\texttt{Заметим например, что в таком случае}\Rightarrow&\\
&a - r \overset{_\operatorname{div}}{=} b&
\end{align}
```

</note>

### 1.3. Свойства делимости

#### 1.3.1. Арифметические свойства

<tabs>
<tab title="Сумма / Разность">
<tip>

```tex
\begin{align}
&a, b \overset{_\operatorname{div}}{=} m\Rightarrow&_\texttt{(Если оба числа делятся на m)}&\\
&a \pm b \overset{_\operatorname{div}}{=} m&_\texttt{(то их сумма и разность тоже делятся на m)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1,b = mq_2\Rightarrow&\\
&a \pm b = mq_1 \pm mq_2 = m(q_1 \pm q_2)&\\
&\Rightarrow a\pm b= m(q_1 \pm q_2)\overset{_\operatorname{div}}{=} m&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение-1">

Этого не было на лекции, однако это обобщенное свойство.

<tip>
    
```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} m,\ b \overset{_\operatorname{div}}{=} n\Rightarrow&_\texttt{(Если оба числа делятся на m и n)}&\\
&ab \overset{_\operatorname{div}}{=} mn&_\texttt{(то их произведение тоже делятся на mn)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1,b = nq_2\Rightarrow&\\
&ab = mq_1nq_2 = mn(q_1q_2)&\\
&\Rightarrow ab = mn(q_1q_2)\overset{_\operatorname{div}}{=} mn&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение-2">

Это свойство можно легко получить из <shortcut>Произведение-1</shortcut>.

<tip>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} m,\ k \in \mathbb{Z}\Rightarrow&_\texttt{(Если a делится на m, а k - произвольное целое число)}&\\
&ak \overset{_\operatorname{div}}{=} m&_\texttt{(то произведение a на k делится на m.)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1\Rightarrow&\\
&ak = mq_1k = m(q_1k)&\\
&\Rightarrow ak = m(q_1k)\overset{_\operatorname{div}}{=} m&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение-3">

Это свойство можно легко получить из <shortcut>Произведение-1</shortcut>.

<tip>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} m,\ n \in \mathbb{N}\Rightarrow&_\texttt{(Если a делится на m, а n - произвольное натуральное число)}&\\
&a^n \overset{_\operatorname{div}}{=} m^n&_\texttt{(то произведение a в степени n делится на m в степени n.)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1\Rightarrow&\\
&a^n = \left(mq_1\right)^n&\\
&\Rightarrow a^n = m^n(q_1^n)\overset{_\operatorname{div}}{=} m^n&
\end{align}
```

</procedure>
</tab>
</tabs>

#### 1.3.2. Модуль делителя

Если `a` делится на `m`, но `a` не равен нулю, то `|a|` не меньше `m`.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} m,\ a \neq 0\Rightarrow&\\
&|a| \geq m&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq\Rightarrow&\\
&\begin{cases}
|a| = |mq| = |m||q|\\
|q| \geq 1_\texttt{(так как не равен нулю)}&
\end{cases}&\\
&\Rightarrow |a| \geq |m|&
\end{align}
```

</procedure>

### 1.4 Простые числа

#### 1.4.1. Определение простого числа

Простое число - это натуральное число, которое делится только на 1 и на само себя.

<procedure>

```tex
\begin{align}
&\texttt{let}\,p \in \mathbb{N}\Rightarrow&\\
&p \texttt{ - простое} \Leftrightarrow\begin{cases}
a \overset{_\operatorname{div}}{=} p\\
a \overset{_\operatorname{div}}{=} 1&
\end{cases}&
\end{align}
```

</procedure>

<procedure title="Примеры" collapsible="true">

```tex
\begin{align}
&2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, \ldots&
\end{align}
```

</procedure>

#### 1.4.2. Определение взаимно простых чисел

Взаимно простые числа - это целые числа, которые не имеют общих делителей, кроме 1, -1.

<procedure>

```tex
\begin{align}
&\texttt{let}\,a, b \in \mathbb{Z}\Rightarrow&\\
&a, b \texttt{ - взаимно простые} \Leftrightarrow
\operatorname{gcd}(a, b) = 1&
\end{align}
```

</procedure>

#### 1.4.3. Теорема о взаимно простых числах

Если `a` и `b` взаимно простые, то существуют такие целые числа `x0` и `y0`, что `ax0 + by0 = 1`.

<procedure>

```tex
\begin{align}
&a, b \texttt{ - взаимно простые}\Rightarrow&\\
&\exists x_0, y_0 \in \mathbb{Z}:\ ax_0 + by_0 = 1&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{Следуем от противного:}&\\
&\texttt{let}\,ax_0 + by_0 = c,\ x_0, y_0 \in \mathbb{Z}_\texttt{(c - наименьшее)}&\\
&\begin{aligned}
&\texttt{let}\,a = cq_a + r_a&\\
&\Rightarrow r_a = a - cq_a&
\end{aligned}\Leftrightarrow\begin{aligned}
&r_a= a - cq_a=a-(ax_0+by_0)q_a&\\
&=a(1-x_0q_a)+b(-y_0q_a)&
\end{aligned}&\\
&\texttt{Заметим, что}\ r_a\ \texttt{тоже подходит под}\ ax_0+by_0=c&\\
&\Rightarrow r_a\lt c,\forall r_a \in \mathbb{N}_\texttt{(противоречие)}&\\
&\Rightarrow r_a = 0,\ \underline{\texttt{а такое возможно только если}\ c = 1}&
\end{align}
```

</procedure>