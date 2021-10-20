---
layout: page
title: §6. Идемпотентные аналоги теорем о неотрицательных матрицах
---



<ul style="list-style-type: none; margin-top: 20px">
<li> <a href="#sec6-1">6.1 Модель баланса знаний Канторовича–Макарова</a> </li>
<li> <a href="#sec6-2">6.2 Арбитражные цепочки на валютном рынке</a> </li>
<li> <a href="#sec6-3">6.3 Экономические индексы</a> </li>
</ul>

Введем вместо сложения и умножения две новые операции:

$$\begin{align}
a \oplus b & := \max(a, b) \\
a \odot b & := a\cdot b
\end{align}$$

Перечислим некоторые свойства.

* $$a \oplus b = b \oplus a$$ $$ $$

* $$(a \oplus b) \oplus c = a \oplus (b \oplus c)$$ $$ $$

* $$(a \oplus b) \odot c = a \odot c \oplus b \odot c$$ $$ $$

*получаем полукольцо*

* но нет обратной операции, т.е. $$a \oplus x = a$$ $$\Rightarrow$$ $$x \leq a$$

* к тому же, есть свойство *идемпотентности*: $$a \oplus a = a$$



<h2 id="sec6-1">6.1 Модель баланса знаний Канторовича–Макарова</h2>

По аналогии с моделью Леонтьева, рассматривающую ресурсы, можно рассмотреть модель, рассматривающую *знания*. В отличие от ограниченных ресурсов, знания будут *неограниченными*.

Пусть $$1, \dots, n$$ — направления исследований. Тогда получаем ограничение: 

$$a_{ij}x_j \leq x_i \quad(i,j = 1, \dots, n),$$

где $$x_i$$ — знания в $$i$$-м направлении, $$a_{ij}x_j$$ — интенсивность исследований (объём работ) в $$j$$-м направлении, $$x_1, \dots, x_n > 0$$

Составим матрицу $$A = \|a_{ij}\|_{i,j=1}^n > 0$$. Она характеризует междисциплинарные связи.

$$\max_{j=1,\dots,n} a_{ij}x_j \leq x_i \quad (i=1,\dots,n)$$

$$\Updownarrow$$

$$A^\oplus \vec x \leq x,\ \vec x > 0$$

<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение 6.</b> Будем говорить, что матрица  \(A = \|a_{ij}\|_{i,j=1}^n > 0\) является <u>продуктивной в идемпотентном смысле</u>, если \(\exists x_1, \dots, x_n > 0:\)

$$\max_{1 \leq j \leq n} a_{ij} x_j \leq x_i \quad (\forall i = 1, \dots, n),$$

т.е. \(A^\oplus \vec x \leq \vec x\), \(\vec x > 0\)

</div>



<h2 id="sec6-2">6.2 Арбитражные цепочки на валютном рынке</h2>

Пусть $$1, \dots, n$$ — виды валют, $$a_{ij}$$ — количество валюты $$j$$, которое можно получить за единицу валюты $$i$$. Тогда матрицу

$$A = \|a_{ij}\|_{i,j=1}^n > 0$$

назовем *матрицей кросс-курсов*. *Арбитражной цепочкой* назовем такую цепочку валютных обменов, которая даёт прибыль. Возникает вопрос о существовании в матрице арбитражных цепочек.

<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение 7.</b> Будем говорить, что матрица \(A = \|a_{ij}\|_{i,j=1}^n > 0\) <u>допускает арбитражную цепочку</u> \((i_1, i_2, \dots, i_t)\), если 

$$a_{i_1i_2}a_{i_2i_3} \dots a_{i_{t-1}i_t}a_{i_ti_1} > 1$$

</div>

<div style="border-left: 5px solid MediumPurple; padding: 10px 20px; margin: 20px 0">

<b>Задача 1.</b> По матрице \(A\) определить, есть ли у неё арбитражные цепочки. Если есть, то найти одну из них.

</div>

Возможное число таких цепочек: 

$$\sum_{t=2}^n C_n^t t1$$

$$\Rightarrow$$ эффективный алгоритм работает за $$n^3$$ операций.

Пусть $$\rho$$ — комиссия за обмен. Тогда $$\dfrac{a_{ij}}{\rho}$$ — получаемые в итоге обмена $$i \to j$$ средства. Следовательно, условие  отсутствия арбитражных цепочек: $$\forall (i_1, \dots, i_t)$$

$$a_{i_1i_2}a_{i_2i_3} \dots a_{i_{t-1}i_t}a_{i_ti_1} \leq \rho^t$$

