---
layout: page
title: §2. Продуктивные матрицы
---


Вспомним определение продуктивной матрицы из <a href="../par_01">§1</a>.

<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение 1'.</b> Будем говорить, что матрица \(D = \| d_{ij} \|_{i,j=1}^n\), все внедиагональные элементы которой неположительны (\(d_{ij} \leq 0\) при \(i \neq j\)), является <u>продуктивной</u>, если \(\exists \vec x \geq 0 :\ D\vec x > 0\)

</div>

Теперь сформулируем две теоремы.

<div id="th1" style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема 1.</b> Пусть \(D = \|d_{ij}\|_{i,j=1}^n\), \(d_{ij} \leq 0\) при \(i \neq j\). Тогда следующие свойства эквивалентны: <br> <br>
<ol>
<li> \(\exists \vec x \geq 0:\) \(D\vec x > 0\) </li> <br>
 
<li> \(\forall \vec w \geq 0\) \(\exists \vec x \geq 0:\) \(D\vec x = \vec w\) </li> <br>
 
<li> <i>Условия Хокинса-Саймона</i>: 
    
$$ \Delta_k = \det\begin{Vmatrix}
d_{11} & \dots & d_{1k} \\
\vdots & \ddots & \vdots \\
d_{k1} & \dots & d_{kk}
\end{Vmatrix} > 0 \quad\quad k=1,\dots,n $$ </li> <br>

<li> \(\forall\ 1 \leq i_1 < \dots < i_k \leq n\) (\(k=1,\dots,n\)) 

$$\det\begin{Vmatrix}
d_{i_1i_1} & \dots & d_{i_1i_k} \\
\vdots & \ddots & \vdots \\
d_{i_ki_1} & \dots & d_{i_ki_k}
\end{Vmatrix} > 0$$ </li>
</ol>
</div>

▶︎ $$\dots$$ ◼︎

*Замечание.* Рассмотрим статическую модель Леонтьева $$\vec x = A\vec x + \vec w$$ в тривиальном случае ($$n=1$$). Пусть $$x$$ &mdash; объём производства, $$a_{11}x$$ &mdash; производственные затраты, $$w$$ &mdash; конечный выпуск. Тогда

$$x = a_{11} + w \quad \Leftrightarrow \quad (1-a_{11})x = w$$

Условие продуктивности:

$$1 > a_{11}$$

<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема 1'.</b> К свойствам 1&ndash;4 теоремы <a href="#th1">1</a> можно добавить следующие: <br> <br>
<ol start="5">
<li> \(\exists \vec p \geq 0:\) \(D^T\vec p > 0\) </li> <br>
 
<li> \(\forall \vec\pi \geq 0\) \(\exists \vec p \geq 0:\) \(D^T\vec p = \vec\pi\) </li> <br>

<li> Все последовательные главные миноры матрицы \(D^T\) положительны </li> <br>

<li> Все главные миноры матрицы \(D^T\) положительны </li> <br>

<li> \(\exists D^{-1} \geq 0\) </li>
</ol>
</div>

▶︎ $$\dots$$ ◼︎
