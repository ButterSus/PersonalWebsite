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

При этом вся совокупность воспринимается как единое целое.

<img src="calculus_set.png" alt="Множество" width="200" align="right"/>
</tab>

<tab title="Числовое множество">
Это множество, элементами которого являются числа.
<img src="calculus_set_of_numbers.png" alt="Числовое множество" width="300" align="right"/>
</tab>

</tabs>

<tip>
Множество обычно обозначается заглавными буквами, однако опционально можно использовать
<emphasis>blackboard bold</emphasis> шрифт.

```tex
\begin{align}
&\mathbb{BLACKBOARD\ BOLD}\Rightarrow\mathbb{A}&\\
&DEFAULT\Rightarrow{A}&
\end{align}
```

</tip>

### 1.2. Типы множеств

Общая диаграмма типов множеств:

```mermaid
graph TD
    A[Типы множеств] --> B[Конечное множество]
    A --> C[Бесконечное множество]
    C --> D[Счётное множество]
    C --> E[Несчётное множество]
```

<tabs>
<tab title="Конечные">
В конечном множестве количество элементов <emphasis>конечно</emphasis>. В таком множестве однозначно
можно найти последний и первый элементы.

Например, множество натуральных чисел от 1 до 10.

<procedure>

```tex
\mathbb{A}= \{a_1, a_2, \ldots, a_n\}
```

</procedure>
</tab>
<tab title="Бесконечные">
В бесконечном множестве количество элементов <emphasis>бесконечно</emphasis>. В таком множестве нельзя найти или
последний, или первый элементы.

Например, множество натуральных чисел, так как их бесконечно много.

<procedure>

```tex
\mathbb{A}= \{a_1, a_2, \ldots\}
```

</procedure>
</tab>
<tab title="Счётные">
В счётном множестве можно последовательно перечислять элементы (первый, второй, третий, ...).

<procedure title="Точная формулировка (для ботанов)" collapsible="true">

<emphasis>Счётное множество</emphasis> - множество, в котором можно установить взаимнооднозначное
соответствие (биекция) между элементами этого множества и множества натуральных
чисел. (При биективном отображении каждому элементу одного множества соответствует
ровно один элемент другого множества, при этом определено обратное отображение,
которое обладает тем же свойством.)

```mermaid
graph LR
    A[Элемент множества] -- "(взаимнооднозначное соответствие)" --> B[Натуральное число]
```

</procedure>

<note>

Из стандартных множеств счётными являются:

```tex
\mathbb{N}, \mathbb{Z}, \mathbb{Q}
```

</note>

</tab>
<tab title="Несчётные">
В несчётном множестве нельзя последовательно перечислять элементы (первый, второй, третий, ...).

<procedure title="Точная формулировка (для ботанов)" collapsible="true">

<emphasis>Несчётное множество</emphasis> - множество, которое нельзя упорядочить в
виде последовательности, в которой каждый элемент имеет свой номер.

</procedure>

<note>
Из стандартных множеств несчётными являются:

```tex
\mathbb{R}, \mathbb{C}
```

</note>
</tab>
</tabs>

### 1.3. Стандартные множества

Здесь представлены лишь самые базовые множества, которые вам понадобятся на экзамене.

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

<tip>
Иногда мы используем следующие множества:

```tex
\begin{align}
&\varnothing=\{\}& \texttt{(пустое множество)} \\
&\mathbb{P}=\{2, 3, 5, 7, 11, \ldots\} & \texttt{(множество простых чисел)} \\
&\mathbb{N}\setminus\mathbb{P}\setminus\{1\}=\{4, 6, 8, 9, 10, \ldots\} & \texttt{(множество составных чисел)}
\end{align}
```

</tip>

### 1.4.0. Универсальное множество

<emphasis>Универсальное множество</emphasis> — это множество, содержащее все объекты и все множества.

Обычно универсальное множество обозначается буквой `U` и нужен лишь для того, чтобы убрать из любого множества
ненужные элементы.

<procedure>

```tex
\mathbb{U}\supseteq\mathbb{A}, \forall\mathbb{A}_\texttt{(универсальное множество содержит все множества)}
```

</procedure>


<tip>

Таким образом, универсальное множество мы например можем использовать следующим образом:

