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
&\texttt{будет использоваться}:\ &\overset{\times}{\sim}
\end{align}
```

</tldr>

### 1.1. Определение делимости

Если `a` делится на `b`, то мы всегда можем разложить `a` на множители `b` и `q`.

<procedure>

```tex
a, b \in \mathbb{Z},\ a \neq 0:\ a \overset{\times}{\sim} b \Leftrightarrow \exists c \in \mathbb{Z}:\ b = aq
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
&a - r \overset{\times}{\sim} b&
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
&a, b \overset{\times}{\sim} m\Rightarrow&_\texttt{(Если оба числа делятся на m)}&\\
&a \pm b \overset{\times}{\sim} m&_\texttt{(то их сумма и разность тоже делятся на m)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1,b = mq_2\Rightarrow&\\
&a \pm b = mq_1 \pm mq_2 = m(q_1 \pm q_2)&\\
&\Rightarrow a\pm b= m(q_1 \pm q_2)\overset{\times}{\sim} m&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение-1">

Этого не было на лекции, однако это обобщенное свойство.

<tip>
    
```tex
\begin{align}
&a \overset{\times}{\sim} m,\ b \overset{\times}{\sim} n\Rightarrow&_\texttt{(Если оба числа делятся на m и n)}&\\
&ab \overset{\times}{\sim} mn&_\texttt{(то их произведение тоже делятся на mn)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1,b = nq_2\Rightarrow&\\
&ab = mq_1nq_2 = mn(q_1q_2)&\\
&\Rightarrow ab = mn(q_1q_2)\overset{\times}{\sim} mn&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение-2">

Это свойство можно легко получить из <shortcut>Произведение-1</shortcut>.

<tip>

```tex
\begin{align}
&a \overset{\times}{\sim} m,\ k \in \mathbb{Z}\Rightarrow&_\texttt{(Если a делится на m, а k - произвольное целое число)}&\\
&ak \overset{\times}{\sim} m&_\texttt{(то произведение a на k делится на m.)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1\Rightarrow&\\
&ak = mq_1k = m(q_1k)&\\
&\Rightarrow ak = m(q_1k)\overset{\times}{\sim} m&
\end{align}
```

</procedure>
</tab>

<tab title="Произведение-3">

Это свойство можно легко получить из <shortcut>Произведение-1</shortcut>.

<tip>

```tex
\begin{align}
&a \overset{\times}{\sim} m,\ n \in \mathbb{N}\Rightarrow&_\texttt{(Если a делится на m, а n - произвольное натуральное число)}&\\
&a^n \overset{\times}{\sim} m^n&_\texttt{(то произведение a в степени n делится на m в степени n.)}&
\end{align}
```

</tip>
<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a = mq_1\Rightarrow&\\
&a^n = \left(mq_1\right)^n&\\
&\Rightarrow a^n = m^n(q_1^n)\overset{\times}{\sim} m^n&
\end{align}
```

</procedure>
</tab>
</tabs>