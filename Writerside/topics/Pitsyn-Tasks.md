# Задачи Пицына

<emphasis>Сергей Алексеевич Пицын (1998-2023): "очева. умницы"</emphasis>

<tip>
Здесь представлены задачи, которые нам давали на сессии по алгебре.

Это нужно чтобы примерно представить, что там будет на экзамене.
</tip>

## Гроб 1

<procedure title="Условие задачи">

```tex
x=\frac{1}{2}+\frac{1}{3}+\ldots+\frac{1}{n};\ \texttt{Доказать, что:}\ \forall{n}\in\mathbb{N}
\Rightarrow x\notin\mathbb{Z}
```

</procedure>

<procedure title="Решение" collapsible="true">

```tex
\texttt{Пока нету...}
```

</procedure>

## Гроб 2

<procedure title="Условие задачи">

```tex
\begin{align}
&\texttt{let}\,f(x)=\mathrm{P}(k), k\in\mathbb{N}\ _\texttt{(многочлен со степенью k)}&\\
&\texttt{let}\,a_i=f(x), i\in\mathbb{N}&\\
&\texttt{Доказать, что:}\ \not\exists\,f(x):\forall{i}\in\mathbb{N}\Rightarrow a_i\in\mathbb{P}\\
&_\texttt{(множество простых чисел)}
\end{align}
```

</procedure>

## Гроб 3

[wilson_theorem]: https://ru.wikipedia.org/wiki/%D0%A2%D0%B5%D0%BE%D1%80%D0%B5%D0%BC%D0%B0_%D0%92%D0%B8%D0%BB%D1%8C%D1%81%D0%BE%D0%BD%D0%B0

Это расширенная версия [теоремы Вильсона][wilson_theorem]{ignore-vars="true"}.

<procedure title="Условие задачи">

```tex
\begin{align}
&\texttt{let}\,f(x)=(x-1)!\operatorname{mod}x&\\
&\texttt{Чему равен}\,f(x)\,\texttt{при:}&\\
&\texttt{a)}\,?x\in\mathbb{P}&\\
&\texttt{б)}\,?x\in\mathbb{N}\setminus\mathbb{P}&\\
\end{align}
```

</procedure>

<procedure title="Решение" collapsible="true">

```tex
\begin{align}
&\texttt{a)}\,\left[\begin{aligned}
&\texttt{По Т. Вильсона}\Rightarrow(x-1)!\equiv-1\pmod{x}&\\
&\texttt{По свойству модуля:}\,(x-1)!\equiv{x-1}\pmod{x}&
\end{aligned}\right .&\\
&\texttt{б)}\,\left[\begin{aligned}
&\texttt{По Т. Вильсона}\Rightarrow(x-1)!\equiv-1\pmod{x}&\\
&\texttt{По свойству модуля:}\,(x-1)!\equiv{x-1}\pmod{x}&
\end{aligned}\right .&\\
\end{align}
```

</procedure>

## Гроб 4

[mersenne_prime]: https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D0%BB%D0%BE_%D0%9C%D0%B5%D1%80%D1%81%D0%B5%D0%BD%D0%BD%D0%B0
[fermat_prime]: https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D0%BB%D0%BE_%D0%A4%D0%B5%D1%80%D0%BC%D0%B0

Задача, где с одной стороны - [числа Мерсенна][mersenne_prime]{ignore-vars="true"},
а с другой - [числа Ферма][fermat_prime]{ignore-vars="true"}.

<procedure title="Условие задачи">

```tex
\begin{align}
&\texttt{let}\,f(x)=2^x-1&\\
&\texttt{let}\,g(x)=2^x+1&\\
&\texttt{Найти все}\rightarrow\,?x:f(x)\in\mathbb{P}\,\wedge\,g(x)\in\mathbb{P}
\end{align}
```

</procedure>

<procedure title="Решение" collapsible="true">

```tex
\begin{align}
&\texttt{Распишем модули от тройки:}&\\
&\begin{cases}
2^x-1\equiv{r_1}\pmod{3}\\
2^x+1\equiv{r_2}\pmod{3}\\
\end{cases}&\\
&\texttt{Из свойств делимости:}&\\
&\begin{cases}
(-1)^x-1\equiv{r_1}\pmod{3}\\
(-1)^x+1\equiv{r_2}\pmod{3}\\
\end{cases}\Rightarrow_\texttt{(одно из чисел кратно 3)}&\\
&\Rightarrow\left[\,\begin{aligned}
&\begin{cases}
2^x-1=3\\
2^x+1=5
\end{cases}&\\
&\begin{cases}
2^x-1=1\\
2^x+1=3
\end{cases}&\\
\end{aligned}\right .&\\
&\Rightarrow x=2&\\
\end{align}
```

</procedure>

## Гроб 5

Существует ли 5 составных двузначных чисел, взаимно простых между собой?

<procedure title="Условие задачи">

```tex
\begin{align}
&?\,\exists\,\mathbb{X}=\left\{\overline{ab}\in\mathbb{N}\setminus\mathbb{P}\right\}:
|\mathbb{X}|=5,(\mathbb{X}_i,\mathbb{X}_j)=1,\forall{i}\neq{j}&\\
\end{align}
```

</procedure>

<procedure title="Решение" collapsible="true">

```tex
\begin{align}
&\texttt{Выпишем первые 10 простых чисел:}&\\
&\mathbb{P}=\left\{2,3,5,7,11,13,17,19,23,29\right\}&\\
&\texttt{Заметим, что чтобы получить 5 минимальных составных чисел,}&\\
&\texttt{нужно перемножить парами по два числа из}\,\mathbb{P}&\\
&\overset{_\texttt{(по принципу дирихле)}}{\Rightarrow}\,\exists
\,(\mathbb{P}_i,\mathbb{P}_j):\mathbb{P}_i\cdot\mathbb{P}_j\gt100_{\texttt{(противоречие)}}&\\
\end{align}
```

</procedure>