<div style="border-left: 5px solid MediumPurple; padding: 10px 20px; margin: 20px 0">

<b>Задача 2.</b> Найти \(\min \rho\), при котором не существует арбитражных цепочек. Такая задача решалась при создании единой валюты для Евросоюза.

</div>

$$A = ||a_{ij}||_{i,j=1}^n > 0$$

$$x_i > 0$$ — количество евро за единицу $$i$$-й валюты. Таким образом, нужно, чтобы 

$$a_{ij}x_j \leq x_i \quad (i,j = 1, \dots, n)$$

$$\Updownarrow$$

$$\max_{1 \leq j \leq n} a_{ij}x_j \leq x_i \quad (1 = 1, \dots, n)$$



<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<p><b>Теорема Африата–Вериана</b></p>

Пусть \(A = \|a_{ij}\|_{i,j=1}^n > 0\). Тогда матрица \(A\) продуктивна в идемпотентном смысле \(\Leftrightarrow\) у матрицы \(A\) нет арбитражных цепочек.

</div>

<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">

<ol>
<li>
<i>Необходимость.</i> Возьмём произвольный набор индексов \(i_1, \dots, i_t\). Матрица \(A\) продуктивна в идемпотентном смысле \(\Leftrightarrow\) \(\exists x_1>0, \dots, x_n>0:\)

$$a_{ij}x_j \leq x_i \quad (i,j = 1, \dots, n)$$

Отсюда, в частности

$$a_{i_1i_2} \leq x_{i_1}, a_{i_2i_3}x_{i_3} \leq x_{i_2}, \dots, a_{i_{t-1}i_t}x_{i_t} \leq x_{i_{t-1}}, a_{i_ti_1}x_{i_1} \leq x_{i_t}$$

Перемножим неравенства выше и получим

$$(a_{i_1i_2} a_{i_2i_3} \dots a_{i_{t-1}i_t} a_{i_ti_1}) \prod_{k=1}^t x_{i_k} \leq \prod_{k=1}^t x_{i_k},$$

откуда получаем

$$a_{i_1i_2} a_{i_2i_3} \dots a_{i_{t-1}i_t} a_{i_ti_1} \leq 1$$
</li> <br>

<li>
<i>Достаточность.</i> Здесь нужно доказать, что существует решение системы

$$\begin{align}
a_{ij}x_j \leq x_i, & & i,j=1,\dots,n \\
x_i > 0, & & i=1,\dots,n
\end{align}$$

Для \(A=\|a_{ij}\|_{i,j=1}^n>0\) построим \(\hat A=\|\hat a_{ij}\|_{i,j=1}^n>0\) т.ч.

$$\hat a_{ij} = \sup_{k_1, \dots, k_{t-1}} \{ a_{ik_1} a_{k_1k_2} \dots a_{k_{t-1}j}\ |\ t \geq 1\}$$

<i>Замечание.</i> Арбитражные цепочки есть \(\Leftrightarrow\) \(\hat a_{ij}=\infty\), арбитражных цепочек нет \(\Leftrightarrow\) \(\hat a_{ij}<1\).

Положим \(x_i := \max_j \hat a_{ij} > 0\). Такие \(x_i\) будут удовлетворять исходной системе неравенств.

$$x_i = \sup_t \{ a_{ik_1} a_{k_1k_2} \dots a_{k_{t-1}m} \} \geq$$

$$\geq a_{ij} \sup_t \{ a_{jk_2} \dots a_{k_{t-1}k_t} \} = a_{ij}x_j$$
</li> <br>
</ol>
◼︎
</div>
</div>


*Замечание.* Вычислим ряд

$$\hat A = A \oplus {A^\oplus}^2 \oplus \dots \oplus {A^\oplus}^n \oplus \dots$$

Если не существует арбитражных цепочек, то сумма ряда стабилизируется после $n$-го элемента, т.е. ряд сходится. 


Число

$$\min \{ \rho\ |\ A^\oplus\vec x \leq \rho \vec x, \vec x > 0 \}$$

назовем *идемпотентным числом Фробениуса–Перрона*





<h2 id="sec6-3">6.3 Экономические индексы</h2>

Считаем отношение величины в текущем периоде к некоторому базовому периоду.

Пусть $$t$$ — базовый период времени, $$\vec p(t) = (p_1(t), \dots, p_m(t))$$ — вектор цен на $$m$$ товаров (в период времени $$t$$), $$\tau$$ — текущий период времени, $$\vec p(\tau) = \dots$$ —  вектор цен в период времени $$\tau$$.

