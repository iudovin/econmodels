---
layout: page
title: §5. Устойчивые матрицы
---



<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение 4.</b> Будем называть матрицу \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\) является <u>устойчивой</u>, если \(\exists k \geq 1:$ $A^k > 0\)

</div>

Рассмотрим $$\rho > 0$$

$$\frac{1}{\rho^t} A^t \overset{t \to \infty}\longrightarrow ?$$

$$\underset{t\to\infty}\lim \frac{1}{\rho^t}A^t = 
\begin{cases}
O, & \rho > \lambda(A) \\
\not\exists, & \rho < \lambda(A)
\end{cases}$$

Нас интересует случай $$\rho = \lambda(A)$$

$$\underset{t\to\infty}\lim \frac{1}{(\lambda(A))^t}A^t = ?$$



<div style="border-left: 5px solid MediumPurple; padding: 10px 20px; margin: 20px 0">

<b>Пример.</b> Рассмотрим \(A = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}\). Её характеристическое уравнение: \(\lambda^2-1=0\). Отсюда \(\lambda(A) = 1\), \(A^2 = \begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}\) \(\Rightarrow\) \(A^{2k} = E\), \(A^{2k+1} = A\)

</div>



<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<p><b>Теорема 5.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\) неразложимая матрица. Тогда: </p>

<ol>
<li> Для того, чтобы существовал предел 
<p id="eq5-1">
$$\underset{t\to\infty}\lim \frac{1}{(\lambda(A))^t}A^t = B \tag{5.1}$$
</p>
необходимо и достаточно, чтобы матрица \(A\) была устойчивой </li> <br>


<li> Если предел (<a href="#eq5-1">5.1</a>) существует, то каждый столбец матрицы \(B\) является вектором Фробениуса-Перрона матрицы \(A\), а каждая строка матрицы \(B\) является вектором Фробениуса-Перрона матрицы \(A^T\) </li>
</ol>
</div>


<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">
Заметим, что матрица $\left(\dfrac{1}{\lambda(A)}A\right)^t$ также даёт в пределе $B$. При этом $\lambda\left(\dfrac{1}{\lambda(A)}A\right) = 1$. Следовательно, без ограничения общности будем считать, что $\lambda(A) = 1$

Начнём доказательство со 2-го утверждения.

*Шаг 1.* Пусть $\underset{t\to\infty}\lim A^t = B \geq 0$

$$\begin{array}
AA^t = A^{t+1} \\
At^A = A^{t+1}
\end{array} \Rightarrow \begin{array}
AB = B \\
BA = B \Leftrightarrow A^TB^T = B^T
\end{array}$$

Каждый столбец $B$ или вектор Фробениуса-Перрона, матрицы $A$, или нулевой вектор. Аналогично, каждая строка $B$ или вектор Фробениуса-Перрона $A^T$, или нулевой вектор. Покажем, что в обоих случаях реализуется первая из альтернатив.

Допустим противное, что у матрицы $B$ есть нулевой столбец. Это означает, что в каждой строке матрицы $B$ есть нулевой элемент $\Rightarrow$ каждая строка $B$ не может быть вектором Фробениуса-Перрона $A^T$ $\Rightarrow$ $B = O$.

$$A\vec x_A = \vec x_A, \quad \vec x_A > 0 \text{ (по теореме 4) }$$

$$\Rightarrow A^t \vec x_A = \vec x_A$$

$$\underset{t\to\infty}\lim A^t \vec x_A = B\vec x_A $$

$$B \vec x_A = \vec x_A \rightarrow B \neq O$$

Противоречие. 

*Шаг 2. Необходимость.* Пусть $\underset{t\to\infty}\lim A^t = B$ существует, $B > 0$ (см. шаг 1). Тогда $\exists k \geq 1:$ $A^k > 0$. Это и означает, что матрица $A$ устойчива.

Разобьём доказательство достаточности на 2 шага.

*Шаг 3.* Достаточность (частный случай, $A > 0$ (т.е. $k=1$)).* Рассмотрим

$$\underset{1\leq i,j \leq n}\min a_{ij} = \varepsilon > 0$$

$$A\vec x_A = \vec x_A > 0$$

Возьмём

$$\underset{1\leq i,j \leq n}\min \frac{[\vec x_A]_i}{[\vec x_A]_j} = \delta > 0$$

$$\vec y(t+1) = A\vec y(t), \quad \vec y(0) \geq 0$$

$$\vec y(t) = A^t \vec y(0)$$

Если есть предел у $\vec y(t)$, то он также будет у матрицы $A^t$. $A^t \vec e_i$ — $i$-й столбец матрицы $A^t$.

$$[\vec y(t+1)]_i = \sum_{j=1}^n a_{ij} [\vec y(t)]_j \tag{✻}$$