```tex
\begin{align}
&\mathbb{A}=\{1, 2, 3, 4, 5\}& \\
&\mathbb{B}=\{2, 4, 6, 8, 10\}& \\
&\mathbb{A}\setminus\mathbb{B}=\mathbb{A}\cup\overline{\mathbb{B}}
=\mathbb{A}\cup\left(\mathbb{U}\setminus\mathbb{B}\right)=\{1, 3, 5\}&
\end{align}
```

</tip>

### 1.4.1. Операции над множествами

<tabs>
    <tab title="Дополнение">
         <procedure>
        <code-block lang="tex">$\forall A:\overline{A}=\mathbb{U}\setminus{A}=
         \{x \mid x \in \mathbb{U} \wedge x \notin A\}</code-block>
        <img src="calculus_complement.png" alt="Дополнение" width="200" align="right"/>
         </procedure>
        <tip>
        <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\neg}</code-block>
        </tip>
    </tab>
    <tab title="Объединение">
         <procedure>
        <code-block lang="tex">$\forall A, B: A \cup B=\{x \mid x \in A \vee x \in B\}</code-block>
        <img src="calculus_union.png" alt="Объединение" width="200" align="right"/>
         </procedure>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\cup}</code-block>
        </tip>
    </tab>
    <tab title="Пересечение">
         <procedure>
        <code-block lang="tex">$\forall A, B: A \cap B=\{x \mid x \in A \wedge x \in B\}</code-block>
        <img src="calculus_intersection.png" alt="Пересечение" width="200" align="right"/>
         </procedure>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\cap}</code-block>
        </tip>
    </tab>
    <tab title="Разность">
         <procedure>
        <code-block lang="tex">$\forall A, B: A \setminus B=\{x \mid x \in A \wedge x \notin B\}</code-block>
        <img src="calculus_difference.png" alt="Разность" width="200" align="right"/>
         </procedure>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\setminus}</code-block>
        </tip>
    </tab>
    <tab title="Симметрическая разность">
         <procedure>
        <code-block lang="tex">$\forall A, B: A \triangle B=(A \setminus B) \cup(B \setminus A)</code-block>
        <img src="calculus_symmetric_difference.png" alt="Симметрическая разность" width="200" align="right"/>
         </procedure>
        <tip>
            <code-block lang="tex">$\texttt{Математическая запись:}\,\Large\pmb{\triangle}</code-block>
        </tip>
    </tab>
</tabs>

### 1.5. Подмножество

Одно множество может содержать все элементы другого множества.
Такое множество называется <emphasis>подмножеством</emphasis>.

<procedure>
<img src="calculus_subset.png" alt="Подмножество" width="200" align="right"/>

В данном случае `A` является подмножеством `B`:

```tex
A \subseteq B \Leftrightarrow \forall x \in A \Rightarrow x \in B \Leftrightarrow A \cap B = A
```
</procedure>

<note>
Так например, множество всех натуральных чисел является подмножеством множества всех целых чисел.

```tex
\mathbb{N} \subseteq \mathbb{Z}
```

А универсальное множество является подмножеством любого множества.

```tex
\mathbb{U} \subseteq \mathbb{A},\forall \mathbb{A}
```
</note>

### 1.6. Декартово произведение

<emphasis>Декартово произведение</emphasis> — это множество всех упорядоченных пар элементов двух множеств.

<procedure>

```tex
\begin{align}
&\texttt{let}\,A, B\,\texttt{— множества}& \\
&A \times B = \{(a, b) \mid a \in A, b \in B\}&
\end{align}
```

</procedure>

<tip>
Например, декартово произведение множеств `A` и `B`:

```tex
\begin{align}
&A = \{1, 2\}, B = \{3, 4\}& \\
&A \times B = \{(1, 3), (1, 4), (2, 3), (2, 4)\}&
\end{align}
```
</tip>

### 1.7. Мощность множества

<emphasis>Мощность множества</emphasis> — это количество элементов в множестве.

<procedure>

```tex
\begin{align}
&\texttt{let}\,A=\{-1,2,-3,4,-5\}\ \texttt{- множество}& \\
&\left|A\right|=5\ \texttt{- мощность множества}&\\
&\left|\varnothing\right|=0\ \texttt{- мощность пустого множества}&
\end{align}
```

</procedure>

Не всегда мощность множества конечна, например, мощность множества натуральных чисел выражается дичью.

<tabs>
<tab title="Обязательный материал">
Два множества называются <emphasis>равномощными</emphasis>,
если между ними существует взаимнооднозначное соответствие (биекция).

