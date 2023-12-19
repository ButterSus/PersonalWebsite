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

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{Следуем от противного:}&\\
&\texttt{let}\,a = bq_1 + r_1 = bq_2 + r_2, r_1 \lt r_2&\\
&\Rightarrow b(q_1 - q_2) = r_2 - r_1, q_1 - q_2 \ge 1_\texttt{(так как остатки не равны)}&\\
&\Rightarrow r_2 - r_1 \ge b(q_1 - q_2) \ge b&\\
&\texttt{let}\,r_1\in\left[0, b-1\right]\Rightarrow 
\underset{\notin\left[0, b-1\right]}{\underline{r_2\in\left[b, 2b-1\right]}}\,_\texttt{(противоречие)}&
\end{align}
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

#### 1.3.3. Сравнимость по модулю

<emphasis>Сравнимость по модулю</emphasis> - это отношение, которое устанавливается между двумя целыми
числами `a` и `b`, если их разность делится на `m`.

<procedure>

```tex
\begin{align}
&a, b \in \mathbb{Z},\ m \in \mathbb{N}\Rightarrow&\\
&a \overset{m}{\equiv} b \Leftrightarrow a - b \overset{_\operatorname{div}}{=} m&
\end{align}
```

</procedure>

<tip>
По сути, это значит, что `a` и `b` дают одинаковые остатки при делении на `m`.
</tip>

#### 1.3.4. Классы вычетов

<emphasis>Класс вычетов</emphasis> - это множество целых чисел, которые дают одинаковые остатки при делении на `m`.

<emphasis>Множество вычетов</emphasis> - это множество всех классов вычетов.

<procedure>

```tex
\begin{align}
&\texttt{мно-во вычетов}:\ \left[a\right]_m = \left\{\overline{0},
\overline{1}, \ldots, \overline{m-1}\right\};&\\
&\texttt{класс вычетов}:\ \overline{a} = \left\{a + mq\right\},\ q \in \mathbb{Z}&
\end{align}
```

</procedure>

### 1.4 Простые числа

#### 1.4.1. Определение простого числа

<emphasis>Простое число</emphasis> - это натуральное число, которое делится только на 1 и на само себя.

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

<note>
Таким образом, число 1 не является простым числом.
</note>

#### 1.4.2. Определение взаимно простых чисел

<emphasis>Взаимно простые числа</emphasis> - это целые числа, которые не имеют общих делителей, кроме 1, -1.

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

#### 1.4.4. Простых чисел бесконечно много