Введём

$$\theta_i(t) = \frac{[\vec y(t)]_i}{[\vec x_A]_t}$$

т.е. по сути перемасштабируем рассматриваемые координаты. Введём также

$$\alpha(t) = \underset{1\leq i\leq n}\min\theta_i(t), \text{ и пусть } \theta_{l(t)}(t) = \alpha(t)$$

$$\beta(t) = \underset{1\leq i\leq n}\max\theta_i(t), \text{ и пусть } \theta_{s(t)}(t) = \beta(t)$$

Подставим эти выражения в сумму (✻).

$$[\vec y(t+1)]_i = \sum_{j=1}^n a_{ij}\theta_j(t)[\vec x_A]_j = \beta(t)a_{is(t)}[\vec x_A]_{s(t)} + \sum_{j \neq s(t)}a_{ij}\theta_j(t)[\vec x_A]_j \geq$$

$$\geq \beta(t)a_{is(t)}[\vec x_A]_{s(t)} + \alpha(t) \sum_{j \neq s(t)}a_{ij}[\vec x_A]_j = (\beta(t) - \alpha(t))a_{is(t)}[\vec x_A]_{s(t)} + \alpha(t) \underbrace{\sum_{j=1}^n a_{ij}[\vec x_A]_j}_{[\vec x_A]_i}$$

$$\theta_i(t+1) = \frac{[\vec y(t+1)]}{[\vec x_A]_i} \geq (\beta(t) - \alpha(t)) a_{is(t)}\frac{[\vec x_A]_{s(t)}}{[\vec x_A]_i} + \alpha(t)$$




$$(\beta(t) - \alpha(t)) a_{is(t)}\frac{[\vec x_A]_{s(t)}}{[\vec x_A]_i} + \alpha(t) \geq (\beta(t) - \alpha(t))...$$



<div style="background: red; margin: 20px">
TODO дозаполнить
</div>



$$\beta(t) \geq \alpha(t) \tag{5.2}$$

$$\alpha(t+1) - \alpha(t) \geq (\beta(t) - \alpha(t))\varepsilon\delta \geq 0 \tag{5.3}$$

$$[\vec y(t+1)]_i = \sum_{j=1}^n a_{ij}\theta_j(t)[\vec x_A]_j = \alpha(t)a_{il(t)}[x_A]_{l(t)} + \sum_{j \neq l(t)} a_{ij}[a_A]_j \theta_j(t) \leq \alpha(t)a_{il(t)}[x_A]_{l(t)} + \beta(t)\sum_{j \neq l(t)} a_{ij}[a_A]_j =$$

$$= (\alpha(t) - \beta(t)) a_{il(t)}[x_A]_l(t) + \beta(t) \underbrace{\sum_{j=1}^n a_{ij} [\vec x_A]_j}_{[\vec x_A]_i}$$

$$\theta_i(t+1) = \frac{[y(t+1)]_i}{[y(t)]_i} \leq (\alpha(t) - \beta(t)) a_{il(t)} \frac{[x_A]_{l(t)}}{[x_A]_i} + \beta(t) \leq (\alpha(t) - \beta(t))\varepsilon\delta + \beta(t)$$

Получаем

$$\beta(t) - \beta(t+1) \geq (\beta(t) - \alpha(t))\varepsilon\delta \geq 0 \tag{5.4}$$

(5.3) $\Rightarrow$ $\alpha(t+1) \geq \alpha(t)$

(5.4) $\Rightarrow$ $\beta(t) \geq \beta(t+1)$

Покажем, что $\beta(t) \geq \alpha(\tau)$

1. $t = \tau$ — см. (5.2)


2. $\tau > t$ $\Rightarrow$ $\beta(t) \geq \beta(\tau) \geq \alpha(\tau)$


3. $\tau < t$ $\Rightarrow$ $\alpha(\tau) \leq \alpha(t) \leq \beta(t)$

Поскольку монотонная ограниченная последовательность имеет предел, получаем, что 

$$\exists \underset{t\to\infty}\lim \alpha(t) = \hat\alpha, \quad \exists \underset{t\to\infty}\lim \beta(t) = \hat\beta$$

Заметим, что $\beta(t) - \alpha(t) \geq 0$ в силу неравенства (5.2), а $\dfrac{1}{\varepsilon\delta}(\alpha(t+1) - \alpha(t)) \geq \beta(t) - \alpha(t)$ в силу неравенства (5.3). По теореме о 2-х милиционерах 

$$\beta(t)-\alpha(t) \overset{t\to \infty}\longrightarrow 0$$

Следовательно $\hat\beta = \hat\alpha$. Заметим также, что 

$$\alpha(t) \leq \theta_i(t) \leq \beta(t) \quad i=1,\dots,n$$