Как строятся индексы? Выбираем некоторую корзину товаров, $$\vec w = (w_1, \dots, w_m)$$ — структура потребительской корзины.

$$\frac{\vec p(\tau) \cdot \vec w}{\vec p(t) \cdot \vec w} \text{ — индекс цен}$$

Аналогична ситуация с объемами потребления — они меняются со временем. Зафиксируем некоторую базовую структуру цен. 

$$\vec w = (X_1(t), \dots, X_m(t)) \text{ — вектор объемов потребления в базовый период времени}$$

$$\frac{\vec p(\tau) \vec X(t)}{\vec p(t) \vec X(t)} \text{ — индекс потребительских цен Ласпейреса}$$

Этот индекс используется потребительскими службами в мире. Если выбрать потребление не в базовый период времени, а в текущий:

$$\frac{\vec p(\tau) \vec X(\tau)}{\vec p(t) \vec X(\tau)} \text{ — индекс потребительских цен Пааше}$$

Эффект Гершенкрона: 

$$\frac{\vec p(\tau) \vec X(\tau)}{\vec p(t) \vec X(\tau)} \overset{\leq}{\underset{>}{?}} \frac{\vec p(\tau) \vec X(t)}{\vec p(t) \vec X(t)} $$



В 1905 г. В. Парето предположил, что потребление товаров домашними хозяйствами может быть описано некоторой моделью.

$$\vec p(\vec X) \text{ — обратные функции спроса}$$

$$F(\vec X) \text{ — функция полезности — описывает ценность потребительского набора } \vec X$$

Можно рассматривать задачу:

$$\begin{cases}
    F(\vec X) \to \max \\
    \vec p\cdot\vec X \leq I \\
    \vec X \geq 0
\end{cases}$$

— задача о рациональном потребителе. 

### Обратная задача о рациональном поведении потребителя. Индексы Конюса-Дивизиа

Потребуем, чтобы

<p id="eq-mp1">
$$\vec X \in \arg\max \{ F(\vec Y) | \vec p(\vec X)\cdot \vec Y \leq \vec p(\vec X)\cdot \vec X, \vec y \geq 0 \} \tag{MP-1}$$
</p>

### Априорные требования к индексу $$F(\vec X)$$

1. Функция должна быть непрерывной: $$F(\vec X) \in C(\mathbb{R}_+^m)$$


2. $$F(\vec X) \geq 0$$ $$\forall \vec X \geq 0$$, $$\exists \hat{\vec X} \geq 0:$$ $$F(\hat{\vec X}) > 0$$


3. $$\forall \vec X \geq 0$$, $$\forall \lambda > 0$$ $$F(\lambda \vec X) = \lambda F(\vec X)$$


4. Вогнутость функции $$F(\vec X)$$ на $$\mathbb{R}_+^m:$$ $$\forall \vec Y, \vec Z \in \mathbb{R}_+^m$$ $$\hookrightarrow$$ $$F(\vec Y + \vec Z) \geq F(\vec Y) + f(\vec Z)$$



Свойство 4 эквивалентно: $$F(\lambda\vec Y + (1-\lambda)\vec Z) \geq \lambda F(\vec Y) + (1-\lambda)F(\vec Z)$$. Будем говорить, что если выполняются свойства 1–4, то $$F(\vec X) \in \Phi$$.

Воспользуемся теоремой Куна-Такера для задачи (<a href="#eq-mp1">MP-1</a>). Функция Лагранжа

$$L(\vec Y, \lambda) = F(\vec Y) + \lambda (\vec p(\vec X)\cdot\vec X - \vec p(\vec X)\cdot\vec Y)$$

Задача монотонная, следовательно в точке максимума в ограничении будет достигаться равенство. Условие экстремума:

$$0 \in \left.\partial_{\vec Y} L(\vec Y, \lambda)\right|_{\vec Y = \vec X}$$

По теореме Моро-Рокафеллара

$$0 \in \partial F(\vec X) - \lambda \vec p(\vec X)\quad \Leftrightarrow\quad \lambda \vec p(\vec X) \in \partial F(\vec X)$$

Рассмотрим функцию 

$$F(\vec Y) - \lambda \vec p(\vec X)\cdot\vec Y \to \max_{\vec Y \geq 0} \tag{MP-2}$$

Чтобы максимум достигался в точке $\vec X$, должны выполняться условия:

$$F(\vec X) - \lambda\vec p(\vec X)\cdot\vec X = 0 \\ \forall \vec Y \geq 0\hookrightarrow F(\vec Y) - \lambda p(X)\cdot Y \leq 0 \tag{MP-3}$$