Множество простых чисел бесконечно. Это можно доказать от противного.

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{Следуем от противного:}&\\
&\texttt{let}\,p_1, p_2, \ldots, p_n\texttt{ - все простые числа}&\\
&\texttt{let}\,N = p_1p_2\ldots p_n + 1&\\
&\Rightarrow\texttt{по теореме о делении с остатком}\Rightarrow&\\
&\exists p_i:\ p_i \overset{_\operatorname{div}}{=} N&\\
&\Rightarrow p_i \overset{_\operatorname{div}}{=} p_1p_2\ldots p_n + 1&\\
&\Rightarrow p_i \overset{_\operatorname{div}}{=} 1\texttt{ (противоречие)}&
\end{align}
```

</procedure>

#### 1.4.5. Малая теорема Ферма

Если `p` - простое число, а `a` не делится на `p`, то `a^(p-1) - 1` делится на `p`.

<procedure>

```tex
\begin{align}
&p \texttt{ - простое},\ a \overset{_\operatorname{div}}{\neq} p\Rightarrow&\\
&a^{p-1} \overset{p}{\equiv} a& 
\end{align}
```

</procedure>

<tip>
Доказательство на сессии не требуется.

Такой способ не гарантирует, что если `p` подходит, то оно простое. (псевдопростые числа)
</tip>

#### 1.4.6. Теорема Вильсона

Число `p` - простое тогда и только тогда, когда `(p-1)! + 1` делится на `p`.

<procedure>

```tex
\begin{align}
&p \texttt{ - простое}\Leftrightarrow&\\
&(p-1)! + 1 \overset{_\operatorname{div}}{=} p&
\end{align}
```

</procedure>

<tip>
Доказательство на сессии не требуется.
</tip>

#### 1.4.7. Теорема Евклида

Наибольший общий делитель двух чисел равен наибольшему 
общему делителю остатка на деления большего делителя
на меньший делитель и меньшего делителя.

<procedure>

```tex
\begin{align}
&\texttt{let}\,a, b \in \mathbb{Z},\ \texttt{let}\,r\overset{b}{\equiv} a&\\
&\Rightarrow \operatorname{gcd}(a, b) = \operatorname{gcd}(b, r)&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,d = \operatorname{gcd}(a, b)&\\
&\Rightarrow\begin{cases}
a = dq_a\\
b = dq_b&
\end{cases}&\\
&\Rightarrow r = dq_a - dq_b * k = d\underset{\ge0}
{\underline{(q_a - q_bk)}}&\\
&\Rightarrow r \overset{d}{\equiv} 0
\Rightarrow \underline{d \overset{_\operatorname{div}}{=} \operatorname{gcd}(b, r)}&
\end{align}
```

</procedure>

### 1.5. Теорема о наибольшем общем делителе

Аналогично [Теореме о взаимно простых числах](#1-4-2), только теперь `a` и `b` заданы произвольно.

<procedure>

```tex
\begin{align}
&\texttt{let}\,a, b \in \mathbb{Z}\Rightarrow&\\
&\exists x_0, y_0 \in \mathbb{Z}:\ ax_0 + by_0 = \operatorname{gcd}(a, b)&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,d = \operatorname{gcd}(a, b)&\\
&\Rightarrow\texttt{let}\,a = dq_a,\ b = dq_b&\\
&\ldots_\texttt{(по теореме о взаимно простых числах)}&\\
&\Rightarrow\exists x_0, y_0 \in \mathbb{Z}:\ q_ax_0 + q_by_0 = 1\,|\times{d}&\\
&\Leftrightarrow\exists x_0, y_0 \in \mathbb{Z}:\ \underline{ax_0 + by_0 = d}&\\
\end{align}
```

</procedure>

### 1.6. Разрешимость линейного диофантова уравнения

<emphasis>Линейное диофантово уравнение</emphasis> - 
это уравнение вида `ax + by = c`, где `a`, `b`, `c` - целые числа, `x`, `y` - неизвестные.

Такое уравнение имеет решение тогда и только тогда, когда `c` делится на `d = gcd(a, b)`.

<procedure>

```tex
\begin{align}
&\texttt{let}\,a, b, c \in \mathbb{Z}\Rightarrow&\\
&\exists x_0, y_0 \in \mathbb{Z}:\ ax_0 + by_0 = c&\\
&\Leftrightarrow c \overset{_\operatorname{div}}{=} \operatorname{gcd}(a, b)&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&\texttt{let}\,a, b, c \in \mathbb{Z}\Rightarrow&\\
&\texttt{let}\,d = \operatorname{gcd}(a, b)&\\
&\Rightarrow ax + by = c&\\
&\Leftrightarrow q_ax + q_by = \frac{c}{d}&\\
&\Rightarrow\frac{c}{d}\in \mathbb{Z}\Rightarrow \underline{c \overset{_\operatorname{div}}{=} d}&
\end{align}
```

</procedure>

### 1.7. Признаки делимости

<tldr>

Для удобства будем использовать десятичную запись числа `a` в следующем виде:

```tex
a = a_n \cdot 10^n + a_{n-1} \cdot 10^{n-1} + \ldots + a_1 \cdot 10 + a_0 = \sum_{i=0}^{n} a_i \cdot 10^i
```

</tldr>

<tabs>
<tab title="/= на  2">

Число делится на 2 тогда и только тогда, когда последняя цифра числа делится на 2.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} 2 \Leftrightarrow a_0 \overset{_\operatorname{div}}{=} 2&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&a = a_0 + \sum_{i=1}^{n} a_i \cdot 10^i&\\
&\Rightarrow a_0 + \underset{\overset{_\operatorname{div}}{=} 2
}{\underline{2(5)\cdot\sum_{i=0}^{n-1} a_i \cdot 10^i}} \overset{2}{\equiv} a&\\
&\Leftrightarrow \underline{a_0 \overset{2}{\equiv} a}&
\end{align}
```

</procedure>
</tab>

<tab title="/= на  3">

