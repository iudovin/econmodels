---
layout: page
title: §3. Спектральные свойства неотрицательных матриц
---



Пусть $$0<\alpha<1$$. Тогда мы знаем, что

$$\frac{1}{1-\alpha} = \sum_{k=0}^\infty \alpha^k$$

Пусть $$A = \|a_{ij}\|_{i,j=1}^n \geq 0$$, $$\rho > 0$$. Тогда зададимся следующими вопросами:

$$(E-A)^{-1} \overset{?}{=} \sum_{k=0}^{\infty} A^k$$

$$(\rho E - A)^{-1} = \frac{1}{\rho} \left( E - \frac{1}{\rho}A \right)^{-1} \overset{?}{=} \sum_{k=0}^{\infty} \frac{1}{\rho^{k+1}} A^k$$

<div id="th2" style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема 2.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\). Тогда: <br> <br>
<ul>
<li> Если \(\exists (\rho E - A)^{-1} \geq 0\), то \(\rho > 0\) и ряд 
<p id="eq10">
$$ \sum_{k=0}^{\infty} \frac{1}{\rho^{k+1}}A^k \tag{10} $$
</p>
сходится, а его сумма равна \((\rho E - A)^{-1}\) </li> <br>

<li> Если \(\rho > 0\) и ряд (<a href="#eq10">10</a>) сходится, то \(\exists (\rho E - A)^{-1} \geq 0\) </li>
</ul>
</div>

<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">
  Очевидно 🙃 <br>
  
  P.S. Потом сделаю
</div>
</div>



Рассмотрим статическую модель Леонтьева

$$\vec x = A\vec x + \vec w$$

Если $$A$$ продуктивна, то по теореме <a href="#th2">2</a> 

$$\vec x = (E-A)^{-1}\vec w = \vec w + A\vec w + A^2 \vec w + \dots$$

Здесь первое слагаемое $$\vec w$$ отвечает за непосредственное производство, второе: $$A\vec w$$ — за производство сырья для производства $$\vec w$$, третье — для производства сырья для сырья и так далее.

*Замечание.* Для анализа реальных матриц затраты-выпуск6 как правило, хватает первых трех слагаемых (до $$A^2\vec w$$) 



<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Лемма 1.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\). Обозначим 

$$M(A) := \{ \rho\ |\ \exists (\rho E - A)^{-1} \geq 0 \}$$

Тогда \(M(A) = (\lambda(A), +\infty)\), где \(\lambda (A) \geq 0\)

</div>

<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">
  Очевидно 🙃 <br>
  
  P.S. Потом сделаю
</div>
</div>

<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Лемма 2.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\), \(\lambda (A) = \inf \{ \rho\ \vert\ \exists (\rho E - A)^{-1} \}\). Тогда \(\lambda(A)\) является собственным числом матрицы \(A\) и \(\exists \vec x_A \geq 0, \vec x_A \neq 0\) т.ч. \(A\vec x_A = \lambda(A)\vec x_A\)

</div>

<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">
  Очевидно 🙃 <br>
  
  P.S. Потом сделаю
</div>
</div>

<div id="th3" style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема 3 (Фробениуса–Перрона)</b> <br> <br>

Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\). Тогда: <br> <br>
<ol>
<li> Среди собственных чисел матрицы \(A\) есть неотрицательные вещественные числа, и наибольшему из них \(\lambda(A)\) соответствует неотрицательный собственный вектор \(\vec x_A\) </li> <br>

<li> Матрица \((\rho E - A)\) неотрицательно обратима (т.е. \(\exists (\rho E - A)^{-1}\)) \(\Leftrightarrow\) \(\rho > \lambda(A)\) </li> <br>

<li> Если \(\vec y \geq 0\), \(\vec y \neq 0\) и \(A\vec y \geq \mu\vec y\), то \(\mu \leq \lambda(A)\) </li> <br>

<li> Если \(\omega \in \mathbb C\) и \(\vec z \in \mathbb C^n\), \(\vec z \neq 0:\) \(A\vec z = \omega\vec z\) (т.е. \(\omega\) — собственное число матрицы \(A\)), то \(|\omega| \leq \lambda(A)\) (т.е. \(\lambda(A)\) — <i>спектральный радиус</i> матрицы \(A\)) </li>
</ol>
</div>

<div>
<button class="proofbtn">Доказательство</button>
<div class="proof">
  Очевидно 🙃 <br>
  
  P.S. Потом сделаю
</div>
</div>



Теорема Фробениуса–Перрона позволяет дать следующее определение.

<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение.</b> Будем называть \(\lambda(A)\) в условии теоремы <a href="#th3">3</a> <u>числом Фробениуса–Перрона</u> матрицы \(A\), а \(\vec x_A\) — <u>вектором Фробениуса–Перрона</u> матрицы \(A\).

</div>

*Замечание.* Простейшая динамическая модель Леонтьева 

$$\vec x(t) = A\vec x(t+1) + \vec w(t+1)$$

имеет темп сбалансированного роста $$s$$, если 

$$\exists \vec x \geq 0, \vec w > 0:\ \frac{1}{s}\vec x - A\vec x = \vec w$$

$$\phantom{\text{(теорема 1')}} \Updownarrow \text{(теорема 1')}$$

$$\exists \left( \frac{1}{s}E - A \right)^{-1} \geq 0$$

$$\phantom{\text{(теорема 3)}} \Updownarrow \text{(теорема 3)}$$

$$\frac{1}{s} > \lambda(A)$$

Получаем, что технологическое ограничение на темп роста системы определяется её числом Фробениуса–Перрона:

$$s < \frac{1}{\lambda(A)}$$



## Свойства числа Фробениуса–Перрона



Пусть $$A = \|a_{ij}\|_{i,j=1}^n \geq 0$$. Тогда:

1. $$\lambda(A^T) = \lambda(A)$$ $$ $$


2. Если $$\alpha > 0$$, то $$\lambda(\alpha A) = \alpha \lambda(A)$$


3. $$\lambda(A^t) = (\lambda(A))^t$$ $$ $$


4. Если $$B \geq A \geq 0$$, то $$\lambda(A) \leq \lambda(B)$$


5. Если $$C$$ — главная подматрица матрицы $$A$$, то $$\lambda(C) \leq \lambda(A)$$


6. Если $$\lambda(A) = 0$$, то $$A^n = 0$$ 


*Замечание.* Смысл свойства 4 в том, что если у матрицы $$A$$ меньше затраты на производство продукции, то у неё меньше ограничений на тепм сбалансированного роста.

Критерий продуктивности: $$\lambda(A) < 1$$

<div>
<button class="proofbtn"><i>Доказательство</i></button>
<div class="proof">
  Очевидно 🙃 <br>
  
  P.S. Потом сделаю
</div>
</div>