Будем искать

$$\inf_{\{\vec X \geq 0 | F(\vec X) > 0\}} \frac{\vec p\cdot \vec X}{F(\vec X)} = q(\vec p) \text{ — преобразование Янга}$$

Обсудим свойства этого преобразования. 

<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема.</b> Если \(F(\vec X) \in \Phi\), то 

$$q(\vec p) = \inf \left\lbrace \left. \frac{\vec p \vec X}{F(\vec X)}\ \right|\ \vec X\geq 0, F(\vec X) > 0 \right\rbrace \in \Phi$$
и
$$F(\vec X) = \inf \left\lbrace \left. \frac{\vec p \vec X}{q(\vec p)}\ \right|\ \vec p\geq 0, q(\vec p) > 0 \right\rbrace$$

</div>

*Обсуждение.* Свойство 2 $$\Leftrightarrow$$ $$p_j(\vec X) = q(\vec p(\vec X))\cdot \dfrac{\partial F(\vec X)}{\partial X_j}\quad j=1,\dots,m$$

$$ q(\vec p(\vec X)) dF(\vec X) = \sum_{j=1}^m p_j(\vec X)dX_j $$

— основная формула теории экономических индексов.

Согласно свойству 3, если взять $$\lambda = \dfrac{1}{q(p)}$$, то $$\forall \vec Y \geq 0$$ $$F(Y) - \lambda p(X)\cdot Y \leq 0$$

$$\forall p \geq 0, \forall X \geq 0 \hookrightarrow q(\vec p)F(\vec X) \leq \vec p\vec X$$

Теперь докажем теорему.


<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">

\(\forall \vec p \geq 0$, $\forall \vec X \geq 0\)

$$\vec p\vec X \geq q(\vec p)\cdot F(\vec X)$$

Свойство положительной однородности: \(\forall \lambda > 0\), \(\forall \vec p \geq 0\)

$$q(\lambda\vec p) = \inf_{\vec X \geq 0, F(\vec X) > 0} \frac{\lambda\vec p\vec X}{F(\vec X)} = \lambda\inf_{\vec X \geq 0, F(\vec X) > 0} \frac{\vec p\vec X}{F(\vec X)} = \lambda q(\vec p)$$

Свойство выпуклости: \(\forall \vec p \geq 0\), \(\forall \tilde{\vec p} \geq 0\)

$$q(\vec p + \tilde{\vec p}) = \inf_{\vec X \geq 0, F(\vec X) > 0} \frac{(\vec p + \tilde{\vec p})\vec X}{F(\vec X)} = \inf_{\vec X \geq 0, F(\vec X) > 0} \left(\frac{\vec p\vec X}{F(\vec X)} + \frac{\tilde{\vec p}\vec X}{F(\vec X)} \right) \geq \inf_{\vec X \geq 0, F(\vec X) > 0} \frac{\vec p\vec X}{F(\vec X)} + \inf_{\vec X \geq 0, F(\vec X) > 0} \frac{\tilde{\vec p}\vec X}{F(\vec X)} = q(\vec p) + q(\tilde{\vec p})$$

Вернемся ко второму свойству. Рассмотрим множество \(\Gamma_F = {(\vec X, t)\ |\ \vec X \geq 0, t \leq F(\vec X)}\) — подграфик функции \(F(\vec X)\). Это множество — выпуклый конус. 

\((\hat{\vec X}, F(\hat{\vec X})) \in \partial\Gamma_F\), \(\hat{\vec X} > 0\). Рассмотрим опорную гиперплоскость в этой точке. Она должна проходить через \(0\). По теореме отделимости существует опормая гиперплоскость \((\vec p, \alpha) \neq 0\) т.ч.

$$\vec p \hat{\vec X} + \alpha F(\hat{\vec X}) = 0$$

и

$$\forall \vec X \geq 0 \forall t \leq F(\vec X) \hookrightarrow \vec p\vec X + \alpha t \geq 0$$

Что можно сказать про \(\alpha\)? Из неравенства выше следует, что \(\alpha \leq 0\). С другой стороны \(\alpha \neq 0\). Рассмотрим вектор 

$$\hat{\vec p} = \frac{1}{|\alpha|}\vec p$$

Получаем, что \(\hat{\vec p}\cdot\vec X - F(\vec X) \geq 0\)

$$F(\vec X) > 0\ \rightarrow\ \frac{\hat{\vec p}\cdot\vec X}{F(\vec X)} \geq 1$$