```mermaid
flowchart LR
   subgraph A["`**Множество A**`"]
      direction TB
      A1(1)
      A2(2)
      A3(3)
      A4(4)
   end
   
   subgraph B["`**Множество B**`"]
      direction TB
      B1(a)
      B2(b)
      B3(c)
      B4(d)
   end

   A1 -- "(биекция)" --> B1
   A2 --> B2
   A3 --> B3
   A4 --> B4
   
   style B fill: #B59C72  ,stroke-width:2px
   style A fill: #547465  ,stroke-width:2px
```

Иными словами, можно выразить следующее:

<procedure>

```tex
|A|=|B| \Leftrightarrow \exists f(x):B=\{f(x)\mid x \in A\}
```

Функция `f(x)` не обязательно должна быть задана математической формулой, например
множество простых чисел и множество нечётных чисел равномощны, но хоть `f(x)` в таком случае
сложно задать, достаточно доказать что она существует.

</procedure>
</tab>
<tab title="Углубленный материал">

**Бесконечные множества**:

Для обозначения мощности бесконечных множеств используют символ <shortcut>aleph</shortcut>,
причём чем больше мощность множества, тем больше индекс у символа.

<procedure>

```tex
\left|\mathbb{N}\right|=\aleph_0
```

</procedure>

Мощности бесконечных множеств - целый отдельный раздел в теории множеств,
но могу сказать в общих словах:

<procedure>

Для мощностей, как и в случае конечных множеств, имеются понятия: `равенство`, `больше`, `меньше`.
То есть для любых множеств `A` и `B` возможно только одно из трёх:
1. `|A| = |B|`, то они равномощны.
2. `|A| < |B|`, то B мощнее A -> в этом случае B содержит подмножество, равномощное A, но A и B не равномощны.
3. `|A| > |B|`, то A мощнее B -> в этом случае A содержит подмножество, равномощное B, но A и B не равномощны.
4. Ситуации, в которой A и B не равномощны и при этом ни в одном из них нет части, равномощной другому,
невозможна по теореме Цермело.
5. Ситуации, в которой `|A| > |B|` и `|B| > |A|` невозможна по теореме Кантора-Бернштейна.

</procedure>

И очень частным случаем является мощность множества действительных чисел:

```tex
\left|\mathbb{R}\right|=\mathfrak c=2^{\aleph_0}>\aleph_0
```

В этом случае `c` - мощность континуума.
</tab>
</tabs>

### 1.8.0. Термины свойств

[inclusion-exclusion-principle]: https://ru.wikipedia.org/wiki/%D0%A4%D0%BE%D1%80%D0%BC%D1%83%D0%BB%D0%B0_%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B8%D1%81%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9#%D0%94%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D1%82%D0%B2%D0%BE

<note>

Этот материал на сессии вряд-ли понадобится, но я решил добавить его
для полноты картины. Мне показалось это нужным когда я читал
[эту статью][inclusion-exclusion-principle]{ignore-vars="true"}.

</note>

<procedure>

<emphasis>Свойство</emphasis> — это утверждение, которое либо верно, либо неверно для каждого элемента множества.

</procedure>

Формула включения исключения в обычной формулировке несёт смысл, только
если мы оперируем с конечным множеством чисел.

Однако на практических задачах (например по физике) часто даются конкретные величины,
которые невозможно перечислить как множество.

В таком случае мы абстрагируемся от множеств и переходим на свойства, где:

<procedure>

```tex
\begin{align}
&N(a_1)\in\mathbb{R} - \texttt{величина, удовлетворяющая свойству 1}&\\
&N(a_1a_2)\in\mathbb{R} - \texttt{величина, удовлетворяющая свойству 1 и 2}&\\
&N(\overline{a_1a_2})\in\mathbb{R} - \texttt{величина, не удовлетворяющая одному из свойств 1 и 2}&\\
&N(a_1+a_2)\in\mathbb{R} - \texttt{величина, удовлетворяющая свойству 1 или 2}&\\
\end{align}
```

</procedure>

Как могли заметить, принято:
- **свойства** - строчными буквами, вычисления в основном с величинами
- **множества** - заглавными буквами, вычисления в основном с элементами

<tip>

**Ещё раз поясню главную мысль:**

Свойства мы используем если работаем с _величинами_, которые невозможно перечислить как множество.
Это просто удобнее и логичнее.