Число делится на 3 тогда и только тогда, когда сумма его цифр делится на 3.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} 3 \Leftrightarrow \sum_{i=0}^{n} a_i \overset{_\operatorname{div}}{=} 3&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&a = \sum_{i=0}^{n} a_i \cdot 10^i&\\
&\Rightarrow \sum_{i=0}^{n} a_i \cdot (3\times3+1)^i \overset{3}{\equiv} a&\\
&\Leftrightarrow \sum_{i=0}^{n} a_i \cdot 1^i \overset{3}{\equiv} a
\Leftrightarrow \underline{\sum_{i=0}^{n} a_i \overset{3}{\equiv} a}&
\end{align}
```

</procedure>
</tab>

<tab title="/= на  5">

Число делится на 5 тогда и только тогда, когда последняя цифра числа делится на 5.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} 5 \Leftrightarrow a_0 \overset{_\operatorname{div}}{=} 5&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&a = a_0 + \sum_{i=1}^{n} a_i \cdot 10^i&\\
&\Rightarrow a_0 + \underset{\overset{_\operatorname{div}}{=} 5
}{\underline{5(2)\cdot\sum_{i=0}^{n-1} a_i \cdot 10^i}} \overset{5}{\equiv} a&\\
&\Leftrightarrow \underline{a_0 \overset{5}{\equiv} a}&
\end{align}
```

</procedure>
</tab>

<tab title="/= на  9">

Число делится на 9 тогда и только тогда, когда сумма его цифр делится на 9.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} 9 \Leftrightarrow \sum_{i=0}^{n} a_i \overset{_\operatorname{div}}{=} 9&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&a = \sum_{i=0}^{n} a_i \cdot 10^i&\\
&\Rightarrow \sum_{i=0}^{n} a_i \cdot (9\times1+1)^i \overset{9}{\equiv} a&\\
&\Leftrightarrow \sum_{i=0}^{n} a_i \cdot 1^i \overset{9}{\equiv} a
\Leftrightarrow \underline{\sum_{i=0}^{n} a_i \overset{9}{\equiv} a}&
\end{align}
```

</procedure>
</tab>

<tab title="/= на  10">

Число делится на 10 тогда и только тогда, когда последняя цифра числа равна 0.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} 10 \Leftrightarrow a_0 = 0&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&a = a_0 + \sum_{i=1}^{n} a_i \cdot 10^i&\\
&\Rightarrow a_0 + \underset{\overset{_\operatorname{div}}{=} 10
}{\underline{10\cdot\sum_{i=0}^{n-1} a_i \cdot 10^i}} \overset{10}{\equiv} a&\\
&\Leftrightarrow a_0 \overset{10}{\equiv} a
\Leftrightarrow \underline{a_0 = 0}&
\end{align}
```

</procedure>
</tab>

<tab title="/= на  11">

Число делится на 11 тогда и только тогда, разность сумм
цифр на четных и нечетных позициях делится на 11.

<procedure>

```tex
\begin{align}
&a \overset{_\operatorname{div}}{=} 11 \Leftrightarrow
\sum_{i=0}^{n} a_i\cdot(-1)^i \overset{_\operatorname{div}}{=} 11&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

```tex
\begin{align}
&a = \sum_{i=0}^{n} a_i \cdot 10^i\Rightarrow \sum_{i=0}^{n} a_i \overset{11}{\equiv} a&\\
&\Leftrightarrow \sum_{i=0}^{\left[\frac{n}{2}\right]} a_{2i} \cdot 10^{2i}+
\sum_{i=0}^{\left[\frac{n+1}{2}\right]} a_{2i+1} \cdot 10^{2i+1} \overset{11}{\equiv} a&\\
&\Leftrightarrow \sum_{i=0}^{\left[\frac{n}{2}\right]} a_{2i} \cdot \underset{=10^2}
{\underline{(9\times11+1)}}^i+
\sum_{i=0}^{\left[\frac{n+1}{2}\right]} a_{2i+1} \cdot \underset{=10^2}{\underline{(9\times11+1)}}
^i\cdot\underset{=10^1}{\underline{(11\times1-1)}} \overset{11}{\equiv} a&\\
&\Leftrightarrow \sum_{i=0}^{\left[\frac{n}{2}\right]} a_{2i} \cdot 1^i+
\sum_{i=0}^{\left[\frac{n+1}{2}\right]} a_{2i+1} \cdot 1^i\cdot(-1) \overset{11}{\equiv} a&\\
&\Leftrightarrow \sum_{i=0}^{\left[\frac{n}{2}\right]} a_{2i}-
\sum_{i=0}^{\left[\frac{n+1}{2}\right]} a_{2i+1} \overset{11}{\equiv} a
\Leftrightarrow \underline{\sum_{i=0}^{n} a_i\cdot(-1)^i \overset{11}{\equiv} a}&
\end{align}
```

</procedure>
</tab>

</tabs>