$$q(\hat{\vec p}) = \inf_{\vec X \geq 0, F(\vec X) > 0} \frac{\hat{\vec p}\cdot\vec X}{F(\vec X)} \geq 1$$

Покажем, в любой точке \(\tilde{\vec p} \in \partial\mathbb{R}_+^m\), есть полунепрерывность сверху.

$$\vec p_k \to \tilde{\vec p}, k \to +\infty$$

$$q(\vec p_k) = \inf_{\dots} \frac{\vec p_k\cdot\vec X}{F(\vec X)}$$

Пусть \(\tilde{\vec X} \geq 0\), \(F(\tilde{\vec X}) > 0\)

$$\underset{k\to+\infty}{\overline\lim} q(\vec p_k) \leq \frac{\tilde{\vec p}\tilde{\vec X}}{F(\tilde{\vec X})}$$

Отсюда получаем, что

$$\underset{k\to+\infty}{\overline\lim} q(\vec p_k) \leq q(\tilde{\vec p})$$

Следовательно, \(q(\vec p)\) полунепрерывна сверху в т. \(\tilde{\vec p}\). Покажем полунепрерывность снизу. Рассмотрим базисные векторы \(\vec e_j\)

Пусть \(\vec p_k \in \text{cone} \{ \tilde{\vec p}, \vec e_{j_t}\ |\ t = 1, \dots, m-1 \}\). Тогда каждый такой вектор \(\vec p_k\) можно разложить по базису \(\{ \vec e_{j_t} \}\) с неотрицательными коэффициентами:

$$\vec p_k = \alpha_0(p_k) \tilde{p} + \sum_{t=1}^m \alpha_{j_t} (p_k) \vec e_{j_t}$$

$$\lim_{k\to+\infty} \alpha_0(p_k) = 1,\ \lim_{k\to+\infty} \alpha_{j_t}(p_k) = 0,\ t=1,\dots,m$$

$$q(p_k) \geq \alpha_0(p_k) q(\tilde{p}) + \sum_{t=1}^m \alpha_{j_t} (p_k) q(\vec e_{j_t})$$

Перейдем к пределу

$$\underset{k\to+\infty}{\underline\lim} q(p_k) \geq q(\tilde{t})$$

Докажем <i>инволютивность</i> преобразования: \(\forall \vec p \geq 0\) \(\forall \vec X \geq 0\)

$$pX \geq q(p)F(x)$$

$$\inf_{\vec p\geq 0, q(\vec p) > 0} \frac{\vec p\vec X}{q(\vec p)} \geq F(\vec X)$$

Обозначим \(G(\vec X) = \inf_{\vec p\geq 0, q(\vec p) > 0} \dfrac{\vec p\vec X}{q(\vec p)}\) и покажем, что \(G(X) = F(X)\). Допустим противное, что \(\exists \hat{\vec X} > 0\) т.ч. \(G(\hat{\vec X}) > F(\hat{\vec X})\). Рассмотрим

$$\Gamma_F = \{ (\vec X, t) | \vec X \geq 0, t \leq F(\vec X) \} \text{ — выпуклый конус}$$

$$(\hat{\vec X}, G(\hat{\vec X})) \notin \Gamma_F$$

Следовательно эту точку можно строго отделить от конуса гиперплоскостью: по теореме отделимости \(\exists (\vec p, \alpha) \neq 0:\) \(\forall \vec X \geq 0, t \leq F(\vec X)\)

$$\vec p\cdot \vec X + \alpha\cdot t \geq 0, \alpha \leq 0, \alpha \neq 0$$

$$\vec p\cdot \hat{\vec X} + \alpha\cdot G(\hat{\vec X}) < 0 $$

Положим \(\hat{\vec p} = \dfrac{1}{|\alpha|} \vec p\). Тогда \(\forall \vec X \geq 0\)

$$\hat{\vec p}\cdot \vec X - F(\vec X) \geq 0\ \Rightarrow\ q(\hat{\vec p}) = \inf_{X \geq 0, F(X) > 0} \frac{\hat{p}X}{F(\vec X)} \geq 1$$

$$\hat{\vec p}\cdot \hat{\vec X} < G(\hat{\vec X})$$

$$\hat{\vec p}\cdot \hat{\vec X} < G(\hat{\vec X}) q(\hat{\vec p})$$

Следовательно, \(\forall \vec x\)

$$G(\vec X)\cdot q(\vec p) \leq \vec p\cdot\vec X$$

Получили противоречие ◼︎
</div>
</div>