По той же теореме, $\theta_i(t) \overset{t\to \infty}\longrightarrow \hat\alpha$, следовательно $\vec y(t) \overset{t\to \infty}\longrightarrow \hat\alpha \vec x_A(t)$

*Шаг 4. Достаточность (общий случай).* Предположим, что $\exists k: A^k > 0$.

$$t = kq(t) + r(t),$$

где $r(t) \in \{0,1,\dots,k-1\}$ — остаток, $q(t)$ — неполное частное, $q(t) \overset{t\to \infty}\longrightarrow \infty$

$$A^t = A^{r(t)} + (A^k)^{q(t)}$$

В силу шага 3, мы можем утверждать, что $\exists \underset{t\to\infty}\lim(A^k)^{q(t)} = B$. Строки и столбца матрицы $B$ будут векторами Фробениуса-Перрона матриц $A^k$ и $(A^k)^T$ соответственно.

$$A\vec x_A = \vec x_A, \vec x_A > 0, \lambda(A^k) = (\lambda(A))^k = 1$$

$$A^k\vec x_A = \vec x_A$$

$$\Rightarrow AB = B, A^2B = B, \dots, A^kB = B,$$

Значит $A^{r(t)}B = B$

$$(A^k)^q(t) = B + R(t), \text{ где } \underset{t\to\infty}\lim R(t) = 0$$

Следовательно 

$$\underset{t\to\infty}\lim AR(t) = 0, \underset{t\to\infty}\lim A^2R(t) = 0, \dots, \underset{t\to\infty}\lim A^{k-1}R(t) = 0$$

$$\underset{t\to\infty}\lim A^{r(t)}R(t) = 0$$

Итак,

$$A^t = A^{r(t)}B + A^{r(t)}R(t) = B + A^{r(t)}R(t)$$

$$\Rightarrow \underset{t\to\infty}\lim A^t = B$$
◼︎
</div>
</div>


<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<p><b>Определение 5.</b> Будем говорить, что неразложимая матрица \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\) допускает <u>циклическое разложение</u>, если существуют непустые множества \(G_0, G_1, \dots, G_{s-1}\) (\(s \geq 2\)) т.ч.  </p>
<ol>
<li> \(N = \{1, \dots, n\} = \cup_{k=0}^{s-1} G_k\) </li> <br>

<li> \(G_k \cap G_l = \varnothing\) при \(k \neq l\) </li> <br>

<li> Если \(j \in G_k\), \(a_{ij} > 0\), то \(i \in G_{(k+1)\mod s}\) </li>
</ol>
</div>



*Замечание.* Если матрица $$A$$ допускает циклическое разложение, то можно, переставляя её строки и столбцы, привести её к блочному виду:

$$E_\pi^T AE_\pi = \begin{pmatrix}
O & O & \dots & X \\
X & O & \dots & O \\
O & X & \dots & O \\
\vdots & \vdots & \ddots & \vdots \\
O & O & \dots & X 
\end{pmatrix}$$




<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<p><b>Теорема 6.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\) неразложимая матрица. Тогда следующие утверждения эквивалентны: </p>
<ol>
<li> \(A\) устойчивая матрица </li> <br>

<li> \(A\) не допускает циклических разложений </li> <br>

<li> \(\text{НОК}\{t\ |\ [A^t]_{ii} > 0\} = 1\) \(\Rightarrow\) это будет так же для любого \(i\) </li> <br>

<li> Если \(A\vec z = \omega\vec z\), \(\vec z \in \mathbb C^n\setminus\{0\}\), \(|\omega| = \lambda(A)\), то \(\omega = \lambda(A)\) </li>
</ol>
</div>



<div style="border-left: 5px solid MediumPurple; padding: 10px 20px; margin: 20px 0">

<b>Пример.</b> Матрица \(A = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}\) не является устойчивой, она не допускает циклических разложений, и т.д. (остальные свойства также верны)

</div>



*Замечание.* Пусть $$a_{ij} \geq 0$$ — вероятность перехода из состояния $$j$$ в состояние $$i$$.

<p id="eq-aa">
$$\sum_{i=1}^n a_{ij} = 1, \quad j=1,\dots,n \tag{✻✻}$$
</p>
  
Пусть $$A = \|a_{ij}\|_{i,j=1}^n$$, $$\vec p(t)$$ — распределение вероятности находиться в том или ином состоянии в момент $$t$$. Получаем
 
$$\vec p(t+1) = A\vec p(t)$$ 

Вектор Фробениуса–Перрона матрицы $$A$$ $$\vec p^*$$ будет т.ч. $$\vec p^* = A\vec p^*$$

*Упражнение.* Доказать, что из (<a href="#eq-aa">✻✻</a>) следует $$\lambda(A) = 1$$