</tip>

[boolean-algebra]: https://ru.wikipedia.org/wiki/%D0%91%D1%83%D0%BB%D0%B5%D0%B2%D0%B0_%D0%B0%D0%BB%D0%B3%D0%B5%D0%B1%D1%80%D0%B0

Подробнее про булеву алгебру со свойствами можно почитать в [этой статье][boolean-algebra]{ignore-vars="true"}.


### 1.8.1 Основная формула включений и исключений

Запомните формулу включений и исключений, она пригодится вам на экзамене.
Формулировка в терминах множеств:

<procedure>

```tex
\left|\bigcup_{i=1}^{n}A_i\right|=\sum^n_{i=1}\left|A_i\right|-\sum^n_{i\lt j}\left|A_{ij}\right|+\sum^n_{i\lt j\lt k}\left|A_{ijk}\right|-\ldots
+\left(-1\right)^n\sum^n_{i\ldots}\left|A_{i\ldots}\right|
```

</procedure>

Есть ещё формулировка в терминах свойств:

<procedure>

```tex
N(a_1+a_2\ldots+a_n)=\sum^n_{i=1}N(a_i)-\sum^n_{i\lt j}N(a_ia_j)+\sum^n_{i\lt j\lt k}N(a_ia_ja_k)-\ldots
```

</procedure>

Вот примеры задач которые можно решить с помощью этой формулы:

<procedure>

Найти количество чисел от 1 до 1000, которые делятся на 2, 3 или 5.

```tex
\begin{align}
&\begin{aligned}
&\texttt{let}\,A_1=\{2, 4, 6, \ldots, 1000\}&\Rightarrow\left|A_1\right|=\frac{1000}{2}=500&\\
&\texttt{let}\,A_2=\{3, 6, 9, \ldots, 999\}&\Rightarrow\left|A_2\right|=\frac{999}{3}=333&\\
&\texttt{let}\,A_3=\{5, 10, 15, \ldots, 1000\}&\Rightarrow\left|A_3\right|=\frac{1000}{5}=200&\\
\end{aligned}&\\
&\left[\begin{aligned}
&\begin{array}{ll}
\left|A_1\cap A_2\right|=\frac{1000}{6}=166\\
\left|A_1\cap A_3\right|=\frac{1000}{10}=100
\end{array}\ \ \ 
\begin{array}{ll}
\left|A_2\cap A_3\right|=\frac{1000}{15}=66\\
\left|A_1\cap A_2\cap A_3\right|=\frac{1000}{30}=33
\end{array}&
\end{aligned}\right]&\\
&\left|A_1\cup A_2\cup A_3\right|=\left(\begin{aligned}
&+\left|A_1\right|+\left|A_2\right|+\left|A_3\right|&\\
&-\left|A_1\cap A_2\right|-\left|A_1\cap A_3\right|-\left|A_2\cap A_3\right|&\\
&+\left|A_1\cap A_2\cap A_3\right|&
\end{aligned}\right)&\\
&\Rightarrow\left|A_1\cup A_2\cup A_3\right|=500+333+200-166-100-66+33=734&
\end{align}
```

</procedure>

<procedure>

Найти количество чисел от 1 до 1000, которые не делятся на ни на 2, ни на 3, ни на 5.

```tex
\begin{align}
&\texttt{Тут всё решается аналогично предыдущему}&\\
&\left|A_1\cup A_2\cup A_3\right|=\ldots=734&\\
&\Rightarrow \left|{\overline{A_1}\cap \overline{A_2}\cap \overline{A_3}}\right|=1000-734=266&
\end{align}
```

</procedure>

<procedure title="Доказательство" collapsible="true">

**`Частный случай с кругами Эйлера`**

<img src="calculus_euler_circles.png" alt="Круги Эйлера" width="400" align="right"/>

В данном случае мы можем воспользоваться кругами Эйлера, чтобы наглядно понять и выразить
формулу включений и исключений.

```tex
\left|A_1\cup A_2\cup A_3\right|=\left(\begin{aligned}
&+\left|A_1\right|+\left|A_2\right|+\left|A_3\right|&\\
&-\left|A_1\cap A_2\right|-\left|A_1\cap A_3\right|-\left|A_2\cap A_3\right|&\\
&+\left|A_1\cap A_2\cap A_3\right|&
\end{aligned}\right)
```

</procedure>

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